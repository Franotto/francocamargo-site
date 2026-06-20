# Franco Camargo Advocacia — Website Design

Design prototype for **Franco Camargo Advocacia e Consultoria Jurídica**, a law firm based in São Paulo (Santana) and Taubaté.

**Live preview:** https://franotto.github.io/francocamargo-site/

## Pages

| Page | File | Description |
|------|------|-------------|
| Home | `index.html` | Hero, stats, about intro, practice areas, philosophy, CTA |
| Quem Somos | `quem-somos.html` | Office presentation, philosophy, values |
| Áreas de Atuação | `areas-de-atuacao.html` | Practice areas for businesses (PJ) and individuals (PF) |
| Equipe | `equipe.html` | Attorney profiles |
| Artigos | `artigos.html` | Blog / articles listing |
| Contato | `contato.html` | Contact form, office addresses, WhatsApp |

## Tech

- Static HTML + CSS (no build tools, no frameworks)
- Single shared stylesheet: `styles.css`
- CSS custom properties for colors, typography, spacing, and shape
- Responsive: 3 breakpoints (1024px, 768px, 480px) with hamburger menu on mobile
- Google Fonts: Montserrat

## Design System

| Token | Value |
|-------|-------|
| Primary | `#7B2D2F` |
| Dark | `#241712` |
| Background | `#F4ECE2` |
| Accent | `#B98A5E` |
| Font | Montserrat |
| Radius | 16px |

## Project Structure

```
├── index.html, quem-somos.html, areas-de-atuacao.html,
│   equipe.html, artigos.html, contato.html
├── styles.css
├── assets/
│   └── office.avif
└── docs/
    ├── FC Advocia.md       # Content source of truth (PT-BR)
    ├── Design.md           # Design spec reference
    ├── designlog.md        # Design iteration history
    └── logos/
```

## Notes for Developer

- This is a **design deliverable**, not a production codebase. Implement in your framework of choice.
- All content is in Brazilian Portuguese.
- The homepage includes an interactive **design panel** (gear icon, right edge) for tweaking typography, colors, spacing, and section visibility live. It's a design tool, not a production feature.
- Placeholder content exists for: team member cards, article content, Google Maps embeds, and photography.
