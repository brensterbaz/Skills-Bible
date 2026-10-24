---
name: site-production-polish-audit
description: Use when auditing a site's production polish.
version: 1.0.0
author: Hermes Agent
license: MIT
metadata:
  hermes:
    tags: [website, audit, production, usability, quality]
    related_skills: [seo-geo-site-audit, dogfood, artifact-delivery]
---

# Site Production Polish Audit

## Overview

Audit all 20 production-quality checks from buildwithfrancis's video, turning each into an evidenced acceptance test. This is not a detector of AI-written code and does not prove who built a product. A generic aesthetic is not itself a defect.

Source: https://vm.tiktok.com/ZGdCnsQ3h/
Canonical: https://www.tiktok.com/@buildwithfrancis/video/7689063547350928643
Reviewed 2026-10-24: recovered matching public video (71.121 seconds), inspected a sequential contact sheet and full-resolution complete checklist frame. Official captions cover only the introduction and ending, not the middle checklist. Requirements below are transcribed from on-screen text; test procedures and qualifications are our engineering interpretation. Do not claim full-audio transcription or frame-by-frame review.

## When to use

Use for pre-launch checks, production-readiness reviews, removing unfinished-template symptoms, and requests to audit a website against the TikTok checklist. Complements seo-geo-site-audit; use that skill for broad discovery/indexing/GEO work rather than expanding this one beyond its twenty-control contract.

Required input: site URL. Optional: repository, intended production domain, critical journeys, authenticated test account, staging URL, approved performance budget.

Default to read-only public audit. If no URL is supplied, ask for it. If only a URL is supplied, proceed: do not block on repository access. Mark inaccessible controls UNVERIFIED, not PASS. Audit permission is not permission to deploy fixes, submit live leads, purchase, delete data, change DNS, or trigger production failure conditions.

## Execution workflow

1. Record exact requested/final URL, date, environment, intended audience, production vs preview status, access available, and tool limits. Verify page identity before testing.
2. Discover public routes from navigation and sitemap. Select home, up to three key service/product/pricing routes, one content/detail route, contact/about, one harmless nonexistent route and primary conversion journey. For an app include list/detail/form and available empty/auth states. Deduplicate in a saved manifest. Record known total and sample denominator; never call a sample an exhaustive audit.
3. Collect HTTP responses, original HTML, rendered DOM, network data and browser console independently. Use browser DOM for semantic checks and vision tools for screenshots. A screenshot alone cannot prove status codes, metadata, network behavior or working links.
4. Inspect at 375px and 390px mobile widths plus 1440px desktop. Check narrower 320px if supported; inspect navigation, overlays, forms, lists, long content and keyboard focus. Scroll before declaring lazy images broken. Record routes/viewports tested.
5. Execute C01–C20 below. Keep one row per control even when there are no issues. Use PASS, FAIL, UNVERIFIED or N/A. N/A needs a concrete applicability reason; missing access is UNVERIFIED.
6. Turn each failure into an atomic finding: control ID, URL/state/viewport, actual vs expected, reproduction, evidence path/excerpt, user impact, severity, fix, owner/dependency, complete effort and acceptance test. Separate inferred risks from reproduced failures.
7. Rank blockers first (exposed secrets, broken critical journeys, unusable mobile), then high-impact/low-effort fixes. Preserve an explicit access/validation queue. Do not hide uncertainty in a numeric aggregate score.
8. Deliver complete coverage matrix, prioritized fixes, healthy controls to preserve, scope/limitations, evidence ledger and re-test instructions. Formal handoffs follow artifact-delivery and include readable Notion content when required.
9. When fixes are authorized, establish repository/environment and deployment scope first, implement with tests, then re-run affected checks and adjacent critical journeys. Compare before/after evidence. Written code is not a verified fix; a local pass is not a production pass.

## Twenty-control acceptance contract

### C01 — vercel.app / preview domain
Inspect final host, redirect chain, visible links and absolute metadata URLs. For a production launch, verify approved branded host with valid HTTPS and consistent canonical/share URLs. Flag accidental preview-host leakage. A deliberately hosted demo or chosen provider subdomain is not automatically defective; obtain intent or mark conditional. Do not change DNS during an audit.

