Review the current state of index.html and styles.css for performance issues affecting load time and Core Web Vitals. Evaluate the following areas and report findings as a prioritized list of issues (Critical → Minor):

## What to check

### Render-blocking resources
- Are any `<script>` tags in `<head>` missing `defer` or `async` attributes?
- Are any CSS files loaded via `<link>` that could be inlined for a single-page site?
- Is the Google Fonts `<link>` using `display=swap` to prevent invisible text during load?
- Are font preconnects (`<link rel="preconnect">`) in place for external font origins?

### CSS efficiency
- Are there unused CSS rules that don't match any element in the HTML?
- Are CSS custom properties used consistently, or are values duplicated?
- Is the total CSS file size reasonable for a single-page site (target: under 10KB minified)?
- Are there any expensive CSS properties (box-shadow, filter, backdrop-filter) applied to many elements or used during scroll/animation?

### Image optimization
- Are all images served in modern formats (WebP or AVIF)?
- Are images appropriately sized for their display dimensions (no serving 2000px images in a 960px container)?
- Is `loading="lazy"` applied to images below the fold?
- Are critical above-the-fold images using `fetchpriority="high"`?
- Is there a hero or OG image that could benefit from `<link rel="preload">`?

### Font loading
- How many font weights/styles are being loaded from Google Fonts?
- Are any loaded weights unused in styles.css? Flag unnecessary weights.
- Is `font-display: swap` applied (either via Google Fonts URL parameter or CSS)?

### Third-party scripts
- List all external scripts (analytics, fonts, etc.) and their estimated impact.
- Are third-party scripts loaded with `defer` or `async`?
- Could any third-party resources be loaded later (after DOMContentLoaded)?

### HTML efficiency
- Is the total HTML file size reasonable for a single-page site (target: under 15KB)?
- Are there any inline styles that should be in the stylesheet?
- Are there unnecessary wrapper `<div>` elements that add DOM depth without purpose?

### Caching & delivery
- Is the site served over HTTPS?
- Are cache headers configured correctly for static assets (via GitHub Pages defaults)?
- Is there a `.nojekyll` file if not using Jekyll (prevents unnecessary build processing)?

### Core Web Vitals indicators
- **LCP (Largest Contentful Paint)**: What is the likely LCP element? Is it optimized (preloaded, correctly sized, no render-blocking dependencies)?
- **CLS (Cumulative Layout Shift)**: Are image dimensions set explicitly (width/height attributes)? Are fonts causing layout shift on load?
- **INP (Interaction to Next Paint)**: Are there any heavy event listeners or JavaScript operations that could delay interaction response?

## Output format

Return a prioritized list:

- **Critical** — render-blocking scripts, unoptimized large images, missing font-display swap
- **Significant** — unnecessary font weights loaded, missing lazy loading, no preconnects
- **Minor** — unused CSS rules, minor file size optimizations, caching improvements

End with 2–3 specific, actionable fix suggestions for the highest-priority issues.