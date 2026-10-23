# StyleKit Design Styles

## Overview

Style catalog and component-borrowing workflow for the `stylekit` project located at `C:\Belousov\Projects\stylekit` (GitHub: https://github.com/d1m40fficial/stylekit).

9 styles with design tokens, CSS variables, Tailwind presets, rules, and a web cheat sheet with live demos: https://d1m40fficial.github.io/stylekit/

## Style catalog (numbered — canonical order used by the cheat sheet)

| # | ID | EN name | RU name | Identity |
|---|----|---------|---------|----------|
| 1 | hand-drawn-doodle | Hand-Drawn Doodle | Развёрнутый дудл | notebook paper, dashed borders, hard offset marker shadows, stop-motion jitter |
| 2 | parallax-sections | Parallax Sections | Параллакс-секции | bg-attachment fixed, full-screen sections, scroll depth, cinematic 500/700ms |
| 3 | shader-gradient | Shader Gradient | Шейдерный градиент | real WebGL fbm mesh gradient, near-black canvas, frosted glass panels, Stripe/Linear look |
| 4 | apple-liquid-glass | Apple Liquid Glass | Жидкое стекло | heavy backdrop-blur[40px]+saturate, rainbow halo borders, 24px corners, gradient+stroke titles |
| 5 | paper-craft | Paper Craft | Бумажные ремёсла | layered papercut cards, soft offset shadows, warm cream bg, layer separation on hover |
| 6 | bento-grid | Bento Grid | Бенто-сетка | irregular CSS-grid cards, mixed spans, rounded-2xl, hover lift + shadow bloom |
| 7 | fullscreen-hero | Fullscreen Hero | Полноэкранный герой | 100vh image/video background, dark overlay, white text, gravity-float CTA |
| 8 | dopamine-design | Dopamine Design | Дофаминовый дизайн | neon-high-saturation palette, pill buttons, colored shadows, font-black headings |
| 9 | full-page-scroll | Full Page Scroll | Полноэкранный скролл | 100vh snap scenes, scroll reveal, capsule nav dots, one accent per scene |

## Data sources (read these, in this priority)

1. `stylekit/tokens/<id>.css` — CSS custom properties (`--color-primary`, `--color-accent-1`...)
2. `stylekit/tokens/<id>.tokens.json` — Tokens-Studio token files (colors, typography, spacing, radius, shadows)
3. `stylekit/tokens/<id>.tailwind.preset.js` — Tailwind v3 theme preset
4. `stylekit/DESIGN_SPEC.md` — full per-style spec: token table, "Never use", "Do", "Don't", animations (bilingual EN/RU)
5. `stylekit/AI_PROMPT.md` — merged system prompt (base style + accent styles), bilingual

## Resolving user references

Users speak Russian and reference styles loosely. Map every phrasing to the catalog:

- By exact name / id: «возьми тему как в "Liquid Glass"» → style 4 (id `apple-liquid-glass`)
- By number: «стиль кнопок из второго стиля / из 2» → catalog row #2 (`parallax-sections`)
- By subject: «анимацию скролла из 4» → the *scroll/parallax feature* lives in style 2 (`parallax-sections`); if the user names a different number, take that style's tokens but implement its motion from its spec section
- If ambiguous between a name fragment matching multiple styles (e.g. «стекло», «градиент», «бумага»), confirm with the user listing the 2 candidates with numbers and names before building

## Workflows

### A) Apply a full theme («возьми тему как в X»)

1. Read the style's block in `DESIGN_SPEC.md` (token table + Do/Don't).
2. Wire tokens: import `<id>.tokens.json` or connect `<id>.tailwind.preset.js` or paste `<id>.css` `:root` vars into globals.
3. Apply shared utility-dial values: border, radius, shadow (md + hover), heading/body font classes, type scale, spacing, gap, transition, active state — all from the token table.
4. Enforce the style's **Never use** list — grep the target codebase (and your generated code) and fix violations first.
5. Follow the style's **Do** list for signature elements (see Identity column above).

### B) Borrow a single element («кнопки/карточки/анимация скролла/панели/hero из X»)

Keep the project's own base theme. Graft only the requested element:

1. Locate the donor style in `DESIGN_SPEC.md`; copy the element's classes (buttons: border/radius/shadow/transition/active; cards: bg/border/radius/shadow shadow-lift; scroll: `bg-fixed`, full-screen sections, sticky overlays; glass: `backdrop-blur-[40px]` etc.)
2. Export as a self-contained CSS component (`.el-<donor>-btn`...) with donor hex values hardcoded — do not inject donor CSS variables into the project globals (token collision).
3. If the element depends on hidden context (e.g. Fullscreen Hero buttons depend on dark overlays; Parallax buttons need fixed bg behind), pull that context too or re-tune contrast explicitly.
4. Check conflicts: run the donor's **Never use** list against the host theme. If the host theme forbids what the element requires (e.g. hard offset shadow from Doodle into Bento's soft `shadow-md` world), prefer the donor values, scoped to the component, and note the deviation to the user.

### C) Merge styles (base + accent)

Follow `AI_PROMPT.md` pattern: base style is dominant; accent style applies only to highlighted sections / standout components. Never blend properties that contradict either style's Never-use list; when contradiction is unavoidable, the base style wins and the accent survives only in composition (layout/subject), not in shared tokens.

## Component-to-style affinity (which style to pick when the user only describes the effect)

| User asks for | Source style |
|---|---|
| scroll animation, parallax depth, sticky sections | 2 Parallax Sections |
| full-page snap scenes, scroll reveal, scroll storytelling | 9 Full Page Scroll |
| living/animated gradient background | 3 Shader Gradient |
| frosted glass panels, blur cards | 3 (dark) / 4 (Apple) Liquid Glass |
| handcraft/paper/layered cards | 5 Paper Craft |
| irregular feature grid | 6 Bento Grid |
| fullscreen image/video intro CTA | 7 Fullscreen Hero |
| neon playful buttons/badges | 8 Dopamine Design |
| sketchy decorations, tape/notes | 1 Hand-Drawn Doodle |
| hard offset shadows | 1 Hand-Drawn Doodle (or `brutal` variant in tokens) |

## Copy-ready prompt phrases (answers for the user)

- Theme: «Возьми тему как в «<name>» (stylekit, стиль #<n>)»
- Buttons: «Возьми стиль кнопок из «<name>» (stylekit, стиль #<n>)»
- Cards: «Возьми стиль карточек из «<name>» (stylekit, стиль #<n>)»
- Scroll: «Возьми анимацию скролла / параллакс из «<name>» (stylekit, стиль #<n>)»
- Palette: «Возьми палитру из «<name>» (stylekit, стиль #<n>)»
- Glass panels: «Возьми стеклянные панели из «<name>» (stylekit, стиль #<n>)»
- Hero: «Возьми шапку/hero как в «<name>» (stylekit, стиль #<n>)»

## Cheat sheet

Live demos, per-style tabs, copy-phrase buttons, palette swatches, Do/Don't lists:
https://d1m40fficial.github.io/stylekit/
