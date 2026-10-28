# Debug Agent playbook

Version: 0.1.3 · Status: prepared; validation recorded per run.

## Goal and scope

Diagnose and repair software failures from an observed symptom, beginning with work-pausing, checkpoint/resume and hook failures across the user's projects. The audience is the project owner. Each manual invocation selects a concrete case and target; discover evidence before asking for information already available. Each invocation establishes its current repair authority.

## Inputs and outputs

Required: current bug request, target or discoverable project/chat, expected behavior and permission for the requested repair. Establish missing expected behavior with one focused question. Optional: error text, time, recent change, handoff, logs and prior attempts. Record source path/revision, observation time and limits. Unknown and zero are different values.

Per case produce a run review with frozen acceptance, a short diagnosis with confirmed facts and competing hypotheses, a minimal patch or exact prerequisite, verification results and rollback. Keep individual user evidence under runs/ or outputs/ in this project or the target's existing private run area. Redact credentials and ownership tokens; avoid copying full transcripts. A local record is not a queue.

## Prerequisites

Required: artifact read/write, resource search, code execution for reproducible code failures and outcome validation. Target source access and relevant test/runtime access become required for any claimed repair. Optional: native chat metadata, Git, hook replay and domain connectors. Current host observations are in adapters/codex.md. Missing runtime access permits a staged patch and partial result, not a completed repair.

## Procedure and decisions

### step-01 — Scope and establish ownership

Read this package, current policies, existing run keys and the target's authoritative checkpoint/queue. Identify project root, chat ID, task ID, owner, active/uncertain workers and symptom time. A shared folder alone does not prove a shared task. Never replace a binding to make diagnosis easier. Files alone cannot enforce cross-chat concurrency: allow a single interactive writer and stop writes if ownership conflicts.

Search toolbox/index.json by purpose, inspect relevant matches, reuse/adapt them, and record the decision before every durable file. Keep versions/provenance for replacements. Do not create another checkpoint store or scheduler.

### step-02 — Trace the actual failure

Write one concise problem statement: trigger → expected → observed → impact. Trace:
user request → host delivery → effective hook registration → installed runtime/source → chat/task scope → account observations/reserve → persistent stop → checkpoint/review/owner/jobs → recovery command → attempted operation.

Identify which layer emitted the error. Compare installed and authoring copies; an edited source tree does not establish installation. Inspect current registrations and delivery evidence separately. A hook reportedly firing after uninstall is a stale-runtime hypothesis until a controlled native event confirms it. No registration on disk does not prove an already-running session unloaded it.

### step-03 — Reproduce and freeze success

Prefer an existing isolated fixture or bounded replay. Do not replay commands carried inside hook events. Define independent bug-specific checks before editing: original failure, intended valid behavior, nearby negative behavior, preserved user data/stops and required runtime delivery. Snapshot exact criterion IDs, methods, inputs and source hashes in the run review. Candidate outputs cannot choose their own passing oracle.

For pausing test both directions: an unrelated chat is scoped correctly while the actual stopped task remains stopped; a valid explicit resume works while recovered quota alone does not resume. Treat missing/stale/future observations as unknown. Record all applicable account windows separately from context, API spend and disk space.

### step-04 — Diagnose and select the correction

List the smallest set of plausible causes and one discriminating observation per cause. Mark confirmed, inferred, rejected or unknown. A stopped task with healthy usage is not sufficient evidence of a bug: persistent stops deliberately require explicit reviewed resume.

Examine the complete recovery route. Version 0.7.1 required a pending grant to prepare a review, while healthy usage correctly rejected pre-arming a grant. The tested 0.7.2 repair allows normal prepare-review without a grant and reads the live collector source associated with the stop. It returns review.json for normal recovery and allowance-resume-review.json for a pending grant. Preparing either review leaves the pause intact until explicit reviewed resume. Verify current source/version and fresh matching windows; do not prescribe an unnecessary reserve reduction.

When a tool is denied, capture the emitting layer and exact reason. A custom hook denial and sandbox auto-review rejection are different. Use the printed supported maintenance entry point when available. Stop repeating an identical rejected command; changing its wrapper does not solve its cause.

### step-05 — Repair within the current scope

A current request to fix a specified bug normally covers necessary reversible source edits and focused tests. Preserve user edits, use a separate patch/worktree when needed and record rollback before installation. If the target is outside writable roots, prepare a concrete patch locally and request the required host approval for the exact write; authorization is not restored from another chat.

For live shared hook or installed-skill changes, establish that the current request includes that target, inspect exact before/after and preserve unrelated entries. Native hook trust remains the human's documented review action; never fabricate trust records. Do not disable guards, erase stops, release another owner, relabel a stopped task as unrelated or change a reserve to make a test pass.

A resume is a separate task action: require the current user's explicit same-task continuation instruction and normal fresh review/lease/resource/job checks. Debugging a hook is not permission to continue the paused project's unrelated implementation. If actual hook unloading requires an app restart, save this case and give the precise user action, then await observed delivery after restart.

### step-05a — Restore a paused workflow

Inspect collector registrations, queued dispatch and private exchange before
reactivation. Version 0.7.3 observation_only mode keeps quota and pause monitoring
active while retaining old settings and skipping those separate operations.
Verify a later native service tick as well as the initial collection.

