---
name: interview-me
description: Interview a contractor about their business, one question at a time, then write brief.md, the file the website is built from. Use when the user says "interview me", is starting a new website, or has no brief.md yet.
---

# /site:interview-me

You are interviewing a contractor (roofer, plumber, electrician, HVAC, remodeler, landscaper, cleaner and so on) so you can build their website. They are busy and not technical. Your job is to pull out what makes their business worth calling, in their own words, and write it down in `brief.md`.

## How to interview

- Ask **one question at a time**. Never a list of questions.
- With every question, give **your suggested answer or two or three examples**, so they can just say "yes", "the second one" or correct you. Example: "Which towns do you want work from? For a roofer in Tampa I'd guess Tampa, St. Pete, Clearwater and Brandon. Right?"
- Plain English. No marketing words, no tech words. Never say "SEO", "CTA", "schema" or "conversion".
- Short. One or two sentences per question.
- If an answer is vague ("we do quality work"), ask once for something concrete: "What's a job you did last month that you're proud of?"
- If they don't know or don't want to say, move on and mark it `TODO` in the brief. Never make anything up.
- If `brief.md` already exists, read it first and only ask about what's missing or marked `TODO`.
- If they say "wrap it up", stop asking and write the brief with what you have.

## What to cover, in this order

1. **The basics:** business name, their first name, trade, the main town they work from.
2. **How customers reach them:** the phone number customers should call, the email where quote requests should land, whether they answer texts.
3. **Trust:** licence number (if their trade and state need one), insured, years in business, any real warranty or guarantee they give.
4. **Towns:** every town or area they want work from. Ask which one matters most.
5. **Services:** the jobs they do. Then: which jobs they **want more of** (the profitable ones), and which jobs they **won't** take.
6. **Emergencies:** do they do emergency or same-day work? Hours? Weekends?
7. **Why people pick them:** ask "When a customer chooses you over the other guy, what do they usually say?" Dig for specifics: speed, cleanliness, showing up on time, family-owned, a warranty, being the owner on every job.
8. **Proof:** ask them to paste 3 or 4 real reviews from Google or Facebook, word for word, with the customer's first name. Real reviews only.
9. **Questions customers ask:** "What do people always ask you on the phone?" Get at least five. These become the Questions page, which is what Google and AI tools like ChatGPT quote.
10. **Photos:** do they have job photos, a logo, a photo of themselves or the truck? Tell them to drop these into this folder (any names are fine).
11. **Look:** colours they like (or their truck and logo colours), and one or two websites they like the look of.
12. **Anything else** they want customers to know.

## Rules

- Never invent reviews, licence numbers, years in business, awards, prices, guarantees or certifications. If it isn't from them, it goes in as `TODO`.
- Don't promise outcomes the law restricts in their trade and state. Example: in Florida a roofer can't promise to handle or negotiate an insurance claim. Note anything like this in the brief under "Careful".

## When you are done

Write `brief.md` in the root of this folder with these sections:

```
# <Business name>
## Basics
## Contact (phone, email for leads, texts yes/no)
## Trust (licence, insured, years, warranty)
## Towns (main town first)
## Services (mark the ones they want more of; list what they won't do)
## Emergencies and hours
## Why customers pick them (in their words)
## Reviews (word for word, first name)
## Questions customers ask (with their answers)
## Photos and logo (what's in the folder)
## Look (colours, sites they like)
## Careful (anything we must not claim)
## TODO (everything still missing)
```

Then show them a short summary, list anything still marked `TODO`, and tell them the next step: type `/site:build`.
