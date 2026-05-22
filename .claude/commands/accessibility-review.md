Review `index.html` and `styles.css` for accessibility issues. Evaluate each area below and report findings as a prioritized list.

## What to check

### Motion & animation
- Does every CSS animation or transition have a `@media (prefers-reduced-motion: reduce)` override?
- Are animations purely decorative, or do any convey meaning that would be lost without them?
- Do transitions exceed 500ms? Longer durations can feel uncomfortable for sensitive users.

### Color & contrast
- Does body text (`--color-text` on `--color-bg`) meet WCAG AA contrast ratio (4.5:1 minimum)?
- Does muted text (`--color-muted`) meet 4.5:1 against the background? If not, does it meet 3:1 for large text?
- Does text in the footer (`--color-footer-text` on `--color-footer-bg`) meet 4.5:1?
- Are links distinguishable from surrounding text by something other than color alone?

### Focus & keyboard navigation
- Do all interactive elements (links, buttons) have a visible `:focus-visible` style?
- Is the default browser focus ring suppressed anywhere without a custom replacement?
- Can a keyboard-only user navigate the full page in a logical order?
- Does the sticky nav interfere with focus or skip-link behavior?

### Semantic HTML & ARIA
- Do all `aria-labelledby` attributes point to valid, existing `id` values?
- Are landmark regions present and correct: `<nav>`, `<main>`, `<footer>`?
- Do sections use `aria-labelledby` to give screen readers a meaningful label?
- Are decorative images marked `aria-hidden="true"` or given empty `alt=""`?
- Do meaningful images have descriptive, non-redundant `alt` text?

### Screen reader text
- Does `aria-hidden="true"` cover all purely decorative content (icons, arrows, emoji)?
- Are there any icon-only links or buttons missing an accessible label (`aria-label`)?

### Responsive & zoom
- Does the layout remain usable at 200% browser zoom without horizontal scrolling?
- Is `font-size` ever set in `px` on body text in a way that ignores user browser preferences?

### Touch targets
- Are all tap/click targets at least 44×44px on mobile?
- Are nav links, footer social links, and the CTA link large enough to tap accurately?

## Output format
Return a prioritized list:
- **Critical** — WCAG failure, broken keyboard nav, missing ARIA reference
- **Significant** — likely barrier for assistive technology users, missing focus style
- **Minor** — best-practice gap, low-risk but worth fixing

End with 2–3 specific, actionable fix suggestions for the highest-priority issues.
