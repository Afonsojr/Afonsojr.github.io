---
name: O Código da Tonalização
description: Guia de colorimetria para tonalização — identidade luxo de brand book, preto e dourado sobre ivory.
colors:
  ink: "#121110"
  ivory: "#F2ECE0"
  ivory-paper: "#FAF7F0"
  gold: "#C9A24B"
  gold-deep: "#7D6225"
  cream: "#F4EEE1"
  charcoal: "#1C1A17"
typography:
  display:
    fontFamily: "Playfair Display, Georgia, serif"
    fontSize: "clamp(2.5rem, 4.4vw, 3.6rem)"
    fontWeight: 700
    letterSpacing: "0.005em"
    lineHeight: 1.05
  headline:
    fontFamily: "Playfair Display, Georgia, serif"
    fontSize: "clamp(1.9rem, 3vw, 2.3rem)"
    fontWeight: 700
    letterSpacing: "0.005em"
    lineHeight: 1.05
  script:
    fontFamily: "Alex Brush, cursive"
    fontSize: "1.6rem"
    fontWeight: 400
    lineHeight: 1.3
  title:
    fontFamily: "Jost, system-ui, sans-serif"
    fontSize: "1.1rem"
    fontWeight: 600
  label:
    fontFamily: "Jost, system-ui, sans-serif"
    fontSize: "0.74rem"
    letterSpacing: "0.18em"
    fontWeight: 600
  body:
    fontFamily: "Jost, system-ui, sans-serif"
    fontSize: "1rem"
    fontWeight: 400
    lineHeight: 1.6
rounded:
  none: "0px"
  sm: "2px"
spacing:
  sp-1: "6px"
  sp-2: "10px"
  sp-3: "16px"
  sp-4: "24px"
  sp-6: "40px"
  sp-8: "64px"
components:
  button-gold:
    backgroundColor: "transparent"
    textColor: "{colors.gold}"
    rounded: "{rounded.sm}"
    padding: "16px 40px"
  button-gold-hover:
    backgroundColor: "{colors.gold}"
    textColor: "{colors.ink}"
  button-gold-ivory:
    backgroundColor: "transparent"
    textColor: "{colors.gold-deep}"
    rounded: "{rounded.sm}"
    padding: "16px 40px"
  button-gold-ivory-hover:
    backgroundColor: "{colors.gold-deep}"
    textColor: "{colors.ivory-paper}"
  panel-ink:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.cream}"
    padding: "64px"
  offer-card:
    backgroundColor: "{colors.ivory-paper}"
    textColor: "{colors.charcoal}"
    padding: "40px"
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

Paleta de dois fundos (ivory / quase-preto) com um único acento dourado — mono-acento, como o Nocturne que substitui, mas quente em vez de frio. Os valores vivem no frontmatter (`colors`) e nos tokens `--color-*` do `index.html`; a prosa abaixo só descreve o papel de cada um.

### Primary
- **Dourado de Ateliê** (`#C9A24B`, `gold`): acento único — traços e filetes, bordas de botão, moldura de placa e card, ícones de linha, aspas e assinatura em script. Sobre o preto de ateliê passa 7.86:1. Sobre o ivory passa só 2.04:1, então nunca usar para texto ou contorno essencial nesse fundo.
- **Dourado Profundo** (`#7D6225`, `gold-deep`): o passo para texto, botão e contorno sobre ivory. Mantém 4.9:1 sobre o Ivory de Mat e 5.38:1 sobre o Papel Ivory (WCAG AA).

### Neutral
- **Preto de Ateliê** (`#121110`, `ink`): fundo dos painéis internos (hero, capítulos, cards de destaque) — nunca preto puro CSS (`#000`).
- **Ivory de Mat** (`#F2ECE0`, `ivory`): fundo da página fora dos painéis — a moldura que dá respiro aos blocos pretos.
- **Papel Ivory** (`#FAF7F0`, `ivory-paper`): variante mais clara do ivory, usada no card de oferta e em superfícies claras elevadas sobre o mat.
- **Creme sobre Preto** (`#F4EEE1`, `cream`): texto e título dentro dos painéis pretos — nunca branco puro.
- **Carvão sobre Ivory** (`#1C1A17`, `charcoal`): texto de corpo sobre ivory — nunca preto puro.

### Named Rules
**The Two-Ground Rule.** Toda a página vive entre exatamente dois fundos — ivory por fora, quase-preto por dentro dos painéis. Nunca um terceiro tom de fundo neutro por variedade.

> **Divergência em aberto:** o código tem duas exceções a esta regra. (1) A faixa de estatística é full-bleed preta, com filetes dourados em cima e embaixo. (2) O card de oferta usa Papel Ivory como terceiro tom. A regra ou o código ainda precisa ser escolhido; até lá, nenhuma nova exceção.

## Typography

