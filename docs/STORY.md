# 📖 Guia Narrativo — Walkers: Brasil

## Temas

- **Escolha irrevogável:** Cada decisão molda o destino
- **Sobrevivência brutal:** Recursos escassos, decisões difíceis
- **Brasil fragmentado:** Diferentes regiões, diferentes realidades
- **Humanidade em crise:** Confiança vs. traição

## Estrutura Narrativa

### Ato 1: Caos (Dia 0-3)
**Localização:** Metrô de São Paulo
**Tema:** Descoberta do apocalipse

- **start** → Detectar zumbis no metrô
- Caminho 1: **trilhos** → Fuga pela cidade
- Caminho 2: **vagao** → Confronto direto com infecção
- Caminho 3: **esperar** → Morte passiva (game over)

**Pontos de Contato:**
- Primeiro "walker" (infectado)
- Primeiro recurso escasso (comida, água)
- Primeira escolha entre fuga vs. enfrentamento

---

### Ato 2: Fragmentação (Dia 3-15)
**Localização:** Grande São Paulo
**Tema:** Diferentes respostas do grupo social

#### Ramificação A: **Rodovia** (+ Alphaville)
- Êxodo em massa
- Saque de carros (risco D20)
- Encontro com enclave militar-corporativo
- **Final:** Alphaville (autoridade, disciplina, preço moral alto)

#### Ramificação B: **Favela** (+ Zona Leste)
- Organização comunitária
- Lei de ferro: "Quem reanima, a gente resolve"
- Roubo de suprimentos (risco D20)
- **Final:** PCC (lealdade à Irmandade, violência institucionalizada)

#### Ramificação C: **Túneis/Superfície** (+ Interior)
- Isolamento
- Encontro casual com caravana
- Oportunidade de liderança (galpão)
- **Final (Provisório):** Galpão independente (fragilidade)

---

### Ato 3: Reconstrução (Dia 15-365)
**Localização:** Interior paulista, sertão, litoral
**Tema:** Novos sistemas emergem

#### Finais Possíveis:

**1. Alphaville** (Dia 7-90)
- Militar-corporativa: painéis solares, milícia
- Preço: Desumanização
- Mensagem: "Eficiência à custa da humanidade"

**2. Aparecida** (Dia 120)
- Religião + esperança: Basílica, hospital
- Ciclo de Irmã Clara: Cuidado humano
- Mensagem: "Fé como bússola"
- Tensão: Cisma crescente, Resende bate à porta

**3. Governo de Resende** (Dia 180)
- Estado restaurado (militares, burocracia)
- Conflito: Guerras entre sobreviventes
- Mensagem: "Os vivos matam os vivos"

**4. Fazenda Santa Bárbara** (Dia 150)
- Feudalismo moderno: Coronel Álvaro
- Segurança em troca de submissão
- Mensagem: "Ordem oligárquica"

**5. Sítio/Isolamento** (Dia 365)
- Solidão total: Segurança, mas loucura
- Rádio como contacto com mundo
- Mensagem: "Existe vida após tudo?"

**6. Ilhabela** (Dia 60)
- Isolamento em ilha: Segurança piratas
- Mar como muro intransponível
- Mensagem: "Paradoxo seguro"

**7. Fernando de Noronha** (Dia 240)
- Pesquisa científica: Dra. Helena
- Sem cura, mas conhecimento
- Mensagem: "Esperança na compreensão"

**8. Nova Canudos** (Dia 90)
- Messianismo no sertão: Fé + isolamento
- Pura, mas desconectada
- Mensagem: "Refúgio espiritual"

---

## Mecânicas Narrativas

### Sistema de Infecção

**Contração:**
- Cena `mordida` (encontro com walker)
- Efeito: `-20 health, infect: true`

**Progressão:**
- Dia 1: Febre, delírio (sanidade -5)
- Dia 2: Tremores, alucinações (sanidade -10)
- Dia 3: Colapso (morte iminente)

**Cura (rara):**
- Encontrar `kit_medico` (cena `saquear_carros_sucesso`)
- Usar antes de dia 3
- Efeito: `infect: false, health: -10` (custo: dor)

