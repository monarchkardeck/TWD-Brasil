# 🧟 Walkers: Brasil

**Ficção interativa de sobrevivência pós-apocalíptico**

Um jogo narrativo não-linear ambientado no Brasil durante um surto zumbi. Cada escolha tem consequências permanentes. Gerencie seus recursos. Sobreviva.

## 🎮 Jogar

- **URL:** [monarchkardeck.my.canva.site](https://monarchkardeck.my.canva.site)
- **Repositório:** [github.com/monarchkardeck/TWD-Brasil](https://github.com/monarchkardeck/TWD-Brasil)

## 🏗️ Estrutura do Projeto

```
walkers-brasil/
├── index.html           # SPA principal
├── src/
│   ├── game/            # Lógica do jogo
│   │   ├── state.js     # Gerenciador de estado
│   │   ├── engine.js    # Motor de renderização
│   │   └── mechanics.js # Mecânicas (D20, efeitos, eventos)
│   ├── data/            # Dados estruturados
│   │   ├── story.json   # Narrativa (cenas, escolhas)
│   │   └── constants.js # Constantes do jogo
│   ├── ui/              # Componentes UI
│   │   ├── hud.js       # Status HUD
│   │   └── styles.css   # Estilos customizados
│   └── utils/           # Utilitários
│       ├── storage.js   # Save/load
│       └── logger.js    # Debug
├── docs/                # Documentação
│   ├── ARCHITECTURE.md  # Design do sistema
│   ├── STORY.md         # Guia narrativo
│   └── CONTRIBUTING.md  # Como contribuir
├── tests/               # Testes
│   └── game.test.js
├── package.json         # Dependências (Vite, etc)
└── .gitignore
```

## 📖 Características

- ✅ **30+ cenas** interconectadas
- ✅ **Sistema de recursos:** Saúde, Sanidade, Comida, Água
- ✅ **Mecânicas de risco:** Testes D20 em ações perigosas
- ✅ **Sistema de infecção:** Contador de dias para morte
- ✅ **Inventário:** Items persistentes que abrem escolhas
- ✅ **Múltiplos finais:** 8+ desfechos diferentes
- ✅ **Save/Load:** Persistência em localStorage
- ✅ **UI responsiva:** Mobile-friendly

## 🔧 Stack

- **Frontend:** Vanilla JS (sem frameworks pesados)
- **Estilo:** Tailwind CSS + custom animations
- **Hospedagem:** Canva Sites (monarchkardeck.my.canva.site)
- **Versionamento:** Git + GitHub

## 🚀 Quick Start

```bash
# 1. Clone
git clone https://github.com/monarchkardeck/TWD-Brasil.git
cd TWD-Brasil

# 2. Develop
npm install
npm run dev  # Vite dev server (localhost:5173)

# 3. Build
npm run build

# 4. Deploy
# Copie dist/ para monarchkardeck.my.canva.site
```

## 📝 Desenvolvimento

- **main** → Produção (hospedado em Canva)
- **develop** → Integração de features
- **feat/\*** → Features em desenvolvimento
- **docs/\*** → Documentação

Veja [CONTRIBUTING.md](docs/CONTRIBUTING.md) para detalhes.

## 🎲 Game Design

### Sistema de Recursos

| Recurso | Min | Max | Efeito |
|---------|-----|-----|--------|
| ❤️ Saúde | 0 | 100 | ≤0 = MORTE |
| 🧠 Sanidade | 0 | 100 | ≤0 = LOUCURA |
| 🍖 Comida | 0 | ∞ | Incrementa saúde |
| 💧 Água | 0 | ∞ | Incrementa saúde |
| 🦠 Infecção | - | - | 3 dias até morte |

### Mecânicas de Risco

```
roll d20 >= DC
✅ Sucesso → Caminho vantajoso
❌ Falha → Consequências
```

## 📊 Estatísticas

- **Cenas:** 32
- **Escolhas totais:** ~120
- **Finais únicos:** 8
- **Eventos aleatórios:** 5
- **Items:** 6

## 🤝 Contribuir

Quer expandir a história, corrigir bugs ou sugerir features?

1. Abra uma [issue](https://github.com/monarchkardeck/TWD-Brasil/issues)
2. Faça fork e crie uma branch (`feat/sua-feature`)
3. Commit e push
4. Abra um PR descrevendo as mudanças

Veja [CONTRIBUTING.md](docs/CONTRIBUTING.md).

## 📜 Licença

MIT — Use livremente em projetos pessoais e comerciais.

## 🧟 Créditos

- **Narrativa & Game Design:** monarchkardeck
- **Imagens:** Pexels (open source)
- **Ícones:** Lucide (MIT)
- **UI:** Tailwind CSS

---

**Última atualização:** 14 ago 2026  
**Status:** 🟢 Em Desenvolvimento Ativo
