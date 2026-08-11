<!-- SEED: established with the user before implementation; re-run /impeccable document once the page is rebuilt in this world, to capture the actual tokens and components. -->

---
name: O Código da Tonalização
description: Guia de colorimetria para tonalização — identidade luxo de brand book, preto e dourado sobre ivory.
colors:
  ink: "#121110"
  ivory: "#F2ECE0"
  ivory-paper: "#FAF7F0"
  gold: "#C9A24B"
  gold-deep: "#7D6225"
  cream-text: "#F4EEE1"
  charcoal-text: "#1C1A17"
typography:
  display:
    fontFamily: "Playfair Display, Georgia, serif"
    fontWeight: 700
    letterSpacing: "0.01em"
    lineHeight: 1.02
  script:
    fontFamily: "Alex Brush, Great Vibes, cursive"
    fontWeight: 400
  label:
    fontFamily: "Jost, system-ui, sans-serif"
    fontSize: "0.72rem"
    letterSpacing: "0.18em"
    fontWeight: 500
  body:
    fontFamily: "Jost, system-ui, sans-serif"
    fontSize: "1rem"
    fontWeight: 400
    lineHeight: 1.6
rounded:
  none: "0px"
spacing:
  sm: "8px"
  md: "16px"
  lg: "32px"
  xl: "64px"
components:
  button-primary:
    backgroundColor: "transparent"
    textColor: "{colors.gold}"
    rounded: "{rounded.none}"
    padding: "16px 32px"
  button-primary-hover:
    backgroundColor: "{colors.gold}"
    textColor: "{colors.ink}"
---

# Design System: O Código da Tonalização

## Overview

**Creative North Star: "O Brand Book de Ateliê"**

Este mundo vem diretamente do brand book real do produto (`uploads/O Codigo da Tonalizacao.pdf`, assinado por Ana Ritter Beauty Concept): um mat ivory que emoldura painéis quase pretos, onde ficha técnica vira ourivesaria — título serifado enorme, filetes dourados de 1px como única ornamentação, e uma assinatura em script dourado carimbando autoria. É registro de estúdio de coloração de luxo, não um curso online genérico: precisão de método com acabamento de joalheria, nunca gritado.

O sistema abandona por completo o Nocturne (dark roxo-azulado, botões outline neutros) usado na primeira versão da página — essa era uma pele emprestada de outro produto, não a identidade real do ebook. A substituição preserva conteúdo, oferta e estrutura de vendas; troca só a pele visual, ancorada no artefato real que a cliente recebe.

**Key Characteristics:**
- Mat ivory por fora, painel quase preto por dentro — o mesmo par de fundos em toda a página, nunca um terceiro tom.
- Serifada bold em caixa alta para títulos de seção, que se sustentam sozinhos, sem etiqueta decorativa acima.
- Script dourado reservado para citações da autora e a assinatura — nunca para corpo de texto.
- Dourado é linha, moldura e texto pontual; nunca preenchimento de área grande.

## Colors

Paleta de dois fundos (ivory / quase-preto) com um único acento dourado — mono-acento, como o Nocturne que substitui, mas quente em vez de frio.

### Primary
- **Dourado de Ateliê** (`#C9A24B`): acento único — traços e filetes, bordas de botão, placa e card, ícones de linha, aspas e assinatura em script. Sobre o preto de ateliê passa 7.86:1. Em texto/botão sobre fundo ivory usar sempre o passo mais escuro, **Dourado Profundo** (`#7D6225`, ajustado para manter ≥4.5:1 contra ambos os tons de ivory — WCAG AA) — nunca o dourado claro em texto pequeno sobre ivory, ele fica abaixo de 3:1 e ilegível.

### Neutral
- **Preto de Ateliê** (`#121110`): fundo dos painéis internos (hero, capítulos, cards de destaque) — nunca preto puro CSS (`#000`).
- **Ivory de Mat** (`#F2ECE0`): fundo da página fora dos painéis — a moldura que dá respiro aos blocos pretos.
- **Papel Ivory** (`#FAF7F0`): variante mais clara do ivory para cards claros e superfícies elevadas sobre o mat.
- **Creme sobre Preto** (`#F4EEE1`): cor de texto/título dentro dos painéis pretos — nunca branco puro.
- **Carvão sobre Ivory** (`#1C1A17`): cor de texto de corpo sobre fundo ivory — nunca preto puro.

### Named Rules
**The Two-Ground Rule.** Toda a página vive entre exatamente dois fundos — ivory por fora, quase-preto por dentro dos painéis. Nunca um terceiro tom de fundo neutro por variedade.

## Typography

**Display Font:** Playfair Display (ou serifada de alto contraste equivalente), com Georgia como fallback.
**Script Font:** Alex Brush ou Great Vibes, para citações da autora e assinatura.
**Body/Label Font:** Jost.

**Character:** Uma serifada editorial de alto contraste para autoridade e escala, contra um sans neutro e discretamente tracked para o texto funcional — a mesma tensão "manuscrito de mestre / ficha técnica" que o brand book carimba em cada página.

