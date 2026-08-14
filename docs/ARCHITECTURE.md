# 🏗️ Arquitetura do Walkers: Brasil

## Overview

Walkers: Brasil é uma ficção interativa modular, desacoplada em:

1. **Data Layer** (`src/data/story.json`) — Narrativa como dados estruturados
2. **Game Engine** (`src/game/engine.js`) — Renderização e transições
3. **State Manager** (`src/game/state.js`) — Gerenciamento de estado (recursos, inventário, dia)
4. **Mechanics** (`src/game/mechanics.js`) — D20, eventos aleatórios, efeitos
5. **UI Layer** (`src/ui/`) — Componentes visuais (HUD, escolhas, animações)
6. **Storage** (`src/utils/storage.js`) — Save/load em localStorage

## Estrutura de Dados

### Cena (Scene)

```json
{
  "scene_id": {
    "text": "Narrativa...",
    "effects": { "health": -10, "sanity": 5, "day": 1 },
    "choices": [ { "text": "Ação", "next": "cena_id", "effects": {...} } ]
  }
}
```

### Estado (Game State)

```javascript
state = {
  health: 100,         // 0-100
  sanity: 100,         // 0-100
  food: 3,             // 0-∞
  water: 3,            // 0-∞
  day: 0,              // Contador de dias
  infected: false,     // Status de infecção
  infectionDay: null,  // Dia da infecção (para countdown)
  inventory: []        // Items coletados
}
```

### Efeitos (Effects)

```javascript
effects = {
  health: -10,         // Modificador de saúde
  sanity: 5,           // Modificador de sanidade
  food: 2,             // Incrementar comida
  water: -1,           // Decrementar água
  day: 1,              // Avançar dias (dispara randomEvent)
  item: "canivete",    // Adicionar ao inventário
  infect: true,        // Contrair infecção
  infect: false        // Remover infecção
}
```

### Escolha (Choice)

```javascript
choice = {
  text: "Descrição da ação",
  next: "cena_proxima",
  effects: { health: -5 },           // Efeitos imediatos
  requires: { hasItem: "canivete" }, // Requisitos (bloqueiam)
  roll: {                            // Mecânica de risco
    dc: 10,            // Dificuldade (1-20)
    success: "sucesso",
    failure: "falha"
  }
}
```

## Fluxo de Jogo

```
┌─────────────────┐
│  renderScene()  │
└────────┬────────┘
         │
    ┌────v────┐
    │ Valida? │──❌──> Reinicia
    └────┬────┘
         │✅
    ┌────v──────────┐
    │ Aplica effects│
    └────┬──────────┘
         │
    ┌────v────────────┐
    │ randomEvent()?   │──> Adiciona msg de evento
    └────┬────────────┘
         │
    ┌────v─────┐
    │ checkDeath│
    └────┬─────┘
         │
      ✅ Vivo? ──> Renderiza cena + escolhas
         │
         ❌ Morreu ──> Fim do jogo + Botão Restart
```

## D20 Mechanic

```javascript
function attemptRoll(choice) {
  const roll = rollD20();  // 1-20
  const dc = choice.roll.dc;
  
  if (roll >= dc) {
    // Sucesso
    renderScene(choice.roll.success);
  } else {
    // Falha
    renderScene(choice.roll.failure);
  }
}
```

**Raridades:**
- `roll === 1` → Evento super positivo (2x suprimentos)
- `roll === 20` → Evento catastrófico (-10 health, -5 sanity)
- `roll === 2-3` → Levemente positivo
- `roll === 19-20` → Levemente negativo
- Resto → Sem evento adicional

## Sistema de Infecção

1. **Contração:** `effects.infect = true` → `state.infected = true, state.infectionDay = state.day`
2. **Contagem:** HUD mostra "Infectado - X dias restantes"
3. **Morte:** `checkDeath()` verifica `state.day - state.infectionDay >= 3`

**Cura possível:**
- Encontrar `kit_medico` na cena `saquear_carros_sucesso`
- Usar antes de 3 dias: `effects.infect = false` → Remova a infecção

## Save/Load

```javascript
// Save
localStorage.setItem('apocalipseBrasilSave', JSON.stringify({ state, currentScene }))

// Load
const { state, currentScene } = JSON.parse(localStorage.getItem('apocalipseBrasilSave'))
```

## Expansão Futura

### Curto Prazo
- [ ] Separar story.json em arquivo externo
- [ ] Adicionar som/música (Web Audio API)
- [ ] Mais animações (Intersection Observer)
- [ ] Dark mode toggle

### Médio Prazo
- [ ] Backend Node.js para leaderboard (dias sobrevividos)
- [ ] Estatísticas por final (qual % escolheu cada caminho)
- [ ] Editor visual de cenas (drag-drop)

### Longo Prazo
- [ ] Multiplayer (websockets)
- [ ] Mod system (carregar story.json customizado)
- [ ] Mobile app (React Native)
- [ ] Integração com Twitch (stream interativo)

## Convenções

### Nomes de Cenas

- `start` — Início
- `trilhos`, `vagao`, `esperar` — Ramificações iniciais
- `rodovia`, `favela`, `mato` — Segundo nível
- `alphaville`, `aparecida`, `sertao` — Finais
- `sucesso`, `falha` — Resultados de rolls

### Nomes de Items

- `canivete`, `kit_medico`, `radio`, `fosforos` — Items coletáveis
- Sempre lowercase + underscore

### Efeitos de Dia

- Escolhas que avançam `day: 0` = mesma cena
- Escolhas que avançam `day: 1` = 1 dia (sem evento aleatório)
- Escolhas que avançam `day: 2+` = Múltiplos dias (com chance de evento)

## Testing

```bash
# Próximo: Jest + Coverage
npm test

# Rotas críticas a testar:
# 1. Death conditions (health ≤ 0, sanity ≤ 0, infecção 3+ dias)
# 2. D20 rolls (sucesso/falha corretos)
# 3. Save/load (persistência)
# 4. Inventário (items aparecem/desaparecem)
# 5. Random events (distribuição)
```

## Performance

- **Sem frameworks pesados** → ~50KB gzipped
- **Lazy loading de imagens** → Pexels CDN
- **localStorage** em vez de IndexedDB → Simples, suficiente
- **Fade-in animations** → CSS transitions (GPU-accelerated)

## Deployment

```bash
# 1. Build
npm run build  # → dist/

# 2. Upload para Canva Sites
# Manual: Arrastar dist/index.html para monarchkardeck.my.canva.site
# Automático: CI/CD (GitHub Actions) em roadmap
```
