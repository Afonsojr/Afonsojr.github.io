# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## O que é este projeto

Uma única landing page de vendas (`Pagina de Vendas - Codigo da Tonalizacao.dc.html`) para o ebook "O Código da Tonalização", construída na ferramenta de design **omelette** — não é um projeto de software com build/lint/test tradicionais. Não há package.json, build step ou test runner; o arquivo `.dc.html` é editado diretamente e renderizado pelo runtime da omelette (via `support.js`).

- `uploads/O Codigo da Tonalizacao.pdf` — o ebook vendido na página; `uploads/tonalizacao-text.txt` é uma extração de texto bruta do PDF (índice/página por página).
- `support.js` e `image-slot.js` são infraestrutura vendorizada da omelette — não editar por engano ao mexer no conteúdo da página. `image-slot.js` implementa o componente `<image-slot>`, um placeholder de imagem preenchível pelo usuário (drag & drop), persistido via um sidecar `.image-slots.state.json` na mesma pasta do HTML.
- `_ds/nocturne-.../` é o design system "Nocturne" vendorizado (tema dark, roxo-azulado). Contém `styles.css` (única folha de estilo — tokens + componentes), `theme.json` (origem dos tokens) e `readme.md` com a documentação completa do sistema.

## Regras de estilo ao editar a página

Seguir estritamente as convenções do Nocturne (detalhadas em `_ds/nocturne-.../readme.md`):

- **Nunca hard-codar** cor (hex), fonte ou valor em px que os tokens já cobrem — sempre usar `var(--color-*)`, `var(--font-*)`, `var(--space-*)`, `var(--radius-*)`, `var(--shadow-*)`.
- Usar as classes já existentes em `styles.css` (`.btn`, `.tag`, `.field`, `.card`, `.nav`, `.table`, `.dialog`, `.lighten`) em vez de inventar classes paralelas.
- Botões primários são outline (borda 1px de accent, sem preenchimento sólido) — nunca preenchidos.
- Layout assimétrico alinhado à esquerda; títulos flush-left, conteúdo colado na margem esquerda com espaço em branco à direita.
- Imagens de conteúdo (hero, fotos inline) sempre envoltas em `.lighten` (usa `mix-blend-mode: lighten`) — preferir fotos com fundo escuro/preto.
- Não usar preto ou branco puro; tudo vem das rampas tonais (`--color-neutral-*`, `--color-accent-*`).
- Accent nunca em áreas grandes/flood — exceção é a faixa de estatística full-bleed (`--color-section`) já existente na página.
- Estados interativos (`:hover`, `:focus-visible`) devem vir do tema, nunca do default do browser — já implementados nas classes `.btn`/`.field` etc., não restilizar por página.
- Ícones: Phosphor Icons (https://phosphoricons.com).

## Estrutura da página atual

`Pagina de Vendas - Codigo da Tonalizacao.dc.html` segue o padrão `templates/landing/` do Nocturne: `<x-dc>` → `<helmet>` (link do `styles.css`, script do `_ds_bundle.js`, script do `image-slot.js`, estilos inline específicos da página) → seções dentro de `.wrap` (nav, hero, e demais blocos de vendas — benefícios, prova social, oferta em `#oferta`).

Para editar cores/tipografia/espaçamento globalmente, mudar os tokens no topo de `_ds/nocturne-.../styles.css` (mantendo `theme.json` em sincronia, conforme instruído no readme do design system) — não sobrescrever com valores inline na página.
