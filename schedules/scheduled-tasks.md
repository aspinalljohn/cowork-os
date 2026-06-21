# Scheduled Tasks — the cadence layer

Cowork lets you set a task once and run it on a cadence ("every morning", "every Friday"). This file is the menu of recurring work worth automating in this workspace. Each entry has the **cadence**, the **exact prompt** to give Cowork when you create the scheduled task, and what it produces.

> To set one up: in Cowork, create a scheduled task, paste the prompt, set the cadence. Cowork runs it unattended and leaves the output where the prompt says.

---

## Intake — pull inputs in (email / Slack / web)

These fetch work *for* you, so you don't move files by hand. Each needs the relevant connector granted (email, Slack, Chrome).

- **Email → inbox.** Cadence: every weekday morning. Prompt: `Read SKILL.md. Read new emails labeled "cowork", save any attachments into 00-inbox/, and write a one-line summary file for each. Then run inbox-triage and propose routing — don't move anything without approval.` Produces: an inbox filled and pre-triaged before you sit down.
- **Slack → inbox.** Cadence: hourly. Prompt: `Read SKILL.md. Check Slack #intake for files or links shared since the last run, and save them into 00-inbox/ with a one-line note on each.` Produces: shared material captured without you switching apps.
- **Web reading list → inbox.** Cadence: daily. Prompt: `Read SKILL.md. Gather the links I flagged today and save a reading list into 00-inbox/ with a one-line summary each.` Produces: a single triage-ready reading list.

## Daily — inbox triage

- **Cadence:** every weekday morning
- **Prompt:** `Read SKILL.md, then run the inbox-triage playbook on 00-inbox/. Propose the routing as a table and wait for my approval before moving anything.`
- **Produces:** a triage table waiting for you each morning; an inbox that never piles up.

## Weekly — review

- **Cadence:** Friday afternoon
- **Prompt:** `Read SKILL.md, then run the weekly-review playbook. Write the review to reviews/ and send me the bottom line.`
- **Produces:** `reviews/weekly-review-<date>.md` plus a summary, ready before you log off.

## Daily — start-of-day review

- **Cadence:** every weekday, early morning (after the email pull)
- **Prompt:** `Read SKILL.md and memory.md, then run the daily-review playbook. Surface today's priorities in the morning brief.`
- **Produces:** a prioritized "what's on today" brief — inbox status, drafts waiting, top next actions.

## Nightly — workspace sweep (index + hygiene)

- **Cadence:** every night
- **Prompt:** `Read SKILL.md, then run the workspace-sweep playbook. Regenerate map.md, and leave the hygiene fix list for me to approve in the morning — don't move or rename anything unattended.`
- **Produces:** a fresh `map.md` (the dataview replacement, refreshed daily) plus a proposed cleanup list. This is the Obsidian-free version of a live index — materialized once a night.

## Daily — content seeds (optional)

- **Cadence:** daily, late afternoon
- **Prompt:** `Read SKILL.md and memory.md. Review what I produced and captured today across 01-projects/, content/, reviews/, and 02-reference/, and draft 2-3 content seeds (post/article angles) in my voice into 00-inbox/ for me to review.`
- **Produces:** ready-to-edit content angles mined from your own work — the Cowork version of a teaching-moments / daily-content cron.

## Weekly — content pipeline (the flagship)

- **Cadence:** weekly, your publishing day
- **Prompt:** `Read SKILL.md and memory.md, then run the content-pipeline playbook for this week's channels. Leave the drafts in content/ for review — don't publish.`
- **Produces:** a dated content folder with one voice-matched draft per channel (defined in `memory.md` → Content channels), quality-checked and waiting for review. The full version of the daily-content workflow, agnostic and config-driven.

## Weekly — mine for reusable playbooks (optional)

- **Cadence:** weekly
- **Prompt:** `Read SKILL.md. Look at what I did by hand this week across 01-projects/, content/, reviews/, and the inbox. Spot any workflow I repeated and propose skillify-ing it into a new playbook.`
- **Produces:** new-playbook candidates so the OS keeps extending itself — the Cowork version of mine-sessions.

## Weekly — reference refresh (optional)

- **Cadence:** Monday morning
- **Prompt:** `Scan 02-reference/ for anything stale or contradicted by newer material in 01-projects/ or content/. List what you'd update or archive, and wait for approval.`
- **Produces:** a short maintenance list so reference material doesn't rot.

---

## Unattended runs & approval

Cowork proposes a plan and waits for approval before acting. For a scheduled task to be useful while you're away, decide its trust level up front:

- **Gather + propose** (safe default) — pulls inputs in, triages, drafts, and leaves proposals/drafts you review later. Use this for everything above.
- **Auto-run** — only authorize a recurring task to act without per-run approval when its actions are bounded and reversible (e.g. moving inbox items into `02-reference/`).
- **Never unattended** — deleting, overwriting, sending email, or posting. Keep a human in the loop on anything destructive or outbound.

## Designing your own cadence

Good scheduled tasks are: **repeatable** (same shape every time), **bounded** (clear inputs and a clear done state), and **failure-safe** (a missing input produces a "nothing to do" note, not a broken run). Anchor each one to a playbook so the scheduled run and the on-demand run behave identically.
