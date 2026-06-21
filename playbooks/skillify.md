# Playbook: skillify

**Use when:** I did something useful by hand and want it turned into a reusable playbook, so the workspace gets smarter over time. This is how the OS extends itself.

**Inputs:** a description of the workflow, or a recent session/output to extract it from.

## Steps

1. Identify the repeatable shape: the trigger, the inputs, the steps, and what "done" looks like.
2. Strip out the one-off specifics — keep the generic process.
3. Write a new file in `playbooks/` following the standard format: **Use when / Inputs / Steps / Output**.
4. Add a one-line row to the playbook index in `playbooks/README.md` **and** in `../SKILL.md`, with the invocation phrase.
5. Show me the new playbook and confirm before saving.

## Output

A new `playbooks/<name>.md`, indexed in both the README and the kernel, runnable by name. The OS now does on command what used to be manual.
