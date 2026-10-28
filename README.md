# Debug Agent

A manual debugging agent that scopes symptoms, reproduces failures, finds causes,
applies authorized focused repairs and verifies regressions. Includes pause,
checkpoint/resume and hook debugging workflows.

## Use

Clone this repository, then ask your coding agent:

    Read /absolute/path/to/debug-agent/AGENT.md and follow its playbook.
    Investigate and fix [symptom] in [project].
    Expected behavior: [what should happen].

It reads PLAYBOOK.md, agent.json, adapters/codex.md and toolbox/index.json.
It uses the model/tools of the invoking chat. Configuration starts as draft;
verify current host capabilities and repair authority before execution.

## Workflow

Scope → reproduce → freeze checks → diagnose → repair → verify → save lessons.

Each case records original failure, versions, fixed acceptance, evidence,
preservation checks and rollback. Generic cases and a run-review template are
in toolbox/. Defaults: three attempts, 30 minutes, one writer, no delegation,
and no paid API execution.

This repository contains reusable instructions/templates. Private incident
records, account settings, chat identifiers, project backups and machine-specific
scripts are excluded. It contains no checkpoint runtime and installs no global
skill, background service or schedule. See VALIDATION.md for verification limits.
