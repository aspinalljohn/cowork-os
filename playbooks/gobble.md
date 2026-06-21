# Playbook: gobble

**Use when:** you hand me a single rich input — a URL, a pasted chunk, a PDF, a transcript — and want it digested, cross-referenced against what's already here, and filed properly. (The deep-ingest cousin of `inbox-triage`, which is for clearing the inbox in bulk.)

**Inputs:** one source (link, file path, or pasted text).

## Steps

1. Read the source fully. If it's a URL, fetch it via Chrome.
2. **Cross-reference first.** Search `02-reference/`, `01-projects/`, `content/`, and `memory.md` for related material before deciding where this lands — connect it to what already exists, don't create an island.
3. Summarize into structured markdown: a one-line takeaway, the key points, and why it matters to me.
4. Propose a routing plan: destination folder + filename, plus relative-path links to the 2+ related files you found.
5. **Wait for approval**, then write the note and report where it landed.

## Output

A structured note in the proposed destination (usually `02-reference/`), linked to related files by relative path, with a one-line takeaway at the top. Nothing written until I approve the routing.
