---
name: build
description: Build a contractor's website from brief.md as plain HTML and CSS that publishes anywhere. Use when the user asks to build, rebuild or redesign their website.
---

# /site:build

Build the website from `brief.md` in this folder. If there is no `brief.md`, stop and tell the user to type `/site:interview-me` first.

## What to build

Plain HTML and CSS, with JavaScript only where it's needed. No frameworks, no build step, no npm. The folder itself is the website: the user publishes it by dragging it onto Netlify.

Every page lives in its own folder as `index.html`, so the addresses are clean (`/services/`, not `/services.html`).

**Pages:**
- **Home** (`/index.html`): the headline says what they do and where ("Roof repair and replacement in Tampa Bay"). A phone button and a short quote form above the fold. Then services, why customers pick them, reviews, the towns they cover, and a final call to action.
- **Services** (`/services/`): one section per service, with the ones they want more of first. If there are 4 or more big services, give each its own page.
- **Service areas** (`/service-areas/`) plus **one page per town** (`/service-areas/<town>/`). Every town page needs genuinely local wording, not the same paragraph with the name swapped.
- **About** (`/about/`): the owner, the story, licence and insurance.
- **Questions** (`/questions/`): the questions from the brief, each answered in two to four plain sentences.
- **Get a quote** (`/quote/`): the full quote form.
- **Thank you** (`/thank-you/`): what happens next and when they'll hear back.
- **404** (`/404.html`).

## The things that make it ring

- The phone number is a tap-to-call link (`tel:`) everywhere it appears: in the header, the hero and the footer.
- On phones, a bar stuck to the bottom of the screen with **Call** and **Free quote**.
- Forms work on Netlify with no code: `<form name="quote" method="POST" data-netlify="true" netlify-honeypot="bot-field" action="/thank-you/">`, a hidden `<input type="hidden" name="form-name" value="quote">`, and a hidden honeypot field `bot-field`. Every form on the site gets its own `name`.
- Short forms: name, phone, town or ZIP, and the job. The full quote page can ask for more.
- Licence, insurance and real reviews near the top, not buried.

## Look

- Use the colours from the brief. If there are none, pick two strong ones that suit the trade, plus white and a dark neutral.
- Mobile first. Check every page at phone width: no sideways scrolling, nothing smaller than 16px in a form field, and buttons big enough for a thumb.
- Use their photos from the folder. Make every image no wider than 1600px, compress it, and give it real `alt` text that describes the job and the town. If they have no photos yet, use clearly placeholder blocks and add a `TODO`. Never pass stock photos off as their work.
- One `styles.css` shared by every page.

## Rules

- Only facts from the brief. No invented reviews, numbers, awards, prices or guarantees. Anything missing stays visibly `TODO` in the page, so it can't go live by accident.
- Follow anything in the brief's "Careful" section.

## When you are done

1. Open the home page in their browser so they can see it.
2. Tell them in three or four lines what you built.
3. Ask them to click around on their phone and their laptop and tell you what to change, in plain words ("make the phone number bigger", "move the reviews higher").
4. When they're happy, tell them the next step: type `/site:get-found`.