**Display Font:** Playfair Display (ou serifada de alto contraste equivalente), com Georgia como fallback.
**Script Font:** Alex Brush, para citações da autora e assinatura (Great Vibes não está carregado).
**Body/Label Font:** Jost.

**Character:** Uma serifada editorial de alto contraste para autoridade e escala, contra um sans neutro e discretamente tracked para o texto funcional — a mesma tensão "manuscrito de mestre / ficha técnica" que o brand book carimba em cada página.

### Hierarchy
- **Display** (700, `clamp(2.5rem, 4.4vw, 3.6rem)`, line-height 1.05, caixa alta, `max-width: 14ch`): título do hero. Só no topo da página.
- **Headline** (700, `clamp(1.9rem, 3vw, 2.3rem)`, line-height 1.05, caixa alta): títulos de seção, como "Perguntas frequentes" e a chamada da oferta. Alguns blocos usam `clamp(1.6rem–2.1rem)` com o mesmo papel; não criar um quarto tamanho.
- **Script accent** (400, 1.6rem, line-height 1.3): citação da Ana Ritter e assinatura no rodapé. Nunca mais de uma ocorrência por seção.
- **Title** (600, 1.1rem, Jost): título de item de lista e FAQ, sem caixa alta.
- **Label** (600, 0.74rem, letter-spacing 0.18em, caixa alta): título da Dica e crédito de citação — só texto curto; frase inteira (como a legenda de placa) fica em sentence case. Sempre **depois** ou **dentro** do bloco que qualifica, nunca acima de um título.
- **Body** (400, 1rem, line-height 1.6): parágrafos explicativos, largura de leitura de 60–70ch (`.prose`). O lede do hero usa 1.1rem e 52ch.

### Named Rules
**The No-Eyebrow Rule.** Nenhum label decorativo acima de um título. O título carrega o próprio peso; se ele precisa de uma etiqueta em cima para fazer sentido, o título é que está fraco. (A landing usava "Capítulo 1 · O problema" como eyebrow — era fantasia: a página de vendas não tem capítulos, o ebook é que tem.)

**The Drawn-Mark Rule.** Marcas e bullets são desenhadas (traço dourado via `::before`, SVG em traço), nunca um glifo Unicode — travessão, seta ou emoji fazendo papel de ícone.

## Layout

Layout assimétrico, alinhado à esquerda: títulos flush-left, conteúdo colado na margem esquerda com respiro à direita — o brand book usa a mesma lógica com o texto sempre à esquerda do retrato.

- **Container:** `.wrap` com `max-width: 1120px`, centralizado, padding lateral de 24px.
- **Painéis:** painéis pretos ocupam a largura da seção (o "documento dentro da página"), com margem ivory ao redor. Dentro deles, o padding segue o ritmo de espaçamento: 64px no desktop, 40px no tablet, 24px no celular.
- **Grades:** 2 colunas assimétricas (1.1fr / 0.9fr, 0.85fr / 1.15fr e similares) e 3 colunas iguais na faixa de estatística. Em `max-width: 860px` todas colapsam para 1 coluna.
- **Ritmo vertical:** cada seção usa 64px acima e abaixo (`sp-8`).
- **Faixa de estatística:** única seção full-bleed escura. Fundo preto, filetes dourados de 1px em cima e embaixo. Não usar outra faixa full-bleed como ela.
- **Barra de compra:** só no celular (até 860px), fixa embaixo, preta com filete dourado no topo. Aparece quando o botão do hero e o da oferta saem da tela; some quando um deles está visível, para não haver dois CTAs disputando o mesmo olhar.

## Elevation & Depth

Sem sombras difusas. A profundidade vem do contraste ivory/preto entre camadas e de uma borda/linha dourada fina como aresta — o brand book não usa nenhum drop-shadow, só blocos de cor nítidos com bordas finas. Nenhum `box-shadow` foi encontrado no `index.html`.

### Named Rules
**The Hard-Edge Rule.** Elevação é contraste de cor e uma borda de 1px, nunca `box-shadow` difuso.

## Shapes

Cantos retos ou quase retos. Botões usam `border-radius: 2px` (`rounded.sm`); tags, painéis e placas usam 0px (`rounded.none`). Bordas finas de 1px em dourado definem os limites dos painéis pretos e das placas contra o mat ivory.

## Components

### Buttons
- **Shape:** `border-radius: 2px`, `min-height: 44px`, texto em caixa alta, 0.92rem, peso 600, letter-spacing 0.03em.
- **Primary (`.btn-gold`):** fundo transparente, borda 1px dourada, texto dourado, padding 16px 40px. Usado sobre painel preto (hero, método, oferta, CTA final). No hover, preenche de dourado sólido com texto preto — inversão de contraste, não tint.
- **Ivory (`.btn-gold-ivory`):** o mesmo desenho com Dourado Profundo. Usado sobre ivory (nav e card de oferta). No hover, preenche de dourado profundo com texto Papel Ivory. Largura total (`.btn-block`) no card de oferta.
- **Foco:** contorno de 2px com 2px de offset — dourado profundo sobre ivory, dourado sobre preto.
- **Secondary / Ghost:** não existem no sistema. Não criar sem decisão explícita.

