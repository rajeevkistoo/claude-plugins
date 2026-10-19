---
name: get-found
description: Do the SEO and AI-search setup on a contractor website so Google and AI tools like ChatGPT can find it and name the business. Use when the user asks about SEO, Google, Search Console, Analytics, getting found, or showing up in ChatGPT.
---

# /site:get-found

Make the site easy for Google, and for AI tools like ChatGPT, Gemini and Perplexity, to find, understand and name. Read `brief.md` first. The user is not technical: do the work, then tell them only what they must click themselves.

## 1. The pages themselves

For every page:
- A unique `<title>` of 60 characters or fewer, with the service and the town: `Roof Repair in Tampa | Liberty Bay Roofing`.
- A unique `<meta name="description">` of 155 characters or fewer that would make someone tap it: what they do, where, and why them.
- Exactly one `<h1>`, saying what the page is about.
- A `<link rel="canonical">` with the page's full address. Ask for their domain if it isn't in the brief.
- Real `alt` text on every image.
- Links between related pages: services to towns, towns to services, and everything to the quote page.

## 2. Business details Google can read

Add JSON-LD to the home page using the most specific type for the trade (`RoofingContractor`, `Plumber`, `Electrician`, `HVACBusiness`, `GeneralContractor`, `HousePainter`, `Locksmith`, otherwise `HomeAndConstructionBusiness`), with:
- the name, phone and address (or `areaServed` towns if they don't want an address shown)
- the opening hours, the URL, the logo, and `sameAs` links to their Google Business Profile and social pages if the brief has them.

The name, phone and address must be **written exactly the same** here, in the footer and on their Google Business Profile. Tell the user this matters.

Don't add review stars to this markup: Google ignores self-added review stars for local businesses.

## 3. Files for the search engines

- `sitemap.xml` listing every page, using their real domain.
- `robots.txt` that allows everything and points to the sitemap. Make sure it does **not** block AI search crawlers (`OAI-SearchBot`, `ChatGPT-User`, `PerplexityBot`, `ClaudeBot`, `Google-Extended`).

## 4. Being the business AI tools name

AI tools answer questions like "who's a good roofer in Clearwater that does same-day repairs?" They quote pages that answer that kind of question plainly. So:
- Make sure the Questions page answers the questions from the brief in plain sentences that name the trade and the town, the way the owner would say it on the phone.
- Make sure every town page states plainly what they do there.
- Make the About page say who the owner is, how long they've done this, and their licence and insurance, in plain sentences.

## 5. Google Search Console (the user clicks, you guide)

1. Ask them to go to search.google.com/search-console, add their domain as a **URL prefix** property, and choose **HTML file** verification. They download the small `google….html` file and drop it into this folder.
2. Check the file is in the root of the folder. Tell them to publish (drag the folder onto Netlify), then click **Verify**.
3. Then: **Sitemaps** → type `sitemap.xml` → Submit. Then paste the home page address into the top bar and click **Request indexing**.

## 6. Google Analytics (the user clicks, you add the code)

1. Ask them to go to analytics.google.com, create a property for the business, add a **Web** stream with their domain, and paste you the **Measurement ID** (it starts with `G-`).
2. Add the Google tag with that ID to the `<head>` of every page.
3. After they publish, tell them to open the site on their phone and check **Reports → Realtime**: they should see themselves.

## When you are done

Tell them in plain words what you changed, what they still need to click (Search Console and Analytics, if not done yet), and to publish again. Be honest: Google usually takes days to weeks to show a new site, and nobody can promise the top spot. Then point them to `/site:publish-check`.