### Hierarchy
- **Display** (700, `clamp(2.4rem, 5vw, 4.2rem)`, line-height 1.02, caixa alta): títulos de capítulo/seção — "FUNDAMENTOS DA COLORIMETRIA", nome do ebook.
- **Script accent** (400, `clamp(1.4rem, 2.5vw, 2rem)`): citações de autoridade da Ana Ritter e a assinatura; nunca mais de uma ocorrência por seção.
- **Label** (500–600, 11–12px, letter-spacing 0.18em, caixa alta): legenda de placa, título da Dica e crédito de citação. Sempre **depois** ou **dentro** do bloco que qualifica, nunca acima de um título.
- **Body** (400, 16px, line-height 1.6): parágrafos explicativos, largura de leitura confortável (60–70ch).

### Named Rules
**The No-Eyebrow Rule.** Nenhum label decorativo acima de um título. O título carrega o próprio peso; se ele precisa de uma etiqueta em cima para fazer sentido, o título é que está fraco. (A landing usava "Capítulo 1 · O problema" como eyebrow — era fantasia: a página de vendas não tem capítulos, o ebook é que tem.)

**The Drawn-Mark Rule.** Marcas e bullets são desenhadas (traço dourado via `::before`, SVG em traço), nunca um glifo Unicode — travessão, seta ou emoji fazendo papel de ícone.

## Layout

Layout assimétrico, alinhado à esquerda, herdado da versão anterior: títulos flush-left, conteúdo colado na margem esquerda com respiro à direita — o brand book usa a mesma lógica com o texto sempre à esquerda do retrato. Painéis pretos funcionam como cards de largura de seção (o "documento dentro da página"), respirando dentro de generosa margem ivory ao redor — nunca full-bleed preto de ponta a ponta como o Nocturne fazia.

## Elevation & Depth

Sem sombras difusas. A profundidade vem do contraste ivory/preto entre camadas e de uma borda/linha dourada fina como aresta — o brand book não usa nenhum drop-shadow, só blocos de cor nítidos com bordas finas.

### Named Rules
**The Hard-Edge Rule.** Elevação é contraste de cor e uma borda de 1px, nunca `box-shadow` difuso.

## Shapes

Cantos retos ou quase retos (raio 0–4px) em painéis e botões — o brand book não arredonda nada. Bordas finas de 1px em dourado ou creme translúcido definem os limites dos painéis pretos contra o mat ivory.

## Components

### Buttons
- **Shape:** cantos retos (raio 0–2px).
- **Primary:** borda 1px dourada, texto dourado, fundo transparente em repouso — preenche de dourado sólido com texto preto no hover (inversão de contraste, não tint).
- **Hover / Focus:** inversão sólida no hover; foco com contorno dourado 2px offset.
- **Secondary:** borda creme/ivory translúcida sobre painel preto, ou carvão translúcido sobre ivory.

### Cards / Painéis de Capítulo
- **Corner Style:** reto (raio 0–4px).
- **Background:** preto de ateliê (`#121110`), com generosa margem ivory ao redor.
- **Border:** 1px dourado fino, sem etiqueta na moldura.
- **Internal Padding:** generoso (`--space-8`/`xl` equivalente), o brand book nunca aperta o conteúdo dentro do painel.

### Placa de Material (`.plate`) — componente-assinatura
- **O que é:** a moldura em que páginas reais do ebook entram na landing: borda 1px dourada, fundo preto de ateliê, imagem a 100% de largura, legenda tracked em caixa alta abaixo.
- **Por quê:** a página prova o produto mostrando o próprio material. A moldura faz a página lida como artefato citado, não como imagem de fundo decorativa.
- **Nunca:** sangrar essas imagens até a borda da tela nem aplicar blend mode nelas — são artefatos de design acabados, não fotos para fundir no fundo.

### Dica da Ana Ritter (`.dica`) — componente-assinatura
- **O que é:** painel preto com borda dourada, ícone de lâmpada em traço dourado, título tracked em caixa alta e corpo em creme. É o mesmo dispositivo que aparece dentro do ebook, trazido para a landing.
- **Uso:** no máximo uma ocorrência por página; é a voz da autora interrompendo, não um card de conteúdo.

### Marca de item (`.inclui`)
- **Style:** um traço dourado desenhado de 14×1px via `::before`, alinhado à baseline. Substitui bullets e travessões — o sistema não usa glifo Unicode como ícone.

### Citações de Autoridade
- **Style:** script dourado, isolado, sem aspas tipográficas grandes ao redor — o próprio traço da fonte já assina a citação. Sempre creditada logo abaixo, em label tracked.

## Do's and Don'ts

### Do:
- **Do** usar exatamente dois fundos (ivory / preto de ateliê) em toda a página.
- **Do** reservar o script dourado só para citações de autoridade e assinatura.
- **Do** manter o traço dourado fino como assinatura de marcas e molduras — nunca preenchimento de área grande.
- **Do** manter cantos retos em botões, cards e painéis.

### Don't:
- **Don't** usar preto puro (`#000`) ou branco puro (`#fff`) — sempre os tons de carvão/creme definidos acima.
- **Don't** usar sombras difusas (`box-shadow` ambient) — profundidade vem de contraste de cor e borda de 1px.
- **Don't** misturar o script dourado em corpo de texto ou botões — ele é só para voz de autoridade.
- **Don't** reintroduzir o roxo-azulado do Nocturne ou qualquer segundo acento de cor — o sistema é mono-acento dourado.
