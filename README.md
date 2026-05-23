# Bertino Consulting Website

Professional website for Bertino Consulting, a content systems practice specializing in language infrastructure and AI-assisted content workflows.

## Live

Visit: [bertino.co](https://bertino.co)

---

## Stack

- **HTML5** — Semantic markup for accessibility and SEO
- **CSS3** — Custom design system with responsive layout
- **Google Fonts** — Inter typography
- **Schema.org** — Structured data for rich search results
- **GitHub Pages** — Fast, reliable hosting

---

## Structure

```
bertino-consulting/
├── index.html       # Main website file
├── styles.css       # All styling and responsive design
├── images/          # Hero photo, logo assets, OG image
├── .claude/         # Project slash commands (e.g. /design-review)
└── README.md        # This file
```

---

## Design system

### Colors

| Token | Value | Usage |
|---|---|---|
| Primary Blue | `#2E5CFF` | Links, interactive states, accent bars |
| Primary Hover | `#1A43CC` | Hover state for primary blue |
| Accent Coral | `#F2614A` | Decorative detail (footer arrow) |
| Dark Text | `#111111` | Body copy, headings, footer background |
| Secondary Text | `#6B6560` | Muted body copy, hero subtitle |
| Warm Background | `#FBF3EC` | Page background |
| Surface Tinted | `#F5EDE6` | Card backgrounds (callout) |
| Border | `#E8E0D8` | Section dividers |
| Footer Text | `#F5EDE6` | Footer headings and links |
| Footer Muted | `#9A938C` | Footer copyright text |

### Typography

- **All text:** Inter (Regular 400, Medium 500, Bold 700)
- Headings use tighter tracking (`letter-spacing: -0.02em`); body uses relaxed line height
- Section labels use uppercase 0.75rem with 0.1em letter spacing

### Spacing scale

Consistent 8px base unit: `8px, 16px, 24px, 32px, 48px, 64px, 96px`

### Shape & shadow

- **Border radius:** `6px` (sm), `12px` (default), `20px` (lg)
- **Shadows:** `--shadow-sm`, `--shadow-md` available for elevated elements

### Motion

- **Durations:** `150ms` (fast), `200ms` (base), `300ms` (slow)
- **Easing:** `cubic-bezier(0.16, 1, 0.3, 1)` (ease-out spring)
- All animations respect `prefers-reduced-motion`

---

## SEO and performance

- Schema.org structured data (`Person` + `Organization`)
- Open Graph tags for social media sharing
- AI crawler permissions (GPTBot, Claude-Web)
- Mobile-responsive design
- Semantic HTML for accessibility
- Optimized meta tags
- Fast loading (no frameworks, no build step)

---

## Responsive design

Fully responsive with breakpoints at:

- **Mobile:** < 768px
- **Tablet:** 768px – 1024px
- **Desktop:** > 1024px

---

## Local development

1. Clone this repository
2. Open `index.html` in your browser
3. That's it — no build process needed.

---

## License

© 2026 Bertino Consulting AB. All rights reserved.

---

## Contact

Joe Bertino — [joe@bertino.co](mailto:joe@bertino.co)

> This is a static website built with vanilla HTML and CSS for optimal performance and simplicity.
