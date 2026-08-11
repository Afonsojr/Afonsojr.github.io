# AGENTS.md

## Overview

Single-page puzzle game "Sequence Breaker" hosted on **GitHub Pages**. No build tools, no dependencies.

## Structure

- `index.html` — single-file app (HTML + CSS + JS, ~2170 lines)
- `README.md` — game docs (Portuguese)

## How to work

- **Run locally:** open `index.html` in a browser directly (no server needed)
- **Deploy:** push to `main` → GitHub Pages serves from root automatically
- **No npm/pip/bundler** — edit HTML/JS/CSS inline
- **Hard refresh** (Ctrl+Shift+R) after edits; use private/incognito window to rule out `localStorage` corruption

## Key facts

- All game logic, rendering, and styles live in `index.html`
- `index.html` is the entrypoint (not `docs/`, not a subdirectory)
- Game UI strings are in **Portuguese (pt-BR)**
- Persistence: `localStorage` key `sequenceBreaker`
- 8 colors with distinct symbols: ◆ ● ▲ ■ ★ ♥ ✚ ⬢
- Game pieces use solid color fills (no patterns)
- Memorization phase: correct sequence shown for 2.5s at level start, then shuffled
- Victory auto-detected when all pieces are correct after a swap (no need to click "Verificar")
- Hints only highlight where pieces should go — swap is manual
- No tests, no lint, no CI
- Commits go directly to `main`

## Known pitfalls

- `const { hints } = levelConfig()` **redeclares `hints`** if used twice in the same function — use the first destructuring result, don't re-`const` it
- Restarting/resetting must reset `score` and `combo` to 0 (simple `level=1` is not enough)
- `showVictory` accuracy string: `(Math.round(...) || 100) + "%"` — wrong precedence without parens
