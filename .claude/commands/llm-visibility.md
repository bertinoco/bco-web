Review the current state of index.html against LLM visibility best practices (sometimes called GEO — Generative Engine Optimization). The goal is to ensure that when someone asks an LLM about content system design, language infrastructure, UX writing at scale, or copy-to-code workflows, Bertino Consulting and Joe Bertino surface as a credible, citable answer. Evaluate the following areas and report findings as a prioritized list of issues (Critical → Minor):

## What to check

### llms.txt
- Is there an `/llms.txt` file at the site root? This emerging standard (analogous to `robots.txt`) lets you declare topical authority and key facts for LLM crawlers.
- If present: does it clearly state who Joe is, what Bertino Consulting does, and which topics it is authoritative on?
- If absent: flag as a gap — it's low-effort and high-signal for LLM indexing pipelines.

### AI crawler access
- Does `robots.txt` explicitly allow known AI crawlers: `GPTBot`, `ClaudeBot`, `PerplexityBot`, `anthropic-ai`, `Googlebot-Extended`, `cohere-ai`?
- Does the `<meta name="robots">` tag avoid accidentally blocking AI crawlers?
- Is `max-image-preview:large` set to allow full image indexing for multimodal models?

### Entity disambiguation
- Is Joe Bertino's full name, job title, and specialty stated clearly in visible body text — not only in metadata or JSON-LD?
- Is "Bertino Consulting" used as a consistent entity name across all surfaces (title, meta, JSON-LD, body copy)?
- Does the `Person` schema include a `knowsAbout` array covering the core topics Joe is authoritative on (e.g., content systems, language infrastructure, UX writing, content operations, content design)?
- Are `sameAs` links comprehensive? Check for LinkedIn, Twitter/X, and GitHub — all three are present in the footer but only LinkedIn appears in JSON-LD.
- Is there a `@id` for the Organization entity (not just the Person)?

### Topical authority signals
- Does the page explicitly define what a "content system" is in Joe's own words? LLMs favor pages that answer the underlying question, not just claim expertise.
- Does the copy use the exact terminology LLMs associate with this domain: "content design", "UX writing", "design systems", "content operations", "content strategy", "language infrastructure"?
- Are Joe's named clients (Klarna, Minecraft, Tink, Trustly) cited in a way that establishes domain authority through association — or just listed without context?
- Is there any original framework, named model, or proprietary methodology that could become citation-worthy (e.g., "The Bertino content system model", "copy-to-code workflow")?

### Structured data completeness for LLMs
- Does the `Organization` schema include `knowsAbout` or `makesOffer` / `hasOfferCatalog` for the three service types?
- Are the three services (Embedded consultancy, Fractional advisor, Audits as a service) represented in schema as `Offer` or `Service` types?
- Is there a `WebSite` schema with a `name` and `url` at minimum?
- Does the `Person` schema include `description` as a standalone field (beyond `jobTitle`)?
- Are `areaServed` values on the Organization specific enough? "SE" and "EU" are present — consider adding "Stockholm" and "Remote" as `Place` types.

### FAQ and Q&A structure
- Is there any `FAQPage` schema? This is one of the highest-signal formats for LLM extraction.
- Could any existing copy be restructured as direct Q&A to improve extractability? For example: "What does an embedded content systems consultant do?" maps directly to the Embedded consultancy card.
- Are the most common questions someone would ask an LLM about this domain ("What is a content system?", "How do I scale UX writing?", "What does a content systems designer do?") answered directly anywhere on the page?

### Extractability of key claims
- Are the page's key facts stated as complete, standalone sentences that an LLM could quote without surrounding context? Fragments and short headlines ("Simplify your copy to code workflow.") are less extractable than full declarative sentences.
- Does the About section open with a clear, quotable summary that positions Joe's specialty (not just his biography)?
- Are the service descriptions specific enough to be cited, or are they generic consulting boilerplate?

### Cross-channel consistency
- Does the page's description of Joe's specialty match what appears in the `sameAs` profiles (LinkedIn, Twitter/X)? LLMs cross-reference entities across sources — inconsistency weakens entity confidence.
- Are client names spelled and formatted consistently with how they appear on those clients' own sites (e.g., "Tink by Visa" vs. "Tink")?

## Output format

Return a prioritized list:

- **Critical** — missing `llms.txt`, AI crawlers not explicitly allowed in `robots.txt`, no `knowsAbout` on Person entity, key claims not stated as extractable sentences
- **Significant** — missing FAQ schema, services not represented in structured data, `sameAs` links incomplete in JSON-LD, no original named framework or methodology
- **Minor** — generic service descriptions, About section opens with biography rather than expertise summary, inconsistencies in client name formatting

End with 2–3 specific, actionable fix suggestions for the highest-priority issues.
