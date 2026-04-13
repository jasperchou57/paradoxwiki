# paradoxwiki.net

Static site for the Paradox Roblox (Bleach RPG) wiki + build planner.
Zero build step. Deploy directly to Cloudflare Pages / Vercel / Netlify.

## Structure

```
/                          index.html              Homepage (op.gg style)
/codes/                    codes/index.html        P0-1 · live code tracker
/trello/                   trello/index.html       P0-2 · searchable Trello mirror
/tier-list/                tier-list/index.html    P0-4 · weekly tier list
/tools/build-planner/      tools/build-planner/    P0-5 · core moat tool
sitemap.xml
robots.txt
```

All pages are single-file static HTML with Tailwind CDN + inline JS.
No build step. No framework. Ship fast, kill fast.

## Deploy (Cloudflare Pages — fastest path)

```
cd /Users/japser/claude/paradoxwiki
npx wrangler pages deploy . --project-name=paradoxwiki
```

Or drag-drop the folder into https://dash.cloudflare.com/pages.

Then point paradoxwiki.net DNS at the Pages project.

## Critical next steps (ordered by SEO impact)

1. **Replace placeholder codes with real ones from the official Discord**
   - File: `codes/index.html` → search `RELEASE2026`
   - File: `index.html` → same 5 rows in the Live Codes table
   - Source: https://discord.gg/ableachgame → #announcements pinned messages

2. **Replace placeholder Trello data with real cards**
   - File: `trello/index.html` → all `.card-row` blocks
   - Source: official Trello linked from Discord pins
   - Target: 6-hour refresh cadence

3. **Replace Build Planner formulas with real Trello calibration numbers**
   - File: `tools/build-planner/index.html` → search `const DATA=`
   - Keys to update: `clanPassive`, `shikaiScale`, `weaponBase`
   - Source: Paradox Trello damage calibration card

4. **Submit to Google Search Console**
   - Add property: https://paradoxwiki.net
   - Verify via DNS TXT or HTML file
   - Submit sitemap: https://paradoxwiki.net/sitemap.xml

5. **Submit to Bing Webmaster Tools**
   - Add site, verify, submit sitemap

6. **Add analytics**
   - Recommended: Plausible (privacy, cheap) or Cloudflare Web Analytics (free)
   - Avoid GA4 until needed — AdSense doesn't require it

## What's included per SOP

### On-Page SEO (all pages)
- Title 50-60 chars, keyword-front-loaded
- Description 120-155 chars
- Single H1 with primary keyword
- 800+ English words per page
- 3-5% keyword density
- FAQPage + Breadcrumb + VideoGame/SoftwareApplication/HowTo Schema
- Canonical tag
- OpenGraph tags
- `max-image-preview:large`

### Three-zone V2.0 structure (tool pages)
- Zone 1: interactive tool in first screen (no CTA jump)
- Zone 2: 800-word content block with unique info gain
- Zone 3: FAQ (FAQPage schema) + internal link cards

### Behavior design (Build Planner)
- Zero signup, first-screen interaction (Hick's Law)
- Real-time stat calc (< 100ms feedback loop)
- "Build optimized X%" progress bar (Zeigarnik effect)
- Actionable suggestions (Goal Gradient)
- Shareable URL + localStorage auto-save (Endowment effect)
- Loss framing in copy ("Don't miss...", "Your code expires in...")

### Internal links (Hub & Spoke)
- Homepage → all 4 sub-pages (3 card grid + nav)
- Codes → Build Planner (workflow push: "spend your Potential wisely")
- Codes → Tier List (workflow push: "check this week's meta")
- Codes → Trello (workflow push: "find all current events")
- Trello → Tier List + Build Planner
- Tier List → Build Planner (submission CTA)
- Build Planner → meta builds table with prefilled URLs

## Kill criteria (from Levels analysis — stick to these)

| When | Check | Action |
|------|-------|--------|
| Day 7  | GSC impressions > 500 | Keep shipping |
| Day 14 | DAU > 50 | Add P1 pages (rising breakout keywords) |
| Day 30 | Revenue > $50 | Decide if worth scaling |
| Day 60 | Revenue > $200 | Continue; else archive & reuse template for next hot game |

Any time | Rolimon peak CCU drops below 10k | Freeze feature work, maintain only `/codes`

## What NOT to do (from Levels + SOP)

- No paid backlinks ($4500-6000 budget kills ROI for a 6-month game)
- No subscription model (Roblox teen audience, <0.5% payment rate)
- No gradients, no `rounded-2xl`, no Geist font, no "Welcome to..." copy
- No multi-language until week 4
- No Next.js / DDD / Trace IDs — this is a 6-month disposable site
- No HackerNews / V2EX / ProductHunt launches — wrong audience
- Do use: Discord #showcase, Reddit r/roblox, TikTok, YouTuber DMs

## Content pipeline (Week 2+)

Rising breakout keywords with near-zero competition — build in this order:

1. `/progression/hollow` — "hollow progression paradox" (RISING +800%)
2. `/progression/how-to-wipe` — "how to wipe in paradox roblox" (RISING)
3. `/bosses/boss-portal` — "paradox boss portal" (RISING)
4. `/bosses/menos` — "menos paradox" (RISING)
5. `/factions/best` — "best faction in paradox roblox" (RISING)
6. `/items/eternal-flame` — "eternal flame paradox" (RISING)
7. `/weapons/` — "paradox weapon" (RISING)
8. `/abilities/` — "paradox abilities roblox" (RISING)

Then per SOP: one or two `/blog/` posts per week covering the long tail that
tool/hub pages can't cover (patch analysis, meta shifts, YouTuber reactions).
Blog stays in subdirectory, never subdomain.
