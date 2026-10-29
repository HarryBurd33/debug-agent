# Debug Agent

A globally installable Codex skill that scopes bugs, reproduces failures,
identifies causes, applies authorized focused repairs and verifies regressions.
Includes pause, checkpoint/resume and hook debugging workflows. Version 0.1.4
distinguishes task-checkpoint 0.8 direct limits from historical 0.7 pause recovery.

## Install for your user

Requires Git and a local Codex installation. In Terminal on macOS or Linux:

```sh
mkdir -p "$HOME/.agents/skills"
git clone https://github.com/HarryBurd33/debug-agent.git "$HOME/.agents/skills/debug-agent"
```

In PowerShell on Windows:

```powershell
New-Item -ItemType Directory -Force (Join-Path $HOME ".agents/skills") | Out-Null
git clone https://github.com/HarryBurd33/debug-agent.git (Join-Path $HOME ".agents/skills/debug-agent")
```

This installs the repository itself as the skill folder: SKILL.md must be at
.agents/skills/debug-agent/SKILL.md beneath your user home. If that destination
already exists, inspect it before proceeding; do not overwrite a customized skill
or create a second competing copy under another skill root.

Open a new Codex turn after installing. If an existing chat has not refreshed its
skill list, reopen the chat or restart Codex. Installation applies to local Codex
sessions on this computer; other devices or hosted environments need their own
installation.

## Use from any project

```text
Use $debug-agent to investigate and fix [problem] in [project].
Expected behavior: [what should happen].
```

For example:

```text
Use $debug-agent to diagnose why this task remains paused after quota recovers.
Preserve legitimate stops and the existing task owner.
```

The skill entry point routes to AGENT.md, PLAYBOOK.md, agent.json and the local
adapter/toolbox. It uses the current chat model and tools. Verify host capabilities
and repair authority on invocation; the portable configuration starts as draft.
Keep case outputs in the target workspace, outside the installed skill folder.

If skill discovery is unavailable, ask the agent to read the absolute path to the
installed SKILL.md and follow it. The repository also works as a manually read
agent package without global installation.

## Update

When your installed clone has no custom changes:

```sh
git -C "$HOME/.agents/skills/debug-agent" pull --ff-only
```

PowerShell:

```powershell
git -C (Join-Path $HOME ".agents/skills/debug-agent") pull --ff-only
```

Inspect local changes first and preserve customizations before updating. To pin a
reviewed version, check out its full commit hash in the installed clone. Refresh
the Codex skill list with a new turn after an update.

## Remove

Remove only your user skill folder .agents/skills/debug-agent after preserving
any local customizations. Task outputs, checkpoints and ownership data stay in
their original target workspaces and should be retained.

## Workflow and limits

Scope → reproduce → freeze checks → diagnose → repair → verify → save lessons.

Each case records the original failure, source versions, acceptance criteria,
before/after evidence, preservation checks and rollback. The toolbox contains
generic cases and a run-review template. Defaults are three attempts, 30 minutes,
one writer, no delegation and no paid API execution.

This skill starts no background service or schedule, installs no hooks or
checkpoint runtime, and grants no extra permissions. Private incident records,
account settings, chat IDs and project backups are excluded from this repository.
See [VALIDATION.md](VALIDATION.md) for verification limits.

## License

[MIT](LICENSE), copyright 2026 HarryBurd33.