### C02 — generic page titles
Read source and rendered title on every sampled indexable route. Pass when titles meaningfully identify the page and product, with no template boilerplate or unexplained duplication. Test client-side route transitions as well as direct requests. Do not impose arbitrary character counts as hard limits.

### C03 — missing meta descriptions
Inspect raw/rendered meta description. Public indexable landing/content pages should have relevant, non-placeholder descriptions aligned with visible content. Explain omissions/duplication. Private utility routes may be N/A. Descriptions influence snippets, not a guaranteed ranking gain; search engines may rewrite them.

### C04 — default favicon
Resolve declared icon URLs, fetch and decode actual image bytes, and visually check branding, contrast and legibility at small size. Flag template/framework icons, missing assets and wrong MIME/content. Check browser tab appearance when available. An icon filename or HTTP 200 alone is not proof.

### C05 — no open graph image
Check original HTML for og:image on shareable routes. Resolve absolute production image URL, verify public successful response, image MIME and decoding, and sensible crop/content for intended platforms. Check og:title, og:description, og:url and relevant social-card metadata for consistency. Metadata injected only after JS can be missed by link crawlers. Use current target-platform guidance rather than inventing universal dimensions.

### C06 — missing canonical URLs
Inspect canonical on public indexable sample pages, including parameter variants when safe. Preferred URL must be absolute, intentional, accessible and aligned with redirects, internal links and sitemap. Do not canonicalize every route to home. Noindex/auth-only routes need context, not blanket failure. A declaration does not prove search engines selected it.

### C07 — broken social previews
Separate tag inspection from real platform rendering. Validate crawler-accessible original HTML, image URLs, title/description and redirects. Where accessible, use the intended platform's preview/debug tool without posting publicly. Record platform and cache limitations. If live preview cannot be observed, report metadata result and mark end-to-end preview UNVERIFIED; never infer a working preview from og:image alone.

### C08 — no custom 404
Request a unique harmless nonexistent path, directly and through client navigation. Verify HTTP 404 (or intentional 410), useful branded explanation and working recovery/navigation, without redirecting every unknown route to home. Detect soft 404s. No stack traces or secrets. Framework/router constraints do not turn a 200 error page into a verified HTTP 404.

### C09 — generic loading states
With browser throttling or approved local/staging mocks, exercise initial load, route changes and important async actions. Pass when progress is understandable, relevant controls avoid duplicate submission, assistive technology receives appropriate status, layout remains stable and waiting can end in success/empty/error recovery. Skeletons or elaborate animation are not mandatory; a clear spinner may be sufficient. Do not disrupt production services to induce loading.

### C10 — generic error messages
Exercise safe invalid input and approved staging/local timeout/offline/error scenarios. Errors should explain the problem without blame or sensitive internals, preserve valid input and offer appropriate retry/correction/support. Check field association, focus and accessible announcement. Client validation does not prove server validation. If failure paths cannot be reached safely, mark their coverage UNVERIFIED.

### C11 — broken H1 structure
Inspect DOM and accessibility semantics. Main page purpose should be expressed by a meaningful primary heading, with coherent nested sections. Flag missing/misleading main headings and styling-only misuse. Prefer a clear main H1, but multiple H1 elements alone do not prove an accessibility violation or SEO penalty. Visually hidden headings require useful semantics, not keyword stuffing.

### C12 — missing alt text
Classify image purpose. Informative images need equivalent text; decorative images typically use alt=""; linked/icon controls need accessible names describing action or destination. Inspect img, SVG, CSS-background information and icon-only controls. File names, repeated generic text and meaningless descriptions do not pass. Do not require descriptions for purely decorative images.

### C13 — no sitemap.xml
Check /sitemap.xml plus robots.txt declarations and sitemap indexes; another valid declared location is acceptable. Parse XML and sample entries for accessible canonical indexable production URLs. Reject preview hosts, dead routes and contradictory exclusions. A private/noindex app may be N/A, and a tiny crawlable site does not become unindexable just because a sitemap is absent. Report it as a discoverability improvement proportionate to scope.

### C14 — console errors
Start console/page-error/network collection before navigation and replay sampled journeys. Record error, URL, reproduction and user impact. Distinguish first-party defects from browser-extension noise, expected errors and third-party failures; do not silently ignore third-party problems that break the journey. Acceptance: no unexplained runtime errors or failed essential resources on tested paths. Clean console on one page does not prove all states healthy.

