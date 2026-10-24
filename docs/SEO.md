# PrayerSeed — SEO playbook

Owner: marketing. Canonical host: **https://www.prayerseed.app** (apex and `prayerseed-web.vercel.app` 301 → www).

## 1. Positioning & keyword map

Search intent we can win as a new domain: long-tail, parent-led, bedtime/prayer-habit queries. Broad "prayer app" is owned by Pray.com/Hallow; we don't chase it on the home page.

| Priority | Keyword cluster | Intent | Target page |
|---|---|---|---|
| P0 | prayer app for kids / kids prayer app / children's prayer app | commercial | Home (title, H2s, FAQ) |
| P0 | bedtime Bible stories app / Bible bedtime stories for kids | commercial | Home (feature + FAQ) |
| P1 | personalised prayers for children / prayers for my child by name | commercial | Home (lead copy, FAQ) |
| P1 | Christian parenting app / family prayer app | commercial | Home ("Who it's for") |
| P2 | bedtime prayers for kids, morning prayer for children, prayer for my child starting school, prayers for toddlers, prayer for teenager exams | informational | **Blog / guides (to build)** |
| P2 | how to pray with your toddler, family prayer routine, teaching kids to pray | informational | Blog |
| Brand | PrayerSeed, PrayerSeed app, PrayerSeed+ | navigational | Home / Support |

Closest competitors in SERPs and app stores: Instill (bedtime prayers, speaks child's name), Theo (parent-child devotions, "9 minutes a day"), Pray.com (celebrity bedtime Bible stories), Evergrace, The Nightly Tales, Kingdom Parenting Daily. Our differentiators to keep in copy: *three prayers a day* (not just bedtime), *stories AND prayers*, *multiple children / co-parents*, *clear privacy for children's data* (competitors are weak here).

## 2. What's implemented (Oct 2026)

- **Title/description** rewritten for the P0 cluster; H1 kept emotional, keyword in lead copy and H3s.
- **Canonical + robots** on every page; `delete-account` is `noindex` (meta + X-Robots-Tag) but reachable for Play Store compliance.
- **robots.txt**, **sitemap.xml**, **site.webmanifest**, favicon/apple-touch icons, `theme-color`.
- **Open Graph / Twitter cards** + `og-image.jpg` (1200×630).
- **Structured data (JSON-LD)**: Organization, WebSite, WebPage, MobileApplication (offers, featureList, store links), FAQPage (answers are verbatim on-page — keep them in sync or Google ignores them).
- **Smart App Banner** (`apple-itunes-app`) on indexable pages → iOS Safari shows a native install banner.
- **Play Store referrer** on Google Play links (`utm_source=prayerseed.app`) → install attribution in Play Console.
- **Content**: How it works, Who it's for, FAQ, final CTA — more crawlable, intent-matching text and internal anchors.
- **Vercel**: vercel.app → www 301 (kills the duplicate), security headers, 1-week cache on static assets, custom 404 with internal links.

## 3. Launch checklist (needs your accounts — I can't do these)

1. **Google Search Console** → add property `prayerseed.app` (Domain, DNS TXT verification) → submit `https://www.prayerseed.app/sitemap.xml` → "Request indexing" for `/` and `/support`.
2. **Bing Webmaster Tools** → import from GSC (one click) → covers Bing + DuckDuckGo + Copilot.
3. **Rich results test**: https://search.google.com/test/rich-results on `/` — expect FAQ + Software App detected.
4. **Social preview check**: https://www.opengraph.xyz/ or share the URL in WhatsApp/Slack.
5. **PageSpeed**: https://pagespeed.web.dev/ — baseline score for mobile; the page is tiny, expect 95+.
6. **Analytics**: enable Vercel Web Analytics (Project → Analytics) or add GA4; track store-button clicks as the conversion.
7. **App Store Connect → App Analytics → Campaigns**: create a campaign link for the website so App Store installs attribute (Apple ignores UTM; needs `pt=…&ct=…` params). Then swap the App Store href.
8. **Google Business / Knowledge panel**: not applicable (no physical location). Skip.

## 4. Next 90 days (content & links — where the organic growth actually comes from)

The home page will rank for brand and a handful of commercial terms. Informational queries are 10× the volume and are what Christian parents actually search at 9 pm. Build a small content hub:

- `/blog/bedtime-prayers-for-kids` — 8–10 short prayers by age, each with a verse, ending with "get one written for your child" CTA.
- `/blog/prayers-for-children-starting-school`, `/blog/morning-prayers-for-kids`, `/blog/prayer-for-my-teenager`, `/blog/how-to-pray-with-a-toddler`, `/blog/family-prayer-routine`.
- Each post: 700–1200 words, one H1, FAQ block (FAQPage schema), author = PrayerSeed, internal link to `/` and to 2 sibling posts; add to `sitemap.xml`.
- Cadence: 2 posts/month. Static HTML is fine — same header/footer, `class="page legal"` layout already styles long-form.

Links & listings (free, high-relevance):
- Directories: faith.tools, Christian app directories, Product Hunt launch, AlternativeTo (as alternative to Instill / Pray.com).
- Church & parenting: offer a free month to church kids'-ministry leads; ask for a listing in their parent resources page.
- PR: pitch UK Christian press (Premier Christianity, Christian Today) — "AI-personalised prayers for children" is a news angle; ask for a link to www.prayerseed.app, not the store.
- Reviews: when someone emails support happy, ask for an App Store review *and* a sentence we can quote on the site (then add `Review` schema with real quotes only).

## 5. ASO alignment (store listings are search too)

- App Store **subtitle** (30 chars) should carry the P0 keyword, e.g. "Kids prayers & Bible stories". **Keyword field** (100 chars): `prayer,kids,children,bedtime,bible,stories,christian,family,devotional,faith`.
- Play **short description** already good ("Personalised prayers & Bible bedtime stories for your children, every day.").
- Store category is Lifestyle; consider **Education** or **Books & Reference** secondary only if ranking shows it helps — Instill and Theo sit in Lifestyle/Education.
- Get to 10+ ratings before adding `aggregateRating` to the site schema (currently 1 rating on iOS; adding it now looks thin and can trigger a manual review).

## 6. Maintenance rules

- Any FAQ edit → update **both** the visible `<details>` text and the JSON-LD answer.
- New page → add canonical, meta description, OG tags, and a `sitemap.xml` entry with `lastmod`.
- Never add `noindex` to `/support`, `/privacy`, `/terms` (stores link to them; they also earn brand links).
- Keep title ≤ 60 chars, description ≤ 155 chars, one H1 per page.
