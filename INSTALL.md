# Install Guide (start here, no tech experience needed)

This walks you through setting up your own AI operating system in Claude Cowork, step by step. You do not need to know how to code. If you can download a file and click around an app, you can do this. Budget about 15 minutes.

If you get stuck, jump to [Troubleshooting](#troubleshooting) at the bottom.

---

## What you are about to set up

Cowork is Claude running on your computer. It can read and write files in one folder you give it, and do real work for you (research, drafting, triage, reviews). On its own, it does not know how you like to work. This kit is a folder full of instructions and ready-made workflows that teach it. Once installed, you just talk to it in plain English.

You will end up with:
- A folder on your computer that is your "operating system."
- A Cowork project that points at that folder.
- An assistant that already knows your name, your style, and a dozen workflows you can run by name.

---

## Before you start (one-time prerequisites)

1. **A computer** (Mac or Windows).
2. **The Claude desktop app.** Go to [claude.ai/download](https://claude.ai/download), install it, open it, and sign in. Update it to the latest version if it asks.
3. **Cowork turned on.** In the Claude app sidebar, look for **Cowork** and click it. If you do not see it, your account may not have access yet; check [the Cowork help center](https://support.claude.com/en/articles/13345190-get-started-with-claude-cowork).

That is all the software you need. You do **not** need GitHub, "git," a terminal, or any developer tools.

---

## Step 1 — Download the kit

You are getting a folder of files onto your computer. Pick the easy way:

### The easy way (recommended, no tools)

1. Open this link in your web browser: **https://github.com/aspinalljohn/cowork-os**
2. Find the green button near the top that says **`< > Code`**. Click it.
3. In the little menu that drops down, click **Download ZIP**.
4. A file called `cowork-os-main.zip` lands in your **Downloads** folder.
5. Find it and **double-click it to unzip** (Mac does this automatically; on Windows, right-click and choose "Extract All").
6. You now have a folder called `cowork-os-main`. Inside it are files like `SKILL.md`, `memory.md`, and folders like `00-inbox`. That is the kit.

> If you only see a single file and not a folder of files, you double-clicked the `.zip` but did not open the folder it created. Look for the folder, not the zip.

### The technical way (only if you already use git)

```
git clone https://github.com/aspinalljohn/cowork-os.git
```

---

## Step 2 — Put the folder somewhere permanent and name it

1. Move the folder out of Downloads to somewhere you will not accidentally delete it. **Documents** is perfect. So you want something like `Documents/cowork-os-main`.
2. **Rename the folder to your own name.** Right-click the folder, choose Rename, and call it `your-name-os` (all lowercase, use hyphens instead of spaces). Examples: `john-os`, `bobby-os`, `priya-os`.
3. From now on, leave this folder where it is. Cowork will remember its location. If you move it later, you will have to point Cowork at it again.

> **Why rename it?** Out of the box this is "Cowork OS." Making it `john-os` makes it *yours*. We will finish the naming in Step 4 and Step 6.

---

## Step 3 — Create your Cowork project

A "project" in Cowork is a saved workspace pinned to the left sidebar. You are going to make **one** project that points at your whole folder.

1. Open the Claude app and go to **Cowork**.
2. Click **New Project** (look for a `+` near the project list on the left).
3. Choose **Use an existing folder** (not "start from scratch").
4. When it asks you to pick a folder, select the `john-os` folder you renamed in Step 2.
5. Name the project **`John OS`** (use your real name). This is the label you will see in the sidebar.
6. If it asks for access to read and edit files in that folder, click **Allow** (you can choose "Always allow" so it stops asking).

> **Make ONE project for the whole folder. Do not make a separate project for each subfolder** (one for `00-inbox`, one for `01-projects`, and so on). Each Cowork project is sealed off with its own memory, so splitting the folder up breaks the system. One folder, one project. The README explains why in detail.

---

## Step 4 — The most important step: standing instructions + memory

This is the step that makes the assistant actually follow the kit every time, instead of forgetting. Do not skip it.

1. In your project, find the **Instructions** field (when creating the project, or click the pencil / edit icon next to the project later).
2. Copy and paste this in, exactly:

   > At the start of every session, read SKILL.md and memory.md in this project folder and follow them. SKILL.md is my operating kernel: how to behave, where files go, and what never to do. memory.md is my standing facts and corrections.

3. Find the **Memory** toggle for the project and make sure it is turned **ON**.
4. Save.

That is it. Now every new conversation in this project starts by reading your kernel and your facts.

---

## Step 5 — Check that it worked

1. Start a new conversation inside your `John OS` project.
2. Type this and send it:

   > Read SKILL.md and memory.md, then tell me how this workspace is set up and what playbooks are available.

3. It should reply describing your folders (inbox, projects, content, reviews) and listing about a dozen playbooks (inbox-triage, research-brief, weekly-review, and so on).

If it does that, you are installed correctly. If it does not, see [Troubleshooting](#troubleshooting).

---

## Step 6 — Make it yours (let the assistant do the typing)

The kit ships with blanks in square brackets like `[your name]` and `[your timezone]`. You can fill them in by hand, or just let Cowork interview you. In a conversation in your project, paste:

> Read SKILL.md and memory.md. Ask me a handful of questions to personalize this workspace: my name, what I do, my voice and style rules, and the channels I publish to. Then rename the kernel title from "Cowork OS" to "<my name> OS", and fill in every bracketed placeholder in SKILL.md and memory.md with my answers. Show me the changes before saving.

Answer its questions, approve the changes, and your OS is personalized. Five minutes here pays off every session after.

---

## You are done. How to use it day to day

- **Drop something in to work on:** put a file (a PDF, a screenshot, some notes) into the `00-inbox` folder, then tell Cowork `triage my inbox`.
- **Run a workflow by name:** for example `run research-brief on our new pricing` or `run my weekly review`.
- **Where your finished work lands:** project work goes inside that project's own folder in `01-projects`, content goes in `content`, reviews go in `reviews`. There is no messy catch-all pile.
- **Teach it as you go:** when you correct it, say `remember: ...` and it saves that forever.

Tip: drag your `john-os` folder into your Finder sidebar (Mac) or Quick Access (Windows) so dropping files into `00-inbox` is one click.

---

## What you should NEVER rename or delete

Renaming your *OS* (the project, the folder, the title inside SKILL.md) is encouraged. But these are **filenames the system reads by their exact name**. Do not rename or delete them:

- `SKILL.md` (the kernel)
- `memory.md` (your facts)
- `map.md` (the index)
- anything inside the `playbooks` folder

Renaming a *file* breaks things. Renaming your *OS* does not. If in doubt, leave filenames alone and only change the words *inside* them.

---

## Troubleshooting

**"It does not seem to know about the playbooks or folders."**
You probably skipped Step 4. Open the project's Instructions field, paste the standing instruction, turn the Memory toggle ON, and start a fresh conversation.

**"It cannot find SKILL.md / says the folder is empty."**
The project is pointed at the wrong folder, or at the zip instead of the unzipped folder. Re-check Step 3 and make sure you selected the `john-os` folder that contains `SKILL.md`, not the `.zip` file.

**"It is asking permission every time."**
When the permission box appears, choose **Always allow** for this folder.

**"A new file called `claude.md` appeared in my folder."**
That is normal. Cowork writes some of its own memory there automatically. It works alongside your `memory.md`. Leave both in place.

**"I moved the folder and now it is broken."**
Cowork remembered the old location. Create the project again (Step 3) pointing at the folder's new location, and redo Step 4.

**"I want to start over."**
Delete the Cowork project (this does not delete your files), then redo from Step 3. Your folder and its contents stay put.

---

Questions or something unclear? The main [README](README.md) has the deeper "why" behind each piece.
