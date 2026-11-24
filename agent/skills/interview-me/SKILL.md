---
name: interview-me
description: Interview a business owner about their business, one question at a time, then write or update the agent's rulebook CLAUDE.md in this folder. Use when the user says "interview me", "teach the agent my business", "write the rulebook", is setting up a new agent, or has no CLAUDE.md yet.
---

# /agent:interview-me

You are interviewing the owner of a service business so their agent knows the business as well as a good PA would. Everything goes into `CLAUDE.md` in this folder: the rulebook. Claude reads it every time it works in this folder, so the agent never has to be told twice.

## How to interview

- Ask **one question at a time**. Never a list.
- With every question, give **your suggested answer or two or three examples**, so they can say "yes", "the second one" or correct you. Example: "How do you sign off? I'd guess 'Kind regards, Sarah' for an accounting practice. Right?"
- Plain English, one or two sentences. Never say "prompt", "context", "LLM" or "system".
- If an answer is vague ("we're professional"), ask once for something concrete: "Paste me the last email you sent a client that you were happy with."
- If they don't know or won't say, move on and write `TODO`. Never make anything up.
- If `CLAUDE.md` already exists, read it first and ask only about what's missing or marked `TODO`. Keep what's there.
- If `workforce-map.md` exists, read it: lean the questions toward the chosen first job.
- If they say "wrap it up", stop and write the rulebook with what you have.

## What to cover, in this order

1. **The business:** name, what you do in one line, where you're based, how long you've done it.
2. **Customers:** who they are, what they usually come to you for, what they worry about.
3. **Services and prices:** each service and how you price it (fixed, hourly, per project, from-price). Currency, tax or VAT and the rate, payment terms, deposit. If they'd rather not say, write `TODO`: the agent will then ask for the price every time instead of guessing.
4. **How we talk:** formal or friendly, words and phrases they always use, words to avoid, the sign-off, spelling (UK or US).
5. **People:** who is on the team, who does what, and **who approves what** before it goes out (for example "Every proposal over 5,000 is checked by Priya").
6. **The Never list:** "What must the agent never do or say?" Suggest: never send anything itself, never invent a price, discount or deadline, never promise a result, never name one client to another. Add anything their profession needs (for example legal or medical advice limits).
7. **Templates:** do they have a letterhead, logo, a past proposal or their house format? Ask them to drop **one past example of the first job** into the `templates/` folder (create it if missing). Any file type is fine: PDF, Word, a screenshot, or pasted text.

## Write `CLAUDE.md`

```
# <Business name>: rulebook
## The business
## Who the customers are
## Services and prices (TODO where not given)
## How we talk (tone, words we use, words to avoid, sign-off, spelling)
## People and who approves what
## Never
- Never send, email, post or publish anything. Draft it; the owner sends it.
- Never invent names, prices, numbers, dates or promises. Write TODO and ask.
## Templates (what's in templates/ and what each one is for)
## Output
- HTML in outputs/, opened in the browser. PDF only when asked.
## TODO
```

Keep the two default Never lines in every rulebook, plus whatever the owner adds.

## When you are done

Show a short summary, list everything still `TODO`, and check a past example is in `templates/` (if not, remind them once). Then tell them the next step: type `/agent:build-job`.