**Morte por infecção:**
- Mensagem: "🦠 A febre consumiu você. Você se tornou um deles."

### Morte por Recursos

**Saúde ≤ 0:**
- Causas: Combate, ferimentos não tratados, infecção avançada
- Mensagem: "☠️ Seu corpo não aguentou..."

**Sanidade ≤ 0:**
- Causas: Decisões morais pesadas, solidão, horrores
- Mensagem: "🕳️ Sua mente se despedaçou..."

### Eventos Aleatórios (D20)

| Roll | Evento | Efeito |
|------|--------|--------|
| 1 | 🍀 Sorte (suprimentos) | +1-2 food, +1-2 water |
| 2 | 🌅 Nascer do sol | +5 sanity |
| 19 | 👁️ Observado | -5 sanity |
| 20 | ⚡ Tempestade | -10 health, -5 sanity |
| Resto | (nada) | — |

---

## Personagens-chave

### NPCs Mencionados (não interativos)

- **Sargento da PM** — Autoridade bruta, mas com humanidade
- **Padre** — Fé, proteção, esperança
- **Líder da Favela** — Lei de ferro, eficiência cruel
- **Coronel Álvaro** — Patriarca feudal
- **Irmã Clara** — Cuidado, hospital, esperança
- **Capitão Ramos** — Estado militar restaurado
- **Dra. Helena** — Ciência, pesquisa
- **Benzedeira** — Cura popular, compaixão

---

## Locais-chave

### Metrô de São Paulo (Dia 0)
- Primeiro encontro com apocalipse
- Escolha: fuga vs. confronto

### Rodovia Dutra (Dia 3-7)
- Êxodo em massa
- Conflito entre grupos

### Zona Leste/Favela (Dia 2-90)
- Organização horizontal → Autoritarismo
- Lei da comunidade

### Alphaville (Dia 7-90)
- Enclave militar-corporativo
- Segurança = disciplina total

### Santuário de Aparecida (Dia 120)
- Basílica como refúgio
- Religião + esperança + crise

### Sertão/Nova Canudos (Dia 90)
- Isolamento extremo
- Messianismo

### Ilhabela (Dia 60)
- Ilha = segurança vs. isolamento
- Piratas como governo

### Fernando de Noronha (Dia 240)
- Pesquisa científica
- Futuro incerto mas esperançoso

---

## Temas Recorrentes

### Autoridade
- Quem governa quando a lei falha?
- Alphaville: Militar-corporativa
- PCC: Organização criminal
- Resende: Estado restaurado
- Aparecida: Religiosa

### Solidão vs. Comunidade
- Isolado no sítio: Segurança + loucura
- Galpão: Comunidade + vulnerabilidade
- Ilhabela: Isolado seguro

### Moral
- Saquear para sobreviver?
- Matar infectados vs. tentar salvar?
- Sacrificar uns para salvar muitos? (Alphaville)
- Lealdade cega? (PCC)

### Esperança
- Aparecida: Esperança religiosa
- Noronha: Esperança científica
- Sítio: Esperança na simplicidade
- Resende: Esperança na ordem

---

## Estatísticas

- **32 cenas** mapeadas
- **~8 finais** únicos
- **~120 escolhas** totais
- **5 eventos aleatórios** (D20)
- **6 items** coletáveis: canivete, kit_medico, radio, fosforos, e 2 a adicionar

---

## Expansões Futuras

### Curto Prazo
- [ ] Mais 10 cenas (Campinas, Sorocaba, Jundiaí)
- [ ] Personagens nomeados (diálogos)
- [ ] Consequências de longo prazo (ações no Dia 5 afetam Dia 120)

### Médio Prazo
- [ ] Relacionamentos (NPC trust/distrust)
- [ ] Tecnologia (rádio → contato com outros grupos)
- [ ] Fações (aliar-se a grupos específicos = opções bloqueadas)

### Longo Prazo
- [ ] Multiplayer (histórias cruzadas: seu Dia 7 afeta outro jogador Dia 120)
- [ ] Mod editor visual
- [ ] Leaderboard (dias sobrevividos, final alcançado)
