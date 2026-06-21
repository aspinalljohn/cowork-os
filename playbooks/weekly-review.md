# Playbook: weekly-review

**Use when:** end of week — you want the week pulled together and next week's priorities set. Good candidate for a scheduled task (see `../schedules/scheduled-tasks.md`).

**Inputs:** this week's items across `00-inbox/`, `01-projects/`, `content/`, and `reviews/`. Email/Slack/calendar via connectors if granted.

## Steps

1. Scan what changed this week: new inbox items, project movement, deliverables produced across `01-projects/`, `content/`, and `reviews/`.
2. If connectors are granted, pull supporting signal (unanswered email threads, calendar for next week, open Slack items).
3. Summarize: **what shipped**, **what stalled**, **what's still open**.
4. Propose next week's priorities — 3 to 5, ranked, each with the first concrete next step.
5. Write to `reviews/weekly-review-<YYYY-MM-DD>.md` and give me the bottom line in chat.

## Output

A dated review in `reviews/` with three sections — **Shipped**, **Stalled / Open**, **Next week (ranked)** — plus a one-paragraph summary surfaced in chat.
