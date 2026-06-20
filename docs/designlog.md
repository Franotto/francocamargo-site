# Design Log — Franco Camargo Advocacia

Chronological record of design decisions and iterations. Referenced from `CLAUDE.md`.

---

## Session 1 — 2026-06-20

### Initial Setup

- Chose HTML/CSS over Figma MCP for design work — better token efficiency and pixel-level control for a design-only deliverable.
- Created `styles.css` (design system with CSS custom properties) and `index.html` (homepage).
- Built initial homepage based on a Claude Design reference artifact (`docs/reference-artifact/reference.html`) — an editorial law firm template ("Hale & Wren") with warm dark tones, serif display type, and configurable props.
- Replaced all placeholder content with real copy from `docs/FC Advocia.md` (Portuguese).

### Design Panel

- Added an interactive side panel for live design tweaking (typography, colors, radius, spacing, shadows, section toggles).
- Added **Copy Parameters** / **Apply Pasted** buttons so the user can export panel state as JSON and paste it into chat — solves the problem of Claude not being able to access `file://` URLs in Chrome.

### Color & Typography Decisions

- **Conflict surfaced:** `Design.md` specified Montserrat + cool off-white (`#F9F9F9`) + burgundy `#742C2D`. Reference artifact used warm cream (`#F4ECE2`) + serif display fonts + chocolate dark (`#241712`). Design.md is mutable, so leaned toward the warmer editorial direction.
- **User's first parameter set:** Montserrat for both display and body, 60px H1, 48px H2, 16px radius, generous spacing. Locked these as defaults.
- **Logo header:** bumped from 48px to 64px height.
- **Top bar:** replaced "Fale com a gente" with actual email `contato@francocamargo.adv.br`.

### Color Testing

- **Tested logo-matched palette:** swapped all colors to match the logo exactly (charcoal `#4A4546` for darks, neutral off-white `#F4F2F0`, no gold accent). Result was too flat/muted — the editorial warmth was lost.
- **Reverted** to the warm editorial palette but kept the logo's exact burgundy (`#7B2D2F`) as primary. The warm cream BG, chocolate-black darks, and gold accent (`#B98A5E`) stayed.
- **Final primary:** `#7B2D2F` (logo-matched), with derived light `#8f3d3f` and dark `#621d1f`.

### Content & Layout

- Added office photo (`assets/office.avif`) to hero section.
- Added **stats section** between hero and Quem Somos intro:
  - 21 — Anos de atuação
  - 99% — Sentenças favoráveis
  - 16 — Áreas do Direito
  - 2 — Escritórios em São Paulo
- Removed hero badge (founding year) since that info moved to stats.
- Homepage sections finalized in order: top bar → header → hero → stats → quem somos intro → áreas de atuação (PJ/PF tabs) → inspirational quote → CTA → footer.

### Status at End of Session

- Homepage design is in a good state.
- 5 inner pages remain: Quem Somos, Áreas de Atuação, Equipe, Artigos, Contato.
- Project is now git-tracked.
