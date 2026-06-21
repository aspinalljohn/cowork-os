# Playbook: inbox-triage

**Use when:** `00-inbox/` has accumulated raw items and you want them summarized, classified, and routed out.

> **"Inbox" here means the `00-inbox/` FOLDER in this workspace — not email/Gmail.** Even if an email connector is available, do not read email for this playbook unless I explicitly say "email" or "Gmail." (Email only enters through a separate scheduled email-pull task that drops messages *into* `00-inbox/` first.)

**Inputs:** everything currently in the `00-inbox/` folder.

## Steps

1. List every item in the `00-inbox/` folder. For each, read enough to understand what it is.
2. For each item, produce a one-line summary and classify it:
   - **Reference** → durable material to keep → propose moving to `02-reference/`.
   - **Project input** → belongs to active work → propose moving into the right `01-projects/<project>/` (or a new project folder).
   - **Actionable** → needs a deliverable → propose which playbook produces it.
   - **Archive** → no longer useful → propose moving to `99-archive/`.
3. Present the full triage as a table: item, one-line summary, classification, proposed destination.
4. **Wait for approval.** Then move the approved items and report what's left.

## Output

A triage table shown in chat, plus the approved moves executed. `00-inbox/` should be measurably emptier. Nothing finished is left in the inbox.
