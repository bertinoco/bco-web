Review the current state of `index.html` and `styles.css` against the design system defined in `CLAUDE.md`. Evaluate the following areas and report findings as a prioritized list of issues (Critical → Minor):

## What to check

### Layout & proportion
- Do section grids feel balanced? Check label column vs body column ratios.
- Are nested grids (e.g. services 2×2 inside a section) getting enough width?
- Is vertical rhythm consistent? Sections should breathe but not feel disconnected.

### Typography
- Are font sizes, weights, and line-heights from the design system being applied correctly?
- Is the type hierarchy clear (H1 → H2 → H3 → body → label)?
- Do max-width constraints on headings (`max-width: 16ch`, `60ch`) look correct at desktop size?

### Color & contrast
- Are CSS custom properties used — no hardcoded hex values except in `:root`?
- Do muted text colors (`#555555`) have sufficient contrast on the `#FAFAFA` background?

### Spacing
- Is the 8px scale respected? Flag any ad-hoc pixel values that don't fit the scale.
- Are section padding values (`--space-12`) consistent across all sections?

### Border & visual separation
- Do section dividers (`border-top`) clash with element-level borders inside sections?
- Do card treatments feel intentional (not doubled or redundant)?

### Responsive behavior
- Are the 768px breakpoint overrides complete? Check section-grid, services-grid, clients-grid, footer-bottom.
- Does anything break or overflow at 375px viewport width?

### Semantic HTML
- Are all sections using the correct landmark elements (`<nav>`, `<main>`, `<section>`, `<footer>`, `<article>`)?
- Do `aria-labelledby` attributes point to valid `id`s?

### Design system adherence
- Are `--radius: 12px`, `--max-width: 960px`, and the spacing scale applied consistently?
- Does any element use inline styles or non-system values?

## Output format
Return a prioritized list:
- **Critical** — broken layout, missing content, accessibility failures
- **Significant** — noticeable visual inconsistency or proportion problem
- **Minor** — small polish items, spacing tweaks, code cleanliness

End with 2–3 specific, actionable fix suggestions for the highest-priority issues.
