# AEO/SEO Portfolio Positioning — Design (2026-07-24)

Reposition the `?role=aeo` variant of `rmcdev-portfolio` (one static `index.html`, git→GitHub→Netlify) so it is **impressive to both freelance clients and recruiters** and lands work — with AEO/SEO as the clear strength on top of broad expertise. The page must itself demonstrate the discipline it sells.

## Goal & audience
- Single static HTML, client/recruiter-facing showcase, **sent** (not primarily search-found). Focus = the `aeo` variant.
- "Great at many things, **very strong in AEO/SEO**."

## Positioning (AI-extractable one-liner)
> Ross Marco Cordova is an AEO/SEO specialist who builds AI-search citation tooling and ships technical SEO for production sites — 70+ builds of range, deep specialization in AI search.

## Proof hierarchy (strongest → weakest)
1. **Built an AEO analysis engine** (his own tool; TypeScript). Hero. Describe what it checks (JSON-LD `@graph`, entity architecture, E-E-A-T pillars, answer-first / comparison-table / machine-readable-pricing / crawlability / share-of-voice). CTA: "run your site through it."
2. **This page is the proof** — valid `@graph` JSON-LD, answer-first structure, semantic HTML. "Inspect the source." (The current page has **zero JSON-LD** — the top credibility fix.)
3. **Real vs. hype nuance** — schema ≠ citation lift (Ahrefs); machine-readable pricing + timestamps *do* move citations.
4. **Applied work, honestly framed** — independent AI-automation projects; on-page health via Seobility 54→85 *labeled hygiene, not outcomes*; 70+ builds grid.
5. Breadth underneath (voice agents, meeting intelligence, workflow automation, web dev).

## HONESTY RULES (non-negotiable)
- Seobility 54→85/57→85/59→85 = **on-page audit hygiene**, never traffic/rankings/revenue. (Current copy already labels them "SEO audit score" — keep.)
- Hornblasters = **team contribution**, large Shopify (only appears in the builds list; make no solo claim).
- Meeting-Intelligence stats (81 / 1,066 / 223) are **real** — keep, unattributed, generic capability framing.
- Engine: **describe only, no sample report**; any future screenshot must run on a **neutral/public** site, never default-ai.agency (would leak).
- No "passes Core Web Vitals" claim unless measured.

## Privacy decisions (job-app privacy)
- **Scrub the "Default-AI" brand name + links everywhere on the `aeo` variant**, but keep the *work* as independent/freelance projects. Reuse the existing `VARIANTS` `over`/`hide` machinery (FREELANCE already does most of this).
- **Keep the visible LinkedIn** link (personal portfolio — recruiters expect it).
- **`sameAs` = none for now** (omit from JSON-LD; do NOT add LinkedIn to schema).
- Person node is **independent** — no `worksFor`/`founder` of an org.

## Build plan (single `index.html` + its `<script>` config)
1. **JSON-LD `@graph`** (always static, in `<head>` or top of `<body>`): `Person` (name, jobTitle "AEO/SEO Specialist & Web Developer", `knowsAbout` [AEO, answer engine optimization, technical SEO, structured data / JSON-LD, entity SEO, E-E-A-T, Core Web Vitals, Schema.org, Webflow, Shopify], **no sameAs**) → `WebSite` + `ProfilePage` (`@id` links) → the engine as a `SoftwareApplication`/`CreativeWork` authored by the Person → optionally the 3 case studies as `CreativeWork`. Consistent `@id`s (this *is* the entity-architecture demo).
2. **Extend the `aeo` VARIANT** object:
   - Stronger AEO pitch (refine existing sentence).
   - `over`: rewrite `xp1-title` ("AI Automation Specialist — Independent"), `xp1-body` (drop "Founded and operate Default-AI" → independent-practice framing, keep the shipped systems), `tradepro-brand` → "my independent practice", `closing` → contract/full-time (no "through Default-AI"). Optionally reframe `work-heading`.
   - Give the **Default-AI flagship card** its own hideable token (e.g. `data-hideable="brand-flagship"`) so we hide **only that card** for `aeo` (keep Tradepro360 + the 70+ builds list). Hide the Default-AI contact link (`contact-brand`).
3. **New AEO section** shown only for `aeo` (add a small `data-onlyfor="aeo"` show-mechanism, mirroring the hide pattern): senior capabilities list (entity architecture & JSON-LD, answer-first modules, technical SEO: crawl/index/canonical/CWV/GSC, E-E-A-T mapping, machine-readable data) + a "this page is the proof" callout + a short "real vs. hype" line + "how I keep schema accurate when data changes" (single-source-of-truth + validation).
4. **Hero for `aeo`**: lead with AEO/SEO (pitch swap already targets this; ensure the role label + pitch read AEO-first).
5. **Minor**: the meeting-intelligence demo URL contains "default-ai" — keep the demo (strong proof) but flag; hide that specific CTA for `aeo` only if strict scrub is wanted.

## Verification
- `node --check` the inline JS; validate the JSON-LD (parse + Rich Results mentally / schema validator).
- `curl` render + confirm `?role=aeo` shows: no "Default-AI" string, AEO-led content, JSON-LD present.
- Ultimate self-demonstration: run the finished page through the **aeo-tracker** (`npm run audit`/`diagnose`) and confirm it scores well.

## Out of scope
- Full redesign; sample engine report; naming/featuring default-ai.agency; other role variants (`web`, `freelance`) beyond not breaking them.