### C15 — leftover console.logs
Inspect runtime logs and, with repo access, production logging configuration and source. Flag debug chatter, sensitive tokens/PII or misleading development messages. Intentional sanitized operational diagnostics may be appropriate. Never include actual secrets in a report; redact and escalate securely. No observed log is not proof all source logging is removed; distinguish runtime and code-review coverage.

### C16 — exposed source maps
Inspect requested scripts and their sourceMappingURL references, then safely fetch only referenced maps or bounded conventional map URLs. Check whether public accessibility is intentional and whether sourcesContent exposes unintended sensitive information. Public maps are not inherently vulnerabilities; removing them does not protect client-side secrets. If secrets are exposed, prioritize revocation/rotation and server-side boundary correction with approval. Private error-monitoring uploads can preserve debugging without public publication. Avoid broad endpoint brute-forcing.

### C17 — massive JS bundles
Measure cold-load transferred/compressed JS and, where tools allow, decoded size, unused code, main-thread work and interaction latency on important routes. Distinguish cache state, device and throttling; list largest bundles and unnecessary eager dependencies. Use an agreed budget or label a proposed budget; do not fail by an arbitrary universal KB cutoff. Recommend route splitting, deferred optional code or dependency reduction based on evidence. Lab measurements are not real-user Core Web Vitals.

### C18 — broken mobile layouts
Exercise specified viewports, menus, dialogs, forms and critical journey. Check unintended horizontal overflow, clipped text/actions, overlapping fixed elements, touch targets, zoom and content order. Compare screenshot inspection with DOM geometry. Intentional horizontal carousels need not fail. If a device/browser was not tested, do not claim its compatibility.

### C19 — inconsistent UI spacing
Inspect repeated components and computed margin/padding/gap across routes/viewports. Identify concrete mismatches to existing design tokens or a documented inferred rhythm, not subjective dislike. Check vertical rhythm, aligned form labels, card internals, section spacing and responsive relationships. Intentional optical adjustments are allowed; acceptance is coherent repeated patterns without clipping/overlap, not identical spacing everywhere.

### C20 — dead buttons & links
Inventory visible interactive controls and internal links, deduplicate destinations, and test safe navigation/actions. Detect placeholder hrefs, JS-only anchors without usable semantics, wrong destinations, no-op buttons, invalid anchors and broken state transitions. Validate disabled controls as intentional and explained. Do not submit payments, send leads/messages, delete content or change accounts without explicit authorization and test data. Unexercised consequential actions remain UNVERIFIED, not PASS. Include keyboard operation and accessible names.

## Required result schema

Persist a JSON or CSV matrix with exactly C01–C20 once each. Each row includes:
- id, source_label, status, applicability_reason;
- tested_urls, states, viewports, evidence, observed_at;
- finding_ids, limitation, acceptance_test.

For FAIL and PASS, require reproducible evidence. For N/A require applicability_reason. For UNVERIFIED require limitation and next_validation. Report status counts computed from the saved matrix; PASS + FAIL + UNVERIFIED + N/A must equal 20. A control can PASS only across its declared tested scope. Partial subcheck coverage remains UNVERIFIED unless a verified failure already makes it FAIL; retain the untested portions explicitly.

Summary order: release blockers; complete coverage matrix; prioritized fixes with effort; validation queue; passed controls; re-test plan; evidence/scope. Never declare 'all done' while applicable failures or unverified checks remain. Even all green means this checklist passed in the stated scope, not a security certification or proof of a flawless site.

## Common pitfalls

- Treating the video as a universal security/SEO standard instead of an input checklist.
- Checking home only, or checking presence without correctness and behavior.
- Inventing timings, screenshots, preview results, bundle sizes or test outcomes.
- Penalizing intentional preview sites, public source maps, standard spinners or decorative empty alt text.
- Confusing an audit skill installation with an actual audit or deployed remediation.
- Omitting checks because authentication, failure-state controls or repository access is missing.

## Verification before delivery

Confirm twenty unique source labels and IDs; all statuses have evidence or explicit gaps; metadata/raw/rendered distinctions preserved; runtime/state testing included; mobile and spacing visually inspected; side effects stayed within permission; counts computed from stored results; every fix has observable acceptance; formal artifacts delivered accessibly and external writes read back.
