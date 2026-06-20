# Franco Camargo Advocacia — Website Redesign

## What This Is

Design-only project for a Brazilian law firm website (Franco Camargo Advocacia e Consultoria Jurídica). The deliverable is visual design in HTML/CSS — not a production codebase. It will be handed off to a developer for implementation.

## Project Structure

```
francocamargo-site/
├── index.html              # Homepage
├── quem-somos.html         # About page
├── areas-de-atuacao.html   # Practice areas (PJ + PF sections)
├── equipe.html             # Team / attorney profiles
├── artigos.html            # Articles / blog listing
├── contato.html            # Contact form + office info
├── styles.css              # Shared design system + component styles
├── assets/
│   └── office.avif         # Hero office photo
├── docs/
│   ├── FC Advocia.md       # Content source of truth (PT-BR) — all copy, pages, nav, contact info
│   ├── Design.md           # Original design spec (colors, type, icons) — mutable except logo
│   ├── designlog.md        # Historical log of design iterations (see below)
│   └── logos/
│       ├── Logo_curvas.png
│       └── Logo_curvas.jpg
└── CLAUDE.md               # This file
```

## Source of Truth

- **Content:** `docs/FC Advocia.md` drives all copy, page structure, navigation, and contact info. This is the factual source — never invent content that contradicts it.
- **Logo:** Immutable. Two-tone monogram (burgundy `#7B2D2F` + charcoal `#4A4546`) with serif text. Do not alter.
- **Design.md:** Mutable reference. Colors, typography, elements, and visuals are all subject to change. If a decision conflicts with Design.md, surface it to the user rather than silently following either.

## Current Design State

### Colors (CSS custom properties in `styles.css :root`)
- Primary: `#7B2D2F` (logo burgundy)
- Primary light/dark: `#8f3d3f` / `#621d1f`
- Dark: `#241712` (warm chocolate-black — deeper than logo's charcoal)
- Cream/BG: `#F4ECE2` (warm cream)
- Accent: `#B98A5E` (gold — not from logo, editorial addition)
- Card BG: `#F7F1E8`

### Typography
- Display + Body: Montserrat (sans-serif for both)
- H1 Hero: 60px
- H2 Sections: 48px

### Layout
- Border radius: 16px / 20px (lg)
- Section padding: 160px 56px (generous)
- Shadows: soft preset
- Max width: 1320px

### Homepage Sections (in order)
1. Top bar (locations + phone + email)
2. Header (logo + nav + contact CTA)
3. Hero (headline, subtitle, location badge, CTA, office photo with arch frame)
4. Stats bar (21 anos, 99% sentenças favoráveis, 16 áreas, 2 escritórios)
5. Quem Somos intro (two-column with quote aside)
6. Áreas de Atuação (PJ/PF tab switcher, 3-col grid cards)
7. Inspirational quote band (dark background)
8. CTA section
9. Footer (4-column: brand, escritório links, áreas links, contato)

### Design Panel
The page includes an interactive side panel (gear icon, right edge) for live tweaking: fonts, colors, radius, spacing, shadows, section visibility. Has **Copy Parameters** / **Apply Pasted** buttons for sharing state as JSON between browser and Claude sessions.

## Pages — All Designed

All 6 pages are complete:
1. **Home** (`index.html`) — hero, stats, quem somos intro, áreas tabs, quote, CTA, footer
2. **Quem Somos** (`quem-somos.html`) — office presentation, philosophy, values grid, CTA
3. **Áreas de Atuação** (`areas-de-atuacao.html`) — separate PJ and PF sections with full card grids
4. **Equipe** (`equipe.html`) — featured profile (Solange) with full credentials + placeholder team grid
5. **Artigos** (`artigos.html`) — category filters + 6 sample article cards (placeholder content)
6. **Contato** (`contato.html`) — form, dual-office info with map placeholders, WhatsApp button

### Mobile / Responsive
All pages are fully responsive with 3 breakpoints (1024px, 768px, 480px). Hamburger menu on mobile. Design panel hidden on mobile. No inline style conflicts remaining.

### Pending / TBD Content
- Equipe: remaining team member names, photos, and areas (marked as placeholder cards)
- Artigos: real article content (currently sample/placeholder titles)
- Contato: Google Maps embeds (currently placeholder boxes)
- All pages: real photography (office, team portraits)
- Privacy policy and terms pages (linked in footer as TBD)

## Design Iteration Log

See `docs/designlog.md` for a chronological record of all design decisions and changes.

## Working With This Project

- All content is in Portuguese (Brazilian Portuguese).
- The design panel JSON is the fastest way to communicate visual state. User copies from browser, pastes into chat.
- When making color/type changes, update CSS custom properties in `:root` — the system is built on them.
- The `Co-Authored-By` trailer and `Generated with Claude Code` PR lines are not used in this project per user preference.
- This is a real codebase (git-tracked) — durable project context goes here in CLAUDE.md, not device-local memory.
