---
name: build-job
description: Turn one recurring job (a proposal, invoice, quote, follow-up, report) into a project skill the owner runs on command, with an HTML output and a built-in check, then run it on a real example and fold every fix back in. Use when the user says "build the job", "build my agent", "make the proposal agent", or after the rulebook is written.
---

# /agent:build-job

Build the agent's one job. Read `CLAUDE.md`, `workforce-map.md` and everything in `templates/` first. If there is no `CLAUDE.md`, stop and tell them to type `/agent:interview-me` first. If a job brief was handed over (from `/agent:job-library` or `/agent:clone`), start from it and only ask what it leaves open.

## 1. Agree the job (one question at a time, with your best guess)

1. **Which job?** Take the first job from `workforce-map.md`. Confirm: "We're building the proposal job. Right?" Pick a short slug for it: `proposal`, `invoice`, `follow-up`.
2. **What goes in each time?** Suggest from the template: "For a proposal I'd guess the client's name, what they need, and the price. Anything else?" Note which inputs are required and which are optional.
3. **What comes out?** One document? A document plus a short email to send it with? Match the example in `templates/`: its sections, order, length and layout.

## 2. Write the skill

Create `.claude/skills/<job-slug>/SKILL.md` in this folder:

```
---
name: <job-slug>
description: <what it makes, in one line>. Use when the owner says "<job> for ...", "draft a <job>", or types /<job-slug>.
---
# /<job-slug>
Read CLAUDE.md and the templates it lists first.
## What I need each time
<inputs; ask one at a time for anything missing; never guess a required one>
## Steps
<numbered, plain steps from input to finished document>
## Output
One self-contained HTML file in outputs/<yyyy-mm-dd>-<client>-<job-slug>.html,
styled like <template file>, printable on A4. Open it in the browser.
PDF only if the owner asks.
## Check before showing
- [ ] Every name, price, date and number came from the input or CLAUDE.md. Nothing invented.
- [ ] No TODO, blank or placeholder left unflagged.
- [ ] Nothing on the Never list in CLAUDE.md.
- [ ] Matches the template: sections, order, letterhead, sign-off.
- [ ] Sounds like "How we talk" in CLAUDE.md.
<job-specific checks, e.g. totals add up, price is present>
Fix anything that fails, then show a short "Checked:" note listing what was checked and anything still TODO.
## Never
Never send, email or post it. The owner sends it.
```

Write the steps and checks for this job, in plain words. Use the template's real structure, not a generic one.

## 3. Run it on real work

Ask for one real example: "Give me a real client you need a <job> for, with the details you'd normally use." Run the new skill exactly as written. Save the HTML to `outputs/` and open it in their browser (`open <file>` on a Mac, `start <file>` on Windows). Show the "Checked:" note.

## 4. Fix it, once and for all

Ask: "What's wrong with it? Say it plainly: 'too long', 'wrong sign-off', 'the price goes at the end'." For every fix:
- if it's about **this job** (layout, sections, steps), change `.claude/skills/<job-slug>/SKILL.md` and add a check for it;
- if it's about **the business** (tone, prices, people, a new Never), change `CLAUDE.md`.

Then re-run and re-open. Repeat until they say it's good enough to send. Tell them which file each fix went into, so they see the agent learning.

## When you are done

Tell them:
- Their new command is **`/<job-slug>`**. If it doesn't show up when they type `/`, close and reopen the Claude panel (or the VS Code window).
- Update `workforce-map.md`: this job is now `built (<folder name>)`.
- Next step: `/agent:add-check` to make the check stricter, then `/agent:clone` to build agent #2.
