---
name: job-library
description: Show ten starter jobs for a service business (proposal, invoice and reminder, quote, follow-up, meeting actions, weekly report, inbox summary, job sheet, review request, content repurposer), let the owner pick one, and hand its brief to the build-job flow. Use when the user says "job library", "show me ideas", "what jobs can an agent do", or can't think of a job.
---

# /agent:job-library

Show the owner the ten jobs below as a short numbered list: the name and one line each, not the full briefs. Ask: "Which one sounds most like your week?" Suggest one if `workforce-map.md` or `CLAUDE.md` points to it. When they pick, show that brief in full, ask "Anything to change for your business?", then follow the `/agent:build-job` flow with this brief as the starting point. If there's no `CLAUDE.md` yet, send them to `/agent:interview-me` first.

## The ten starter jobs

**1. Proposal** (`proposal`)
- In: client name and contact, what they need, the price (or the service from the price list), any deadline.
- Out: a proposal in the house format: their situation, what we'll do, timeline, price, next step. Plus a three-line covering email.
- Check: the price is present and matches the input or price list; client name spelled as given; no promised results; signed by whoever the rulebook says.

**2. Invoice and payment reminder** (`invoice`)
- In: client, what was done, amounts, invoice number (or the last one used), due date.
- Out: an invoice in the house format, and polite reminder drafts for any that are overdue.
- Check: totals and tax recalculated; number follows on from the last; bank details from the rulebook only; no late fee unless the rulebook sets one.

**3. Quote** (`quote`)
- In: the client, the job, line items and quantities, prices (or the price list), how long it's valid.
- Out: an itemised quote with totals, what's included, what's not, and the validity date.
- Check: every line has a price from the input or list; sums add up; exclusions stated; no price guessed.

**4. Follow-up after an enquiry** (`follow-up`)
- In: the enquiry as it came in (pasted email, form or message), and any notes from a call.
- Out: a reply that answers what they asked and suggests one clear next step, plus a short nudge to send after a few days if there's no answer.
- Check: answers only what the rulebook can back up; no availability, price or promise that isn't in the input; their name and question are right.

**5. Meeting notes to action list** (`meeting-actions`)
- In: rough notes or a transcript, and who was in the meeting.
- Out: decisions, actions (who, what, by when), open questions, and an optional recap email.
- Check: every action has an owner named in the notes; no due date unless one was said; nothing added that wasn't discussed.

**6. Weekly numbers report** (`weekly-report`)
- In: this week's numbers, pasted or as a spreadsheet file in the folder; last week's report if there is one.
- Out: one page: the numbers, the change since last week, what stands out, and questions to ask.
- Check: every figure traces to the input; changes recalculated; no explanation presented as fact if it's a guess.

**7. Inbox triage summary** (`inbox-summary`)
- In: emails pasted or saved into the folder (the agent does not log into email).
- Out: a summary grouped into needs you today, can wait, and FYI, with a draft reply for each urgent one.
- Check: no email left out; senders and dates correct; drafts follow "How we talk"; nothing sent.

**8. Job sheet / work order** (`job-sheet`)
- In: client, site or address, the work to be done, who is assigned, date, materials or notes.
- Out: a one-page job sheet the team can print or open on a phone.
- Check: address and contact exactly as given; assigned person is on the team list; no materials or times invented.

**9. Review request** (`review-request`)
- In: the client's first name, the job you did for them, the review link from the rulebook.
- Out: a short, personal message asking for a review, in email and text-message lengths.
- Check: names the real job; uses the review link from the rulebook only; no pressure or incentive; never writes the review for them.

**10. Content repurposer** (`repurpose`)
- In: one long piece (an article, a talk transcript, a newsletter) pasted or in the folder.
- Out: five short posts for the channels in the rulebook, each with a one-line hook.
- Check: every claim comes from the source piece; tone matches "How we talk"; nothing on the Never list; nothing posted.

## Rules

- These are starting points. The owner's template and rulebook always win over the brief.
- Anything that would talk to customers unsupervised, take money or answer calls is not in this library. Say so if they ask.
