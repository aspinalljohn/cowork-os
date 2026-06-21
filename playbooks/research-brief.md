# Playbook: research-brief

**Use when:** you need a sourced, decision-ready brief on a topic or question — not a wall of links.

**Inputs:** the topic/question, plus any seed files in `00-inbox/` or `02-reference/`. Web access via Chrome if granted.

## Steps

1. Restate the question in one line and confirm scope (what decision this informs, how deep to go). If scope is unclear, ask before researching.
2. Gather from the best available sources: reference files first, then web. Prefer primary/authoritative sources over aggregators.
3. Cross-check key claims against a second source. Flag anything you could only find once as **unverified**.
4. Synthesize — don't dump. Lead with the answer, then the reasoning, then the evidence.
5. Write the brief **inside the project it informs**: `01-projects/<project>/research-brief-<topic>-<YYYY-MM-DD>.md`. If it's standalone (not tied to existing work), create a project-of-one folder for it: `01-projects/<topic-slug>/research-brief-<YYYY-MM-DD>.md`. Ask which project if it's unclear.

## Output

A markdown brief inside the relevant `01-projects/<project>/` folder with:
- **Bottom line** — the answer in 2-3 sentences.
- **Key findings** — bulleted, each with a source link.
- **What's uncertain** — open questions, conflicting evidence, unverified claims.
- **Sources** — full list of URLs/files used.
