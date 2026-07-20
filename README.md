# Color Logic: Sequence Breaker

## Descrição do Jogo

**Sequence Breaker** é um jogo de lógica e puzzle onde você deve organizar peças coloridas em uma sequência específica. O jogo apresenta uma estética futurista/cyberpunk com animações fluidas e efeitos visuais.

## Funcionamento

O jogo gera uma **sequência secreta** de cores (3 a 8 peças dependendo do nível) que você precisa descobrir. As peças são distribuídas em formato geométrico (polígono regular) e começam embaralhadas.

### Cores disponíveis (8 total):
- 🔷 Azul (◆)
- 🟣 Roxo (●)
- 🟠 Âmbar (▲)
- 🟢 Esmeralda (■)
- 🔴 Carmesim (★)
- 🩷 Rosa (♦)
- 🔵 Ciano (○)
- 🟡 Lima (□)

Cada cor possui um **símbolo único** para acessibilidade (daltônicos).

---

## Botões e Controles

### Botões Principais:

1. **✓ Verificar** - Confirma se a sequência atual está correta
   - Mostra peças corretas (verde) e incorretas (vermelho)
   - Atualiza a barra de progresso
   - Se errar: perde 1 vida

2. **💡 Dica** - Revela a posição correta de uma peça
   - Custa 1 dica (quantidade limitada)
   - Destaca onde a peça deve ir (amarelo) e onde ela está (verde)
   - A troca deve ser feita manualmente

3. **↺ Reiniciar** - Reinicia o jogo do nível 1
   - Reseta score e combo
   - Mantém progresso salvo

4. **❓ Ajuda** - Abre modal com regras do jogo

### Atalhos de Teclado:
- **D** - Usar dica
- **?** - Mostrar regras
- **ESC** - Fechar modal

---

## Condições de Vitória

### ✅ Vitória:
- Todas as peças estão na posição correta
- Aparece tela "NÍVEL COMPLETADO!"
- Ganha estrelas baseado no desempenho:
  - ⭐⭐⭐ (3 estrelas): Sem erros
  - ⭐⭐ (2 estrelas): Até 2 erros
  - ⭐ (1 estrela): Mais de 2 erros

### Bônus de Pontuação:
- **Pontos base:** 100 × número de acertos
- **Combo:** +50 × combo atual
- **Perfeito:** +500 (se acertar na 1ª tentativa)
- **Dificuldade:** +50 × (slots - 3)
- **Dicas não usadas:** +100 × dicas restantes

---

## Condições de Derrota

### ❌ Game Over:
- **Vidas chegam a 0**
- Quando erra uma verificação, perde 1 vida
- Quantidade de vidas calculada matematicamente baseada nas permutações possíveis:
  - Nível 1-2 (3 cores): 3 vidas
  - Nível 3-5 (4 cores): 4-5 vidas
  - Nível 6-9 (5 cores): 6-7 vidas
  - Nível 10+ (6-8 cores): Até 15 vidas

### Sistema de Combo:
- **Combo aumenta** quando acerta na sequência completa
- **Combo reseta** quando erra
- Multiplicador de pontos: x1, x2, x3...

---

## Progressão de Níveis

| Níveis | Cores | Permutações | Vidas |
|--------|-------|-------------|-------|
| 1-2 | 3 | 6 | 3 |
| 3-5 | 4 | 24 | 4-5 |
| 6-9 | 5 | 120 | 6-7 |
| 10+ | 6-8 | 720+ | 8-15 |

### Dicas Disponíveis:
- Ganha 1 dica a cada 3 níveis
- Fórmula: `floor((nível - 1) / 3) + 1`

---

## Recursos Adicionais

### 📊 Estatísticas Salvas (LocalStorage):
- Maior score
- Nível atual
- Combo máximo
- Número de jogos
- Data do último jogo

### 🎮 Interface:
- **Barra de progresso:** Mostra % de peças corretas
- **Histórico:** Registra todas as tentativas
- **Performance:** Estrelas em tempo real
- **Partículas:** Efeitos visuais ao trocar peças
- **Conectores:** Linhas entre peças que mudam de cor (verde=correto, vermelho=errado)

### 💾 Salvamento Automático:
- Salva progresso ao completar nível
- Indicador visual "💾 Salvo!" aparece brevemente
- Botão "Resetar Progresso" limpa todos os dados

---

## Como Jogar

1. Observe as peças coloridas embaralhadas no tabuleiro
2. Clique em duas peças para trocá-las de posição
3. Clique em "Verificar" para testar sua sequência
4. As peças corretas ficam verdes, as erradas ficam vermelhas
5. Continue trocando até acertar todas as posições
6. Use dicas (tecla D) quando estiver com poucas vidas
7. Complete o nível para avançar e ganhar pontos!

---

## Tecnologias Utilizadas

- HTML5
- CSS3 (com animações e gradientes)
- JavaScript (ES6+)
- LocalStorage para persistência de dados
- Design responsivo

---

## Autor

Desenvolvido como um projeto de jogo de lógica com foco em acessibilidade e experiência do usuário.
