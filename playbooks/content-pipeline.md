# Playbook: content-pipeline

**Use when:** turn your own work and notes into a batch of publish-ready drafts, in your voice, on a cadence. This is the flagship workflow — multi-step and scheduled-friendly. It's fully agnostic: it reads *which* channels and formats you want from `memory.md`, so it works for any creator or operator without naming a single platform in the playbook itself.

**Inputs:** recent deliverables across `01-projects/`, prior content in `content/`, durable material in `02-reference/`, ideas captured in `00-inbox/`, and your **Content channels** list in `memory.md`. Optional: a publishing connector.

## Steps

1. Read `memory.md` for the **voice rules** and the **Content channels** list (what to produce, length, cadence). If no channels are defined, ask me to name them once, then proceed.
2. Gather source material: this period's outputs, ideas captured in the inbox, and reference worth resurfacing. Pick the 1-2 strongest angles — quality over volume; don't manufacture filler to fill a channel.
3. For each channel, draft the piece **in my voice**: lead with the hook, one idea per piece, formatted to that channel's length.
4. Self-check every draft against the bar:
   - Is the point in the first two lines?
   - One idea, not five?
   - Does it sound like me, not generic AI?
   - Any unverified claim flagged `[CHECK]` rather than asserted?
5. Write drafts to `content/<YYYY-MM-DD>/`, one file per channel. Summarize each in one line.
6. **Publish only if I've explicitly authorized this run** to use a connector. Otherwise leave the batch for review.

## Output

A dated folder in `content/` with one voice-matched, quality-checked draft per channel, `[CHECK]`-flagged where uncertain, waiting for review. Published only on explicit authorization.

> Define your channels once in `memory.md` under **Content channels** (e.g. "LinkedIn post — ~150 words, weekly"). Change them there and this playbook adapts — no edits here.
