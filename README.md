# The Afternoon Website plugin

A Claude Code plugin for contractors who want a website that brings in calls, built with an AI agent in one afternoon. It comes with the course at rajeevkistoo.com/afternoon-website.

## Install

In Claude Code (VS Code or the terminal), type:

```
/plugin marketplace add rajeevkistoo/claude-plugins
/plugin install site@rajeevkistoo
```

## Commands

| Command | What it does |
|---|---|
| `/site:interview-me` | Asks you about your business, one question at a time, and writes `brief.md` |
| `/site:build` | Builds the website from your brief |
| `/site:get-found` | Does the SEO, Google Search Console and Analytics, and gets you ready for AI answers |
| `/site:publish-check` | Checks everything, fixes what's wrong, and walks you through publishing |

Use them in that order, in a folder made just for your website.

# The Afternoon Agent plugin

A Claude Code plugin for owners of service businesses who want the small jobs off their desk: the proposal, the invoice, the follow-up, the report. You build your first AI agent in one afternoon, then copy it to build the next one yourself. It comes with the course The Afternoon Agent.

An agent is a folder with four things in it: a rulebook (`CLAUDE.md`), one job (a skill you run as a command), a template (your past example in `templates/`), and a check (it re-reads its own work before you see it). It drafts; you send.

## Install

In Claude Code (VS Code or the terminal), type:

```
/plugin marketplace add rajeevkistoo/claude-plugins
/plugin install agent@rajeevkistoo
```

## Commands

| Command | What it does |
|---|---|
| `/agent:pick-the-job` | Lists the jobs in your week, scores them, picks the first one, and writes `workforce-map.md` |
| `/agent:interview-me` | Asks you about your business, one question at a time, and writes the rulebook `CLAUDE.md` |
| `/agent:build-job` | Turns the job into its own command, runs it on real work, and fixes what it gets wrong |
| `/agent:add-check` | Makes the agent check its own work more strictly before it shows you |
| `/agent:clone` | Copies the folder into a new agent with a new job |
| `/agent:job-library` | Ten starter jobs to pick from if you're not sure where to start |

Use them in that order, in a folder made just for your first agent.
