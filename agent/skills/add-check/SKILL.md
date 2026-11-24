---
name: add-check
description: Review an agent's job skill and make its "Check before showing" list stricter, so the agent catches its own mistakes before the owner sees the work, then re-run the job and show the "Checked:" note. Use when the user says "add a check", "make it check its work", "it keeps getting X wrong", or after building a job.
---

# /agent:add-check

The check is what turns a draft into something the owner can send without rewriting. Read `CLAUDE.md`, the job skill in `.claude/skills/`, the files in `templates/`, and the latest files in `outputs/`. If there is more than one job skill, ask which one: "I see `proposal` and `invoice`. Which one gets the stricter check?"

## 1. Find what can go wrong

Look at the job and the last outputs, and ask the owner one question: "What did you have to fix last time, even something small?" Then build the list from four sources:

**Facts that must come from the input, never invented**
- Client and contact names, spelled exactly as given.
- Every price, amount, quantity, rate, date and deadline: each one traceable to the input or to `CLAUDE.md`. If it isn't, it becomes `TODO` and is flagged.
- Totals, tax and discounts recalculated from the line items, not copied.
- No made-up results, figures, testimonials or past work.

**The rulebook's Never list**
- One check line per item under "Never" in `CLAUDE.md`, worded so it can be ticked or failed.

**The format**
- Same sections, order and headings as the template.
- Letterhead, logo, contact details and sign-off present and correct.
- Required parts present (for a proposal: the price; for an invoice: the number, due date and payment details).
- Spelling as set in "How we talk" (UK or US), and the tone matches.

**Everything the owner has corrected so far**
- Read the conversation and past fixes in the skill. Each correction becomes its own check, so it is never needed twice.

## 2. Rewrite the check

Replace the "Check before showing" section of the job skill with the full list, grouped as above, each line a plain yes/no test. Keep the closing instruction:

```
Fix anything that fails, then show a short note:
Checked: names, prices, dates, totals, Never list, format, tone. Fixed: <what>. Still TODO: <what, or "nothing">.
```

## 3. A log, if they want one

Ask: "Want a one-line record of every run, so you can see what it did?" If yes, add a step to the end of the job skill: append a line to `outputs/log.md` (create it with this header if missing):

```
| Date | Client | Output file | Checks failed and fixed | Still TODO |
```

## 4. Prove it

Re-run the job on the last example in `outputs/` (or ask for one). Save the new version next to the old one, open it in the browser, and show the "Checked:" note. Point out anything the new check caught that the old one would have missed.

## Rules

- Checks only test facts against the input, `CLAUDE.md` and `templates/`. A check never adds new facts.
- Don't make the check so long the note becomes noise: the note is three lines at most.
- Tell them which file you changed. Next step: `/agent:clone` to build agent #2.