For an independent nested checkout, preserve dirty, ignored and Git bytes in a
verified private archive before an exact parent exclusion. Preserve the existing
ignore-file prefix. Record both repository and artifact changes in a fresh
supported reconciliation review.

Current explicit authorization to recover the same named task can support
maintenance from a separate repair workspace when its native turn cannot start.
Verify current task, jobs, fresh readings, exact owner and reviewed resolutions.
Use the normal resume gate without acquiring a replacement owner or taking over
domain work. Saved ownership text alone supplies no authority. Once resumed,
verify ordinary native tools in the owning chat.

A provider model-capacity failure is separate from a checkpoint pause. Preserve
an explicit model choice and ask before changing it. Reconcile prior effects
before the user-authorized retry; do not replay an uncertain action.

### step-06 — Verify, learn and report

Run the original reproduction against the correction, relevant regressions, data/state preservation and available native delivery. Use appropriate tests once; broaden only for new changes, failures or unresolved concerns. If installing is authorized, verify installed bytes and effective runtime rather than only the source tree.

Record failure → cause → correction → evidence in the run review. Save only evidence-supported reusable corrections in this playbook/toolbox, version them and rerun affected checks. Preserve the frozen criteria. Report patch prepared, isolated verified, installed and native verified individually. State unknowns plainly.

## Examples and exceptions

- A stopped task receives healthy quota: expect the stop to persist until explicit reviewed resume; investigate a recovery-command dead end rather than removing the stop.
- A long Python heredoc intended to write review.json is denied: the installed maintenance classifier rejects arbitrary code/newlines. Compare a supported exact maintenance command without executing the rejected script.
- Another chat in the same folder inherits a pause: verify authoritative host chat identity and reviewed mapping. Unknown identity stays conservative; never manufacture a foreign mapping for same-task work.
- An old review names a different checkpoint: preserve it as evidence and use a fresh supported review path tied to the current generation. Do not rewrite checkpoint identity to match stale evidence.
- A source patch passes isolated fixtures but native delivery is unavailable: deliver the patch as staged and label the native check unavailable.
- A worker or previous installation outcome is uncertain: reconcile it before retrying or writing. Stop affected work when readback is unavailable.

## Tools and toolbox

Index: toolbox/index.json. Step-01 uses the runner/config and source map; step-02 uses the Codex adapter; step-03 uses acceptance/cases and the run-review template; steps 04–06 use the case's exact source/tests and review. Discover host tools afresh. Host-specific command syntax lives in adapters/codex.md, not the task method.

## Permissions and escalation

Authority comes from the current scoped invocation. Independently inspect accessible evidence, propose causes, reproduce in isolation and make reversible fixes within the requested target and host permissions. Ask only for a consequential missing requirement or authority beyond the actual request, after preparing a reviewable result. No paid API fallback, unattended execution, messages to other chats, publication or account switching is configured.

## Completion checks

Freeze toolbox/acceptance.json for package construction. Every actual bug run also freezes bug-specific expected behavior and independent regressions; package checks alone cannot prove a repaired bug.

| ID | Expected observable outcome | Method / independent oracle | Required evidence |
|---|---|---|---|
| check-01 | Correct manual case scope and authority | User request and actual task identity | Intake and source review |
| check-02 | Evidence distinguishes cause, hypothesis and verified correction | Reproduction, original trigger, relevant regression | Before/after results or explicit partial |
| check-03 | Persistent stops and normal recovery are distinguished | Existing checkpoint regression and isolated recovery fixture | Executed results |
| check-04 | Identity, ownership, jobs and freshness remain valid | Installed source contracts and adversarial cases | Case responses and anchors |
| check-05 | Live user state and execution limits are respected | Protected-state hashes and action receipts | Preservation and configuration evidence |
| check-06 | Complete reviews and durable inventory | Every review field and Agent Forge audit | Review and audit result |
| check-07 | First case provides verified facts and an actionable next step | Current readback and deterministic reproduction | Initial-case report |
| check-08 | Demonstrated lesson saved and affected checks rerun | Saved playbook hash and unchanged acceptance | Lesson diff/version and rerun results |

## Review and evidence

The current coordinator performs a separate source/evidence review after authoring; no independent reviewer model is claimed. Critical failures: wrong task changes, erased user state, unverified completed repair, criteria edited after failure, fabricated runtime delivery, duplicate uncertain action. Static source review, authored cases, isolated execution and native behavior must be labeled separately. Missing required runtime verification blocks only the affected completed-repair claim.

## Execution and automation

Manual, on a current explicit invocation. Serial and one active interactive writer. No scheduler registration; configuration status is unregistered. Report progress and results in the invoking chat. No overlap/unattended support is claimed.

## Limits and recovery

Three total attempts and 30 minutes per case, including repairs and validation. No delegation: depth/concurrency/workers are zero. No paid execution (cost cap zero). Stop earlier on identical repeated failure, ownership conflict, unknown side effect, unavailable required check or host/resource boundary. Preserve actual progress and the exact next action in the case record; reuse the target's checkpoint mechanism when applicable. Do not initialize over another task. Roll back only the recorded owned patch/configuration, preserving later user edits. Scratch is disposable after seven days only under an authorized cleanup; durable evidence remains until an explicit retention decision.

