# Cowork OS — Starter Kit

A clone-and-run operating system for **Claude Cowork** (Anthropic's desktop agent). Point Cowork at this folder and it has a predictable place to read inputs, do work, and file finished deliverables — plus a kernel of operating rules and a library of reusable playbooks.

Built for **general knowledge work**: research, drafting, analysis, triage, reviews. Not tied to any one industry.

> **New to this / not technical?** Follow the step-by-step **[INSTALL.md](INSTALL.md)** instead — it assumes zero tech experience and walks you through every click. The setup steps below are the quick version.

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

## Step 1 — Get the files onto your computer

Cowork works on files on your own machine, so the workspace folder has to live on your computer. There's no "install from a link" — you download it once, then point Cowork at it. Two ways:

- **Download (no tools needed):** open [the repo on GitHub](https://github.com/aspinalljohn/cowork-os) → click the green **`Code`** button → **Download ZIP** → unzip it. You now have a `cowork-os` folder.
- **Clone (if you use git):** `git clone https://github.com/aspinalljohn/cowork-os.git`

Put the folder somewhere permanent (e.g. `~/Documents/`). This folder *is* your operating system — don't move it around after setup.

## Step 2 — Make it *your* OS (name it)

Out of the box it's called "Cowork OS." Make it yours — "John OS," "Bobby OS," whatever your name is. The name lives in **three** places:

1. **The folder** → rename `cowork-os` to `john-os` (lowercase, hyphens, no spaces).
2. **The Cowork project** → when you create it in Step 3, name it **`John OS`**. This is the label you'll see in the sidebar.
3. **The kernel title** → open `SKILL.md`, change the first heading `# Cowork OS — Kernel` to `# John OS — Kernel`, and put your name under **Who I am**.

> ⚠️ **Rename the project, the folder, and the titles — never the files.** `CLAUDE.md`, `SKILL.md`, `memory.md`, `map.md`, and everything in `playbooks/` are read by their exact filenames. Renaming a *file* breaks the system; renaming your *OS* (project + folder + title) does not.

## Step 3 — Point Cowork at the folder

1. **Get Cowork.** Install Claude Desktop, update to the latest version, switch to **Cowork** in the sidebar.
2. **Open your folder in Cowork** → either **Work in a folder** and select your `john-os` folder, or create a **Project** from it (New Project → Use an existing folder). Either works. Use **one** workspace for the whole folder — *not* a separate one per subfolder ([why](#why-one-workspace-not-one-per-folder)).
3. **That's it — it loads itself.** This folder includes a `CLAUDE.md` file, which Cowork reads automatically at the start of every session. `CLAUDE.md` tells it to load the kernel (`SKILL.md`) and your facts (`memory.md`), so the OS is live without any manual priming.
4. **Check it worked.** Start a conversation and ask: `Tell me how this workspace is set up and what playbooks are available.` It should describe your folders and list the playbooks. If it does, you're wired.

> **Optional, Projects only (extra reliability):** if you made a Project, you can also paste `At the start of every session, read CLAUDE.md and follow it` into the project's **Instructions** field and switch the **Memory** toggle **ON**. Not required — `CLAUDE.md` already handles loading — but it's a belt-and-suspenders backup.

## Step 4 — Personalize it (let Cowork do the typing)

The kit ships with `[bracketed]` placeholders for your voice, defaults, and standing facts. Fill them in by hand in `SKILL.md` and `memory.md` — **or paste this into Cowork and let it interview you:**

```
Read SKILL.md and memory.md. Ask me a handful of questions to personalize this
workspace — my name, what I do, my voice/style rules, and the channels I publish to.
Then rename the kernel title to "<my name> OS", and fill in every [bracketed]
placeholder in SKILL.md and memory.md with my answers. Show me the changes before saving.
```

Five minutes here pays off every session after. Then drop a file in `00-inbox/` and say `triage my inbox`, or run any playbook by name.

---

## Why one workspace, not one per folder

**Point Cowork at the whole folder once — don't carve it into a separate workspace per subfolder.**

When Cowork works in a folder (whether as a quick "Work in a folder" session or a saved Project), it automatically sees every subfolder and file inside it — no file picker. So one workspace at the root reaches everything.

- **Do:** point it at this folder **root** (the one holding `CLAUDE.md`, `SKILL.md`, and `memory.md`). That root *is* your OS — it reaches `00-inbox/`, `01-projects/`, `content/`, `reviews/`, everything, and `CLAUDE.md` loads the kernel automatically.
- **Don't:** make a separate Project for `00-inbox/`, another for `01-projects/`, etc. Each Cowork **Project** is an isolated context with its own memory — a per-folder Project can't see `CLAUDE.md`/`SKILL.md`/`memory.md` at the root, so nothing loads and every cross-folder playbook breaks (inbox-triage routes inbox→projects; recall and workspace-sweep scan all folders). One workspace = one folder, the same way a second brain is one vault, not eleven.

**Seeing and browsing the folders:** the sidebar shows the workspace, not a full file tree. For visual file browsing, pin the folder root to your **Finder sidebar** — it's all plain folders on disk. For an at-a-glance index of what's where, ask Cowork to refresh `map.md` (the `workspace-sweep` playbook) and read that.

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
| `CLAUDE.md` | The loader Cowork auto-reads first, every session. Boots the kernel. |
| `SKILL.md` | The kernel: identity, folder map, operating rules, voice, playbook index. |
| `memory.md` | Your standing facts, decisions, corrections. Read every session. |
| `map.md` | Materialized index of the workspace (the dataview replacement). |

Deliverables live **with their subject** → project work in its project folder, content in `content/`, reviews in `reviews/`. There's deliberately no generic "outputs" bin; the routing rule in `SKILL.md` keeps work and its output together.

Coming from an Obsidian / second-brain setup? `FROM-SECOND-BRAIN.md` maps exactly what ports over and what you drop.

Want to see it running before you set up your own? `examples/` is a filled-in workspace for a fictional persona — model your `memory.md` on `examples/memory.md` and skim the sample outputs to see what each playbook produces.

## Extending it

- **Add a playbook** → copy any file in `playbooks/`, rewrite the steps, add a one-line entry to the playbook index in `SKILL.md`. Done.
- **Add a folder** → create it, then add a row to the folder map in `SKILL.md` so Cowork knows its purpose.
- **Promote a playbook to a Cowork skill** → move it into its own folder as `SKILL.md` if your Cowork version auto-discovers nested skills.

> Cowork is a fast-moving product. `CLAUDE.md` is the file it auto-reads at the start of every session — that's what boots the kernel. If a future version uses a different auto-loaded filename, rename `CLAUDE.md` accordingly (the bootstrap content is what matters). `SKILL.md` and the rest can keep their names.
