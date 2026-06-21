# Porting a second brain off Obsidian

This kit is the Obsidian-free port of a markdown second-brain system. If you run a vault today, here's exactly what carries over and what you drop — and why dropping it costs you nothing.

## The realization

A "second brain" feels like one system, but it's really three layers stacked:

1. **The editor/index** (Obsidian) — stores markdown, links notes, auto-generates indexes (dataview), draws a graph.
2. **The agent** (a coding agent + its skills, hooks, and memory).
3. **The scheduler** (OS cron — launchd, Task Scheduler — running jobs unattended).

Cowork collapses three layers into two: **Cowork** is the agent *and* the scheduler, and **plain folders** are the storage. The only thing left to replace is what the editor uniquely did.

## What ports cleanly (the load-bearing stuff)

| Second-brain piece | Lives here as |
|---|---|
| Tool-agnostic memory file | `memory.md` — read every session |
| Skills (ingest, extract, recall, remember, sweep, review) | `playbooks/` |
| Cron jobs (nightly sweep, morning pull, content runs) | Cowork scheduled tasks (`schedules/scheduled-tasks.md`) |
| Session-end logging hook | An end-of-day scheduled "log what changed" task |
| Routing folders (route by subject, not lifecycle) | `00-inbox/` → `01-projects/` (work + its deliverables) → `02-reference/`, `content/`, `reviews/` → `99-archive/`. Deliverables live with their subject, mirroring the vault's domain routing — not piled in one outputs bin. |
| Naming + voice conventions | The kernel (`SKILL.md`) |

Notice: the highest-value parts were never Obsidian-specific. A memory file is just markdown. A skill is just a documented process. Cron is just a schedule.

## What you drop (and the replacement)

| Obsidian feature | Why it doesn't survive | What replaces it |
|---|---|---|
| **Dataview** (live auto-indexes) | It's a plugin query engine; nothing outside Obsidian runs it | `map.md`, a *materialized* index Cowork regenerates on a schedule via `workspace-sweep`. Refreshed nightly instead of live — same answer, one day's lag at most. |
| **`[[wikilinks]]`** | Obsidian-specific link syntax + backlink graph | Relative-path markdown links (work in any editor) plus the index. You navigate by folders + `map.md`, not a graph. |
| **Graph view** | Pretty, rarely load-bearing | Nothing. You won't miss it. The index answers "what's related" better than a hairball does. |

## The honest trade

You give up *live* indexes and a visual graph. You gain a system that runs in one app, schedules its own work, and that **any** agent can read — because it's all plain files and documented processes, not a plugin stack. For an operator who wants the workflows, not the visualization, that's a straight upgrade.
