# Playbook: meeting-notes

**Use when:** you have a transcript or raw notes and want clean, structured notes plus action items.

**Inputs:** a transcript or notes file (path in `00-inbox/` or named directly).

## Steps

1. Read the source. Identify attendees, the purpose, and the date.
2. Extract: **decisions made**, **key discussion points**, **open questions**, **action items** (with owner and any due date when stated).
3. Don't invent owners or dates. If an action item has no clear owner, mark it `owner: unassigned`.
4. Preserve substance over polish — capture what was actually said, not a sanitized version.
5. Write the notes **inside the project/client they belong to**: `01-projects/<project>/meeting-notes-<topic>-<YYYY-MM-DD>.md` (create a project-of-one folder if the meeting isn't tied to existing work).

## Output

A dated notes file inside the relevant `01-projects/<project>/` folder with sections: **Summary** (3 lines), **Decisions**, **Discussion**, **Open questions**, **Action items** (checkbox list with owners). Action items surfaced in chat so nothing gets buried.
