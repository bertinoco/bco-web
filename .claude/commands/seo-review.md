Review the current state of index.html against SEO best practices and the design system defined in CLAUDE.md. Evaluate the following areas and report findings as a prioritized list of issues (Critical → Minor):

## What to check

### Meta tags
- Is `<title>` present, unique, and under 60 characters?
- Is `<meta name="description">` present and under 155 characters?
- Does the description accurately reflect the page content?
- Is `<meta name="viewport">` set correctly for mobile?
- Is there a `<link rel="canonical">` pointing to the correct URL?

### Open Graph
- Are `og:title`, `og:description`, `og:image`, `og:url`, and `og:type` all present?
- Is `og:image` pointing to a valid, accessible URL with recommended dimensions (1200×630)?
- Does `og:description` align in tone and content with the meta description without being identical?

### Structured data (JSON-LD)
- Is there a valid `<script type="application/ld+json">` block?
- Does the `@graph` include appropriate types (Organization, Person, WebPage)?
- Are `name`, `url`, `description`, and `contactPoint` populated correctly?
- Does the Person entity reference the Organization via `worksFor`?
- Are `sameAs` links (LinkedIn, etc.) present and valid?

### Heading hierarchy
- Is there exactly one `<h1>` on the page?
- Do headings follow a logical sequence (h1 → h2 → h3) with no skipped levels?
- Do heading texts reflect the page's core topics (content systems, language infrastructure)?

### Images & media
- Do all `<img>` elements have meaningful `alt` attributes?
- Are images using modern formats (WebP, AVIF) with appropriate fallbacks?
- Are images sized correctly (no oversized assets being scaled down in CSS)?
- Is there lazy loading (`loading="lazy"`) on below-the-fold images?

### Links & navigation
- Do all internal links use relative paths or correct absolute URLs?
- Are external links using `rel="noopener noreferrer"` where appropriate?
- Is there a skip-to-content link for accessibility?
- Do anchor links (nav → sections) point to valid `id` attributes?

### Crawlability
- Is there a `robots.txt` file at the site root?
- Is there a `sitemap.xml` file referenced in `robots.txt`?
- Are there any `noindex` or `nofollow` tags that shouldn't be there?

### Language & locale
- Is `<html lang="en">` set correctly?
- If multilingual support is planned, are `hreflang` tags present?

### Content consistency
- Does the messaging across `<title>`, meta description, OG tags, JSON-LD, and hero copy use consistent terminology (content systems, language infrastructure)?
- Are there any contradictions between metadata and visible page content?

## Output format

Return a prioritized list:

- **Critical** — missing or broken metadata, invalid structured data, crawlability blockers
- **Significant** — inconsistent messaging across tags, missing OG/schema fields, heading hierarchy issues
- **Minor** — suboptimal description length, image format improvements, polish items

End with 2–3 specific, actionable fix suggestions for the highest-priority issues.