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

### Status at End of Session 1

- Homepage design is in a good state.
- 5 inner pages remain: Quem Somos, Áreas de Atuação, Equipe, Artigos, Contato.
- Project is now git-tracked.

---

## Session 1 (continued) — 2026-06-20

### All Inner Pages Designed

Added shared inner-page CSS to `styles.css` (page hero banner, content sections, two-column layouts, values grid, profile cards, team grid, article cards, contact form, map placeholders, WhatsApp button).

#### Quem Somos (`quem-somos.html`)
- Page hero with breadcrumb, title, subtitle
- Two-column layout: office presentation text + philosophy quote aside
- Centered philosophy section on alt background
- 5-column values grid (Ética, Cidadania, Confiança, Pessoalidade, Responsabilidade) with icon circles using first letter
- Discrete CTA closing

#### Áreas de Atuação (`areas-de-atuacao.html`)
- Intro paragraph about strategic partnership
- Separate PJ and PF sections (no tabs — each gets its own full section with heading)
- PJ: 9 area cards in 3-column grid, last card (Projetos Sociais) in accent style
- PF: 7 area cards, last card (Previdenciário) in accent style
- CTA: "Não encontrou exatamente o que procura?"

#### Equipe (`equipe.html`)
- Featured profile: Solange Pereira Franco de Camargo with full credentials and courses from content doc
- Photo placeholder (aspect-ratio 3:4)
- Two credential sections: Formação e Credenciais + Cursos Extracurriculares with styled bullet lists
- 3-card placeholder grid for additional team members (TBD content)
- No CTA per content doc guidance (trust-building page)

#### Artigos (`artigos.html`)
- Category filter buttons (Todos, Tributário, Trabalhista, Civil, Família, Consumidor, Previdenciário)
- 6 sample article cards in 3-column grid, each with:
  - Image placeholder
  - Category tag + date
  - Title, summary, "Ler mais" link
- Sample titles are topically relevant to FC's practice areas (not real articles)

#### Contato (`contato.html`)
- Full contact form: nome, email, telefone, assunto (dropdown with all 15 practice areas + Outro), mensagem, submit button
- Dual-office info blocks (São Paulo Santana + Taubaté) with addresses, phones, map placeholders
- Email + social media links (Instagram, Facebook)
- WhatsApp button with SVG icon, links to wa.me/5511910391001

### Cross-Page Updates
- Updated all navigation links across all pages (header nav + footer) to point to actual HTML files
- Updated index.html header and footer links from `#` to real page filenames
- Consistent header/footer/top-bar across all pages

### Status
- All 6 pages designed and linked.
- Awaiting user review for design feedback.
- TBD: real team member data, real article content, Google Maps embeds, photography.

---

## Session 1 (continued) — 2026-06-20 — Mobile Optimization

### Responsive CSS Added

Added three breakpoint layers to `styles.css`:

#### Tablet (≤1024px)
- Section padding reduced to 100px/32px
- Hero goes single-column, h1 to 48px
- Stats grid: 2×2, numbers to 48px
- Intro, CTA, page hero layouts: single-column
- Areas grid: 2 columns
- Footer: 2-column grid
- Values: 3 columns, profiles single-column, team/articles: 2 columns
- Contact layout: single-column

#### Mobile (≤768px)
- Padding reduced to 72px/20px
- **Hamburger menu**: 3-bar toggle replaces desktop nav, slides down as full-width dropdown. "Contato" CTA button hidden (available as nav link instead).
- Hero: h1 30→36px, arch frame hidden, image uses standard radius
- Stats: 2×2 with right-border on odd items for visual separation
- All grids collapse to single-column
- Quote aside: smaller padding, 22px font
- Inspiration: 26px quote
- CTA button: full-width
- Footer: single-column, centered bottom links
- Design panel: hidden entirely on mobile
- Contact: full-width form submit, smaller map height
- Values: 2 columns
- Team/articles: single-column

#### Small Mobile (≤480px)
- Top bar stacks vertically
- Hero h1: 30px, image goes 1:1
- Stats numbers: 34px
- Values: single-column
- Quotes: 20-22px
- All headings: 28px floor

### HTML Changes (all 6 pages)
- Added hamburger menu button (`<button class="mobile-menu-toggle">`) before nav in all page headers
- Added "Contato" link inside mobile nav dropdown (since CTA button hides on mobile)
- Converted inline `font-size:48px` on `areas-de-atuacao.html` h2 elements to `.section-heading` class (inline styles block media queries)

### Status
- Mobile optimization complete across all 6 pages.
- Awaiting user review.
