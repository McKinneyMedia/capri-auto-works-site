# Capri: Figma → GitHub → Vercel

Production: https://www.capriautoworks.online/
Repository: https://github.com/McKinneyMedia/capri-auto-works-site
Vercel project: capri-auto-works (McKinney Media), production branch main.
Figma: https://www.figma.com/design/YSHGKtN5oZDft5ds96ZKYH

## Frame-to-code map

| Figma node | Implementation |
| --- | --- |
| Desktop homepage 1:107 | index.html |
| Mobile homepage 58:91 | assets/site.css media queries |
| Header 1:108 | header, .site-nav |
| Hero 1:110 | .hero |
| Service cards 1:112 | #auto-repair, #inspection-emissions, #used-cars |
| Emissions callout 1:114 | #free-diagnostics |
| Why Capri 1:116 | .why |
| Service area 1:120 | .area |
| FAQ 1:126 | #faq |
| Location 1:128 | #visit |
| Final CTA 1:130 | .cta |
| Footer 1:132 | footer |
| Button/Primary 1:35 | .btn-primary |
| Secondary buttons 1:37, 1:39 | .btn-outline |
| Mobile actions 1:99 | .mobile-actions |

Color variables live in assets/tokens.css; reusable styles and responsive layouts live in assets/site.css. HTML sections carry data-figma-node references. Assets are committed locally; expiring Figma MCP URLs must not be used in production.

## Editorial rules

Auto Repair first; PA Inspection & Emissions second; Free Emissions Diagnostics is a differentiator. Used Cars is secondary and directs customers to call or visit the lot. No online inventory. A free diagnostic is not a free state emissions inspection. Do not publish unverified sample testimonials, payment methods, or vehicle claims.

## Update and release

1. Edit the existing desktop/mobile Figma frames using shared components. Copy links to changed selections and record the approved changes.
2. Read the specific nodes through Figma MCP get_design_context. Adapt changes into existing HTML/CSS; do not overwrite the site with generated React code.
3. Work on a Git branch. Update relevant sections, tokens and assets. Update the build-version meta tag, footer stamp and stylesheet version queries together.
4. Push and open a GitHub pull request. Review the Vercel preview and verify that its source commit matches the pull request.
5. Check 1440, 820, 390 and 320 pixel widths, navigation, FAQ expansion, call/directions destinations, keyboard focus, metadata, canonical, robots and sitemap.
6. Merge the reviewed commit into main. Confirm Vercel READY and matching commit SHA, then verify the marker at both the plain and cache-busted production URL.
7. If release verification fails, restore the prior Vercel deployment and revert the Git commit so source and production agree.

The apex domain redirects to www. Keep the existing DNS and hosting configuration.

## Automatic versus manual

Automatic: the existing GitHub integration triggers Vercel deployments. Shared CSS tokens apply consistently across the page.

Manual: selecting approved Figma changes, implementing HTML/CSS, exporting assets, reviewing previews, merging and verifying production. Component descriptions with GitHub references and this map help navigation; they do not synchronize designs and code automatically.

Code Connect was not configured. The observed Figma plan is Professional; the Code Connect skill requires Organization or Enterprise. This workflow does not require a plan upgrade.

## Current scope

As inspected September 4, 2026 UTC, only the desktop and mobile homepage frames were populated. Auto Repair — Desktop, Inspection & Emissions — Desktop, Used Cars — Desktop, Contact — Desktop and Mobile — Other Pages were empty. Production is one page with section navigation. Additional pages need content, design and implementation before adding routes to navigation or sitemap.

The repository has no form backend, notification recipient or booking service. Contact uses telephone, directions and visits. A future form needs a confirmed destination and delivery verification. Do not deploy a decorative form or report test delivery without evidence.

Phone, address and hours match the existing repository and Figma; they were not reconfirmed directly with the business during this deployment. Figma sample reviews were not treated as verified testimonials.

Native developer-resource APIs were unavailable in the connector. References were saved in the descriptions of seven existing Figma components instead. Desktop and mobile hero headlines/supporting copy were updated. Other Figma sections retain their prior layout and draft content; follow the editorial rules above when implementing them.

## v6 visual correction — September 4, 2026

Re-read desktop 1:107 and mobile 58:91 (mobile contents now 84:19 onward) before implementing. The previous adapted layout was replaced with the Figma single-row desktop navigation, mobile hamburger, cropped hero, three service cards, inline benefit icons, both exported maps, expanded FAQ rows, location map on the left, and responsive CTA/footer. Inter fonts and optimized images are self-hosted. assets/site.js controls the accessible mobile menu.

