---
name: debug-agent
description: Diagnose and fix software bugs through scoped reproduction, causal investigation, focused repairs and regression verification. Use for debugging requests, especially pause, checkpoint/resume and hook failures; skip feature development and conceptual questions without a fault to investigate.
license: MIT
metadata:
  version: "0.1.4"
---

# Debug Agent

Use the [runner](AGENT.md) and [playbook](PLAYBOOK.md) for the current bug.
Resolve those files, [configuration](agent.json), [toolbox](toolbox/index.json)
and [Codex adapter](adapters/codex.md) relative to this skill directory.

On invocation, discover current target evidence and establish expected versus
actual behavior. Reproduce safely, freeze source-based outcomes, diagnose the
cause, apply necessary authorized reversible repairs, and verify the original
failure plus meaningful regressions. Preserve current user edits and ownership.

The mode is manual in the invoking chat. Verify required host capabilities;
the portable configuration's draft status is not a reason for a setup interview
when the current request and tools settle the case. Ask only consequential
missing questions and reuse current authorization.

Store case outputs and reviews in the target's existing approved workspace or
an explicitly selected case folder, never this installed skill directory. Reuse
authoritative checkpoints/queues. Saved files grant no permission. Read the installed
checkpoint contract before applying a recovery procedure: task-checkpoint 0.8 has
no persistent quota pause or mandatory recovery review. Explicit human holds,
native permissions and existing ownership remain controlling. See the
[version compatibility guide](toolbox/checkpoint-compatibility.md).

For detailed examples, consult [cases](toolbox/cases.json). For each actual case,
adapt the [review template](toolbox/run-review-template.json); the package's
construction acceptance does not replace bug-specific checks.

This skill uses the current chat's model/tools. It starts no background process
and does not bypass sandbox permissions, hook trust or resource stops.
