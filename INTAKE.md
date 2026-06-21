# Getting work in — capture & automation

Two ways work enters this workspace: **you push files in**, or **Cowork pulls them in for you**. The entry point for both is `00-inbox/`, and the first move is always the `inbox-triage` playbook.

---

## Push — you drop files into `00-inbox/`

`00-inbox/` is a normal folder, so anything that can save a file can feed it. Make it effortless:

- **Pin it.** Drag `00-inbox/` into your Finder sidebar (Mac) or Quick Access (Windows) favorites. One click to drop things.
- **Make it a default save spot.** Point browser downloads — or your "Save as" muscle memory — at `00-inbox/` for things you grab on the fly.
- **From your phone.** Map `00-inbox/` to a cloud-synced folder (iCloud Drive, Dropbox, or Google Drive desktop sync). Save to it from your phone's share sheet; it lands on the desktop for Cowork.
- **Screenshots & quick notes.** Same idea — save into `00-inbox/`, then say `triage my inbox`.

## Pull — Cowork fetches inputs for you

The real unlock: you don't move files at all. With connectors granted (email, Slack, Chrome), a **scheduled task** reads those sources on a cadence and drops what matters into `00-inbox/` — then triages it. Examples (full prompts in `schedules/scheduled-tasks.md`):

- Every morning, read new emails labeled `cowork`, save their attachments into `00-inbox/`, and triage.
- Every hour, pull files shared in Slack `#intake` into `00-inbox/`.
- Daily, gather the links you flagged into a single reading list in `00-inbox/`.

You sit down to an inbox that filled and pre-sorted itself.

## The honest limits

- **Cadence, not triggers.** Cowork automations run on a schedule (every morning, hourly). A task *checks* the inbox/connectors and acts — it doesn't fire the instant a file appears. For true the-moment-it-lands behavior, pair with an OS-level automation (macOS Folder Actions, Hazel, or a Power Automate flow) that moves files into `00-inbox/`. Optional booster, not required.
- **Unattended runs need trust.** Cowork proposes a plan and waits for approval. For a scheduled task to work while you're away, decide its trust level — see *Unattended runs & approval* in `schedules/scheduled-tasks.md`. Safe default: automations **gather and propose**; you approve anything consequential.
