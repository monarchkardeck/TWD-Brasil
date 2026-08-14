# 🤝 Contribuindo para Walkers: Brasil

## Como Começar

### 1. Fork e Clone

```bash
git clone https://github.com/monarchkardeck/TWD-Brasil.git
cd TWD-Brasil
git checkout -b feat/sua-feature
```

### 2. Setup

```bash
npm install
npm run dev  # Vite dev server
```

### 3. Tipos de Contribuição

#### 🎨 Adicionar Cenas/História

1. Edite `src/data/story.json`
2. Siga o formato:

```json
{
  "nova_cena": {
    "text": "Narrativa em português...",
    "effects": { "day": 1 },
    "choices": [
      {
        "text": "Opção 1",
        "next": "cena_proxima",
        "effects": { "health": -5 }
      }
    ]
  }
}
```

3. Teste:
   - Play no browser
   - Verifique transições
   - Valide effects

#### 🐛 Corrigir Bugs

1. Abra uma [Issue](https://github.com/monarchkardeck/TWD-Brasil/issues)
2. Descreva: comportamento esperado vs. real
3. Crie branch: `fix/descricao-bug`
4. Corrija em `src/game/` ou `src/utils/`
5. Teste e faça PR

#### ✨ Melhorar UI/UX

1. Edite `src/ui/styles.css` ou `index.html`
2. Use Tailwind (não adicione CSS novo se possível)
3. Teste responsividade (mobile, tablet, desktop)
4. Faça PR com screenshot antes/depois

#### 🔧 Adicionar Mecânicas

1. Implemente em `src/game/mechanics.js`
2. Exponha função pública
3. Documente com JSDoc
4. Adicione testes em `tests/`

### 4. Padrões de Código

**JavaScript:**
```javascript
// ✅ Bom
function renderScene(sceneId) {
  const scene = story[sceneId];
  if (!scene) {
    console.error('Cena não encontrada:', sceneId);
    return;
  }
  // ...
}

// ❌ Evite
function render(s) {
  var scene = story[s];
  if (scene != null) { ... }  // Use ===
}
```

**Nomes:**
- Funções: `camelCase` → `renderScene`, `applyEffects`
- Constantes: `UPPER_SNAKE` → `MAX_HEALTH`, `DEFAULT_FOOD`
- IDs de cenas: `snake_case` → `nova_cena`, `hospital_infectado`
- Items: `snake_case` → `kit_medico`, `canivete`

**Comentários:**
```javascript
// Evento raro: sorte encontrando suprimentos
if (roll === 1) {
  // Código...
}
```

### 5. Git Workflow

```bash
# 1. Crie branch
git checkout -b feat/minha-feature

# 2. Commit com mensagem clara
git commit -m "feat: adiciona cena do aeroporto"

# 3. Push
git push origin feat/minha-feature

# 4. Abra PR no GitHub
# Descreva mudanças, screenshots, testes realizados
```

**Tipos de commit:**
- `feat:` Nova feature
- `fix:` Correção de bug
- `docs:` Documentação
- `style:` Formatação (não muda lógica)
- `refactor:` Refatoração
- `test:` Testes
- `chore:` Dependências, config

### 6. Pull Request Checklist

Antes de enviar PR, verifique:

- [ ] Código testado no `npm run dev`
- [ ] Sem console.errors ou warnings
- [ ] Nomes de variáveis claros
- [ ] Comentários em lógica complexa
- [ ] Sem comentários de debug
- [ ] Compatível com mobile (Chrome DevTools)
- [ ] Save/load funcionam (se modificou state)
- [ ] Descrição clara no PR

### 7. Roadmap

**v1.0 (MVP)**
- [x] Story base (30 cenas)
- [x] Mecânicas de risco (D20)
- [x] Save/load
- [x] Mobile UI

**v1.1**
- [ ] Separar story em JSON externo
- [ ] Adicionar música/SFX
- [ ] Dark mode
- [ ] Mais eventos aleatórios

**v2.0**
- [ ] Backend (leaderboard, stats)
- [ ] Mod system
- [ ] Editor visual
- [ ] Versão mobile nativa

### 8. Questões?

- 📝 Documentação: [docs/ARCHITECTURE.md](ARCHITECTURE.md)
- 🐛 Bugs: [Issues](https://github.com/monarchkardeck/TWD-Brasil/issues)
- 💬 Discussão: [Discussions](https://github.com/monarchkardeck/TWD-Brasil/discussions)

---

Obrigado por contribuir! 🧟‍♂️
