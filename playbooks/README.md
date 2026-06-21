# Playbooks

Reusable workflows. Each file is a self-contained process Cowork runs when you invoke it by name. The kernel (`../SKILL.md`) indexes them and tells Cowork to prefer a matching playbook over improvising.

| Playbook | Invoke with |
|---|---|
| [inbox-triage](inbox-triage.md) | `triage my inbox` |
| [research-brief](research-brief.md) | `run research-brief on <topic>` |
| [weekly-review](weekly-review.md) | `run my weekly review` |
| [meeting-notes](meeting-notes.md) | `run meeting-notes on <file>` |
| [document-draft](document-draft.md) | `run document-draft: <what>` |
| [gobble](gobble.md) | `gobble this: <source>` |
| [recall](recall.md) | `recall <topic>` |
| [remember](remember.md) | `remember: <fact>` |
| [skillify](skillify.md) | `skillify this` |
| [daily-review](daily-review.md) | `run my daily review` |
| [workspace-sweep](workspace-sweep.md) | `sweep the workspace` |
| [content-pipeline](content-pipeline.md) | `run the content pipeline` |

## Writing your own

Copy any file here, keep the four sections (**Use when / Inputs / Steps / Output**), rewrite the steps, then add a one-line row to the playbook index in `../SKILL.md`. A good playbook is specific about *where the output lands* and *what done looks like*.