Intentional differences: omit unverified sample reviews and payment claims; use call/visit destinations because the additional page frames are empty and no form backend exists; keep three service cards on mobile because mobile services frame 84:34 is empty. FAQ answers clarify the diagnostic offer and no online inventory. These differences change total page height.

Before every release compare fresh desktop AND mobile Figma screenshots with the rendered page. A version-marker change alone does not bring Figma changes into production. Update the HTML, CSS and assets first, then verify the actual published files against the release.

## v7 source refresh

Fresh design context now includes desktop header logo I1:134;91:85 at 109×62, footer logo 91:93 at 109×62, mobile footer logo 84:149 at full width ×126, and bordered mobile action bar 84:155. These updates and exported mobile menu/FAQ icons are implemented in v7.

Desktop contact form 87:69 was newly added in Figma. It has first/last name, email, phone, optional vehicle year/make/model, and message fields. The email shown in the input is not proof of the delivery recipient. Form publication remains pending a confirmed recipient and configured delivery service; do not show a false success state or a nonfunctional Send button.

Recipient confirmed: capriautoworks@gmail.com. The responsive contact form is prepared locally, but publication is pending explicit approval of FormSubmit as the processor, inbox activation, and delivery verification. v7 publishes only the Figma visual changes.

## v8 contact form launch

The user explicitly approved FormSubmit as the processor for names, email addresses, phone numbers, optional vehicle details and messages, forwarding to capriautoworks@gmail.com. The prepared form is published in v8 with required/email validation and provider CAPTCHA enabled. Confirm inbox activation and test-message receipt before calling email delivery verified. FormSubmit owns the submission confirmation page; no false local success screen is used.

## v9 fresh deployment

Re-read Figma desktop 1:107 and mobile 58:91. Desktop design context was unchanged; mobile header logo 84:21 changed to 190×48.117. Applied the new mobile dimensions and current exported mobile image. Retained the approved FormSubmit form and existing editorial exceptions. Version 2026-09-04-v9 triggers a fresh GitHub-to-Vercel production deployment.

## v10 redesign — November 17, 2026

Production was replaced with a new single-page design that was built directly in code, not from Figma. The Figma frame map above describes v9 and no longer matches production. Update Figma from the live site before using the Figma-first process again.

What changed:

- One `index.html` with inline CSS and JS. `assets/site.css`, `assets/tokens.css`, `assets/site.js`, the Inter fonts, icons and exported images were removed. They remain in Git history.
- Hero with a garage-door reveal and a live open/closed status computed in America/New_York.
- "What's going on?" triage chips, a decoder for 8 dashboard warning lights, and a PA inspection sticker checker. The checker assumes a 3-month early-inspection window; confirm against PennDOT guidance.
- The Google Map is embedded directly and lazy-loaded (it loads as visitors scroll toward it). Fonts are self-hosted woff2 files, and the logo is WebP. JSON-LD `AutoRepair` data is included.
- The FormSubmit form keeps the approved recipient (capriautoworks@gmail.com), adds a honeypot field, and asks a required "Have you been to Capri before?" question (New, Current or Past customer, sent as `customer_type`).

Editorial checks for this release:

- Phone, address and hours match v9.
- The free emissions diagnostic is stated as separate from the PA emissions inspection.
- Used cars point to calling or visiting the lot, with no online inventory.
- The review quotes and the "92% recommend (35 reviews)" figure are real public reviews from Capri's Facebook page and Google Business Profile (checked November 16, 2026). They are not Figma samples.
- The review figure will drift over time, so recheck it periodically.

Before this release, Lighthouse on a temporary deploy scored 100 in all four categories on desktop, and on mobile scored 99 for Performance and 100 for the other three.

## v10.3 social share, favicon, SEO and AEO — November 17, 2026

- Social share image: `assets/og-image.jpg` (1200×630, supplied by Carter). Open Graph and Twitter card tags include size and alt text.
- Icons: `favicon.ico` (16/32/48), a 32px PNG, a 180px Apple touch icon, and 192/512 manifest icons. All are cropped from the logo's "C".
- Structured data: one JSON-LD `@graph` with WebSite, WebPage, AutoRepair and FAQPage.
  - AutoRepair adds a description, image, Google Maps link (CID 8282412669277652845), City-typed service areas and a service catalog.
  - FAQPage is generated from the five visible FAQ answers. If you edit an FAQ, update the JSON-LD to match.
- No review or rating markup. Google does not show review stars for businesses marking up their own reviews.
- `llms.txt` gives AI answer engines a plain-text summary of the business. Keep its hours and services in step with the page.
- `robots.txt` already allows all crawlers. The sitemap now has a `lastmod`.
