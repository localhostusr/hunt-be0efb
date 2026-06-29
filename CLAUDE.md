# CLAUDE.md, Shane "The Hunt" Career Tracker

## What this is
A single self-contained HTML career-search tool built for Shane Sprague, a craft-beer sales and marketing
pro (Advanced Cicerone) leaving the beverage industry. It guides him from idea stage to targeted
applications and informational interviews. Styled like an ecommerce storefront (Amazon aesthetic, no
Amazon trademarks) with a full-page bald eagle watermark, and the parody elements all do real work.

## Where things live (current, as of 2026-06-29)
- Live site: https://localhostusr.github.io/hunt-be0efb/
- GitHub repo: localhostusr/hunt-be0efb (public, hardened: obscure name + noindex meta + robots.txt disallow)
- Canonical local repo (deploy source): ~/Documents/shane-career-tracker-site (index.html + eagle-watermark.jpg + robots.txt + this file)
- Resumes + prior career materials: Google Drive, My Drive/6. Career/01. Shane
- Backup snapshot of the HTML (stale, June 5): Google Drive, My Drive/Family/Shane

## REPO HISTORY, READ THIS (avoids a past mistake)
- Originally deployed to repo localhostusr/tracker-499ce2.
- That repo got taken over by a SEPARATE project, a vinyl record inventory app called "The Wax Stacks"
  (vinyl-inventory.html). On 2026-06-29 the career tracker was moved to its own dedicated repo
  (hunt-be0efb) to end the collision. tracker-499ce2 is now VINYL ONLY, its homepage redirects to the
  vinyl app. Do NOT push Shane career-tracker content to tracker-499ce2 ever again.
- The old local dir ~/Documents/shane-the-hunt-tracker is DEPRECATED, its git origin still points at the
  vinyl repo. Do not deploy from it. Use ~/Documents/shane-career-tracker-site.

## Deploy workflow (how to ship a change)
1. Edit ~/Documents/shane-career-tracker-site/index.html directly (the old Downloads working copy is gone).
2. gh auth switch --user localhostusr   (the CLI also has chriskohlPMP; localhostusr must be active to push)
3. git -C ~/Documents/shane-career-tracker-site add -A && commit && push origin main
4. GitHub Pages rebuilds in 1 to 3 min. The link Shane has never changes; it always serves the latest.

## Architecture
- One HTML file. Vanilla JS, no build step, no dependencies. CSS is base styles plus a later override
  block ("Amazon-style restyle") that re-themes via CSS variables.
- Tabs are data-driven from the TABS array; each entry maps to a section.tab by id. show(id) toggles them.
- Persistence is localStorage, per browser, private to the user. Keys: shaneOptState, shaneInterviews,
  shaneScorecard, shaneApplications, shaneVersions, shanePlanChecks.
- IMPORTANT: Shane's typed-in data never reaches GitHub. The document is versioned by git; his data is
  versioned only by the in-app Saved Versions tab and the JSON backup export/import. Saving the web page
  does NOT save his data.

## Tabs
Start Here, Game Plan, Resources, Options Menu, Jargon Decoder, Info Interviews, Decision Scorecard,
Applications, Income Reference, The Journey, AI Edge, Saved Versions.
- Game Plan: the source-of-truth current direction (June 26 review), scoring matrix with a directional
  caveat, July/August timeline, and an interactive action checklist (Shane's items + Chris's items).
- Options Menu: 16 options across 3 lanes, editable Interest/Status/Notes, parody ratings/badges, search.
- The Journey tab is the canonical written record of the strategy and every decision.
- Saved Versions: snapshot/restore + download/import JSON backup.

## The strategy (current direction, June 26 2026 review)
- PRIMARY focus: Real Estate related, led by Mortgage Lending, then Title Insurance Sales.
- SECONDARY: Hospitality and Medical Sales. No new job categories right now, work the leads in motion.
- Timeline: July is housing/move + career search; in August as current contract work runs out, career
  search ramps toward 100%. Resumes should be ready before August.
- Scoring caveat: the June 26 matrix double-counts "speed," which inflates Mortgage and understates
  Medical. A salaried medical associate could pay sooner/steadier than commission mortgage lending. Treat
  the scores as directional; the RE-primary call rests on real leads + the August clock, not the points.
- Background framing still valid: Shane is an Autonomy-Seeker not a Founder; three-lane model (Employee /
  Center-merge / Autonomy) lives in The Journey tab.

## Open work items (as of 2026-06-29)
- BUILD: Mortgage Lending resume + Title Insurance Sales resume (mirror the navy one-page med-device
  resume already saved in Drive 6. Career/01. Shane). These were the next deliverables when the repo
  collision interrupted.
- Med Sales "is it really a 15+" scoping memo (AI task).
- Med-device resume (Shane Sprague Resume - Medical Device.pdf/.docx) already built; now the SECONDARY asset.

## Testing
Validated with Playwright (Chromium). Scripts in /tmp (ephemeral): test_tracker.py, validate.py,
test_plan.py, shot.py. Serve the repo dir over http for tests (localStorage on file:// is unreliable).
If Playwright errors that the browser is missing, run: python3 -m playwright install chromium-headless-shell.

## Known caveats (disclosed in the page)
- Star ratings and "Best Seller" badges are parody, footnoted. Real ranking is in The Journey tab.
- AI Edge tool prices are early-2026 ballparks; verify before subscribing.
- Financial figures are directional San Diego 2026 estimates at ~7% mortgage rates. Entry condo all-in
  corrected to ~$4,850/mo (incl HOA); median house ~$6,300/mo.

## Status
2026-06-29: Game Plan tab added; tracker migrated to dedicated repo hunt-be0efb; vinyl repo separated.
Next: build the Mortgage Lending and Title Insurance resumes.
