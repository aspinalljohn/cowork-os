# Cowork OS — Starter Kit

A clone-and-run operating system for **Claude Cowork** (Anthropic's desktop agent). Point Cowork at this folder and it has a predictable place to read inputs, do work, and file finished deliverables — plus a kernel of operating rules and a library of reusable playbooks.

Built for **general knowledge work**: research, drafting, analysis, triage, reviews. Not tied to any one industry.

---

## What Cowork is (and why this exists)

Cowork is Claude running on your desktop. You **"Work in a folder"**, grant it connectors (Chrome, Slack, email), and describe an outcome. It proposes a plan, waits for your approval, then works across your files and apps until the deliverable is done. You can also set **scheduled tasks** so it runs on a cadence ("every Friday, pull metrics and draft the weekly review").

The problem: a blank folder gives Cowork no conventions. It doesn't know where outputs go, what your voice is, or which workflows you run repeatedly. So every session starts from zero.

**Cowork OS fixes that.** It gives Cowork:
1. A **workspace map** — predictable folders for inputs, work, reference, and outputs.
2. A **kernel** (`SKILL.md`) — the operating rules Cowork reads every time: how to behave, where things go, what to never do.
3. A **playbook library** — your repeatable workflows, written once, invoked by name.
4. A **cadence layer** — the recurring tasks worth scheduling.

---

## 5-minute setup

1. **Get Cowork.** Install Claude Desktop, update to the latest version, switch to **Cowork** mode in the sidebar.
2. **Drop this folder** wherever you want your workspace to live (e.g. `~/Documents/cowork-os`).
3. In Cowork, click **"Work in a folder"** and select this folder. Cowork is now sandboxed to it.
4. **Prime the kernel.** First message: `Read SKILL.md and memory.md, then tell me how this workspace is set up and what playbooks are available.` Cowork loads the operating rules + your memory and confirms it understands the map. (A `SKILL.md` in the working folder is persistent context — Cowork remembers it every session.)
5. **Make it yours.** Fill in the `[bracketed]` placeholders in `SKILL.md` (your voice, defaults) and `memory.md` (your standing facts). Five minutes here pays off every session after.

That's it. Drop a file in `00-inbox/` and say `triage my inbox`, or run any playbook by name.

---

## Setting it up in the Cowork app (read this first)

**Make ONE project for the whole workspace — not one per folder.**

In Cowork, a "project" is a self-contained workspace with its *own* files, instructions, **and memory**, pinned to the left sidebar. When a project points at a folder, Cowork automatically sees every subfolder and file inside it — no file picker.

- **Do:** New Project → **Use an existing folder** → point it at this workspace **root** (the folder holding `SKILL.md` and `memory.md`). That one project *is* your OS. It appears once in the sidebar and reaches `00-inbox/`, `01-projects/`, `content/`, `reviews/`, everything.
- **Don't:** make a separate project for `00-inbox/`, another for `01-projects/`, etc. Each Cowork project is an **isolated** context with its own memory — so a per-folder project can't see `SKILL.md`/`memory.md` at the root, and every cross-folder playbook breaks (inbox-triage routes inbox→projects; recall and workspace-sweep scan all folders). One workspace = one project, the same way a second brain is one vault, not eleven.

**Seeing and browsing the folders:** the sidebar shows the *project*, not a full file tree. For visual file browsing, pin the workspace root to your **Finder sidebar** — it's all plain folders on disk. For an at-a-glance index of what's where, ask Cowork to refresh `map.md` (the `workspace-sweep` playbook) and read that.

---

## How to use it day to day

- **Capture** → drop files into `00-inbox/` (pin it to your Finder sidebar), or let Cowork pull them from email/Slack for you. See `INTAKE.md`.
- **Work** → say `run research-brief on <topic>` or `triage my inbox`. Cowork proposes a plan, you approve, it works.
- **Find outputs** → deliverables live *with their subject*: project work in `01-projects/<project>/`, content in `content/`, reviews in `reviews/`. No catch-all bin — see the routing rule in `SKILL.md`.
- **Automate** → schedule both intake (pull inputs in) and processing (triage, review) so the workspace runs itself. See `schedules/scheduled-tasks.md`.

## The folder map

| Folder | What lives here |
|---|---|
| `00-inbox/` | Raw, untriaged inputs. Transient — gets routed out. |
| `01-projects/` | Active work **and its finished deliverables**, one folder per project. |
| `02-reference/` | Durable source material Cowork reads (specs, notes, knowledge base). |
| `content/` | Recurring content drafts (the content-pipeline stream), one dated folder per run. |
| `reviews/` | Daily and weekly reviews, dated. |
| `99-archive/` | Completed or dormant material. |
| `playbooks/` | Reusable workflows, one file each. Invoke by name. |
| `schedules/` | Cadence definitions for recurring scheduled tasks. |
| `memory.md` | Your standing facts, decisions, corrections. Read every session. |
| `map.md` | Materialized index of the workspace (the dataview replacement). |

Deliverables live **with their subject** → project work in its project folder, content in `content/`, reviews in `reviews/`. There's deliberately no generic "outputs" bin; the routing rule in `SKILL.md` keeps work and its output together.

Coming from an Obsidian / second-brain setup? `FROM-SECOND-BRAIN.md` maps exactly what ports over and what you drop.

Want to see it running before you set up your own? `examples/` is a filled-in workspace for a fictional persona — model your `memory.md` on `examples/memory.md` and skim the sample outputs to see what each playbook produces.

## Extending it

- **Add a playbook** → copy any file in `playbooks/`, rewrite the steps, add a one-line entry to the playbook index in `SKILL.md`. Done.
- **Add a folder** → create it, then add a row to the folder map in `SKILL.md` so Cowork knows its purpose.
- **Promote a playbook to a Cowork skill** → move it into its own folder as `SKILL.md` if your Cowork version auto-discovers nested skills.

> Cowork is a fast-moving product. If your version uses a different persistent-context filename than `SKILL.md`, rename the kernel accordingly — the structure is what matters, not the filename.