### Painéis (`.panel-ink`)
- **Corner Style:** reto (0px).
- **Background:** Preto de Ateliê (`ink`), texto em Creme (`cream`).
- **Border:** 1px dourado. Sem etiqueta na moldura.
- **Internal Padding:** `sp-8` (64px) no desktop, `sp-6` (40px) até 860px, `sp-4` (24px) até 480px.

### Card de oferta (`.offer-card`)
- **Background:** Papel Ivory (`ivory-paper`), borda 1px dourada, texto em Carvão (`charcoal`). Preço em Display com Dourado Profundo.
- **Padding:** `sp-6` (40px), `sp-4` (24px) no celular.
- **Nota:** é o único card claro. Ver a divergência em Named Rules de Colors.

### Placa de Material (`.plate`) — componente-assinatura
- **O que é:** a moldura em que páginas reais do ebook entram na landing: borda 1px dourada, fundo preto de ateliê, imagem a 100% de largura, legenda em sentence case abaixo, 0.86rem (`.plate-cap`).
- **Por quê:** a página prova o produto mostrando o próprio material. A moldura faz a página lida como artefato citado, não como imagem de fundo decorativa.
- **Nunca:** sangrar essas imagens até a borda da tela nem aplicar blend mode nelas — são artefatos de design acabados, não fotos para fundir no fundo.
- **Selo (`.selo`):** sobreposição centralizada sobre a tabela de receitas, com ícone de cadeado em traço dourado e texto em dourado. O borrão das fórmulas está gravado no próprio JPEG, não em CSS.

### Dica da Ana Ritter (`.dica`) — componente-assinatura
- **O que é:** painel preto com borda dourada, ícone de lâmpada em traço dourado (40px), título tracked em caixa alta e corpo em creme. É o mesmo dispositivo que aparece dentro do ebook, trazido para a landing.
- **Uso:** no máximo uma ocorrência por página; é a voz da autora interrompendo, não um card de conteúdo.

### Marca de item (`.inclui`)
- **Style:** um traço dourado desenhado de 14×1px via `::before`, alinhado à baseline. Substitui bullets e travessões — o sistema não usa glifo Unicode como ícone.

### Tag (`.tag`)
- **Style:** contorno de 1px em dourado profundo, caixa alta, 0.72rem, letter-spacing 0.1em, peso 600, padding 6px 14px, sem arredondamento.
- **Variante `.muted`:** contorno e texto em carvão a 30% e 65%, para o lado "não é pra você".

### Itens e listas (`.item`)
- **Style:** blocos separados por filete de 1px em carvão a 12%, padding vertical de 24px. Título em `title`, descrição em carvão a 65% com largura máxima de 60ch.

### Citações de Autoridade
- **Style:** script dourado, isolado, sem aspas tipográficas grandes ao redor — o próprio traço da fonte já assina a citação. Sempre creditada logo abaixo, em label tracked.

### Reveal (motion)
- **Único momento de motion:** as placas de material entram uma vez, com fade e deslizamento de 18px, em 0.6s com `cubic-bezier(0.16, 1, 0.3, 1)`, com atraso de 0.12s no segundo item. Só com `prefers-reduced-motion: no-preference`. Sem JS, nada some.
- **Barra de compra:** desliza em 0.3s ease. Sem animação com reduced motion.

## Do's and Don'ts

### Do:
- **Do** usar exatamente dois fundos (ivory / preto de ateliê) em toda a página, salvo as exceções registradas em Named Rules.
- **Do** reservar o script dourado só para citações de autoridade e assinatura.
- **Do** manter o traço dourado fino como assinatura de marcas e molduras — nunca preenchimento de área grande.
- **Do** manter cantos retos ou de 2px em botões, cards e painéis.
- **Do** usar Dourado Profundo para texto, botão e contorno sobre ivory.

### Don't:
- **Don't** usar preto puro (`#000`) ou branco puro (`#fff`) — sempre os tons de carvão/creme definidos acima.
- **Don't** usar sombras difusas (`box-shadow` ambient) — profundidade vem de contraste de cor e borda de 1px.
- **Don't** misturar o script dourado em corpo de texto ou botões — ele é só para voz de autoridade.
- **Don't** usar dourado claro (`gold`) como texto ou contorno essencial sobre ivory (2.04:1).
- **Don't** reintroduzir o roxo-azulado do Nocturne ou qualquer segundo acento de cor — o sistema é mono-acento dourado.
- **Don't** adicionar uma segunda faixa full-bleed escura além da faixa de estatística.
- **Don't** colocar hex direto no HTML ou no CSS da página. Usar `var(--color-*)`, inclusive nos atributos `stroke` dos ícones SVG.
