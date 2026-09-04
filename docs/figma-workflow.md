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
