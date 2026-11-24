---
name: clone
description: Build agent number two by copying this agent folder's rulebook and templates into a new sibling folder and giving it a new job. Use when the user says "clone", "build my second agent", "copy this agent", "next agent", or has finished their first job.
---

# /agent:clone

Agent #2 is this folder copied, with a new job. The rulebook already knows the business, so this is quick. Read `CLAUDE.md` and `workforce-map.md` in this folder first. If there is no `CLAUDE.md`, stop and tell them to type `/agent:interview-me` first.

## 1. Pick the next job (one question at a time, with your best guess)

1. **Which job?** Take the top of "Next three" in `workforce-map.md`: "Next on your map is invoices. Shall we build that one?" If there's no map, offer the choices from `/agent:job-library`.
2. **Folder name.** Suggest one from the job: "I'll call the new folder `invoice-agent`, next to this one. OK?" Use lowercase and dashes. If that folder already exists, stop and ask for another name: never write into an existing folder.

## 2. Make the new folder

Create `../<new-agent-name>/` (next to this folder, not inside it), then copy:

| Copy | Don't copy |
|---|---|
| `CLAUDE.md` | `outputs/` (old work stays with the old agent) |
| `templates/` (all of it) | `.claude/skills/` (the old job) |
| `workforce-map.md` | anything else |

Create an empty `outputs/` and `.claude/skills/` in the new folder.

In the new folder's `CLAUDE.md`, change only the "Templates" section if this job needs a different example. Ask: "Do you have a past invoice I can learn from? Drop it into `../<new-agent-name>/templates/`." Leave everything about the business as it is.

## 3. Build the new job

Follow the `/agent:build-job` flow, working on the files in `../<new-agent-name>/`, not this folder:
- skip any question the rulebook already answers (prices, tone, people, sign-off);
- write the job skill to `../<new-agent-name>/.claude/skills/<job-slug>/SKILL.md`;
- run it once on a real example, save to `../<new-agent-name>/outputs/`, open it, and fold the fixes back in as usual.

## 4. Update both maps

In `workforce-map.md` in **both** folders, mark the new job `built (<new-agent-name>)`.

## When you are done

Tell them, in this order:
1. **Why that was fast, in one line:** "That took minutes because the rulebook already knew your business; we only had to teach it the new job."
2. **To use the new agent:** in VS Code, **File > Open Folder**, choose `<new-agent-name>`, open the Claude panel, and type `/<job-slug>`. If it doesn't show, close and reopen the Claude panel.
3. **If the business changes** (new prices, new sign-off), update `CLAUDE.md` in each agent folder, or ask any agent to do it for them.
4. **Next:** the next job on the map, and they can type `/agent:clone` again from any agent folder.
