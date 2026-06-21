# Playbook: daily-review

**Use when:** start of day — you want a prioritized picture of what needs attention. Forward-looking (vs `weekly-review`, which is the retrospective). Good scheduled task.

**Inputs:** current state of `00-inbox/`, `01-projects/`, `content/`, `reviews/`. Email/calendar via connectors if granted.

## Steps

1. Check the inbox for anything untriaged.
2. Scan active projects for open threads and anything marked due or in progress.
3. List drafts sitting in project folders, `content/`, or `reviews/` that are waiting on me (review, send, publish).
4. If calendar/email are connected, pull today's meetings and anything that needs a same-day reply.
5. Produce **Today** — 3 to 5 prioritized items, each with the single next action.

## Output

A short "what's on today" list surfaced in chat (and optionally written to `reviews/daily-review-<YYYY-MM-DD>.md`): inbox status, drafts waiting, top priorities with next actions.
