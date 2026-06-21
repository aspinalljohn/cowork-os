# Playbook: inbox-triage

**Use when:** `00-inbox/` has accumulated raw items and you want them summarized, classified, and routed out.

**Inputs:** everything currently in `00-inbox/`.

## Steps

1. List every item in `00-inbox/`. For each, read enough to understand what it is.
2. For each item, produce a one-line summary and classify it:
   - **Reference** → durable material to keep → propose moving to `02-reference/`.
   - **Project input** → belongs to active work → propose moving into the right `01-projects/<project>/` (or a new project folder).
   - **Actionable** → needs a deliverable → propose which playbook produces it.
   - **Archive** → no longer useful → propose moving to `99-archive/`.
3. Present the full triage as a table: item, one-line summary, classification, proposed destination.
4. **Wait for approval.** Then move the approved items and report what's left.

## Output

A triage table shown in chat, plus the approved moves executed. `00-inbox/` should be measurably emptier. Nothing finished is left in the inbox.
