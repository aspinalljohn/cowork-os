# Playbook: workspace-sweep

**Use when:** keeping the workspace healthy — refresh the index and catch drift. This does two jobs Obsidian used to: it **regenerates `map.md`** (the dataview replacement) and **runs hygiene** (the librarian-sweep equivalent). Run it on a nightly schedule.

**Inputs:** the whole workspace.

## Steps

1. **Refresh the index.** Scan `01-projects/`, `content/`, `reviews/`, `00-inbox/`, `02-reference/` and rewrite `map.md`: active projects (with each one's latest deliverable), recently produced files across projects/content/reviews (newest first), inbox count, key reference files. Update the "Last refreshed" line with today's date.
2. **Flag hygiene issues** — don't fix silently, propose them:
   - Inbox rot: items sitting in `00-inbox/` more than a few days.
   - Naming violations: files not lowercase-hyphenated, or time-bound files missing a date.
   - Stale items: finished projects that should move to `99-archive/` (whole folder, deliverables included).
   - Broken relative links: links pointing at files that moved or were renamed.
   - Misrouted deliverables: finished work sitting loose in `00-inbox/`, or a project's deliverable saved outside its project folder.
3. Present the hygiene findings as a fix list. **Wait for approval** before moving, renaming, or relinking anything.

## Output

A freshly rewritten `map.md`, plus a proposed fix list in chat. The index regenerates unattended; the fixes wait for me. (Safe to run on a schedule — see `../schedules/scheduled-tasks.md`.)
