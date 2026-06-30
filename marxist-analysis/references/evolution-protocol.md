# Evolution Protocol

Use this file when improving, debugging, evaluating, or extending this skill. The goal is to make `marxist-analysis` evolve through evidence, not through bigger slogans or broader summaries.

## Core Rule

```text
Do not optimize the sample answer. Optimize the skill behavior that produced it.
```

A skill edit is valid only when it is tied to a failure trace, a rubric gap, or a new recurring use case.

## SkillOpt-Lite Loop

| Phase | Action | Output |
| --- | --- | --- |
| RED | Run a realistic prompt and record the failure | Failure trace, missing behavior, affected module |
| Diagnose | Score the output with `evaluation-rubric.md` and check `coverage-matrix.md` | Weak dimensions, automatic-fail signals, covered or uncovered area |
| Prior-art scan | Check mature skills, frameworks, repos, or docs before inventing a new mechanism | Reuse ledger, transferable mechanism, non-transferable assumption, local adaptation decision |
| Edit | Patch the smallest relevant reference file | One bounded module change, not a global rewrite |
| Validate | Re-run the scenario and at least one nearby scenario | Pass/fail result and remaining risk |
| Holdout | Check a scenario not used to design the patch | Guard against overfitting |
| Consolidate | Update routing only if the failure is recurrent | SKILL.md or dispatcher changes only when necessary |

## What Counts As A Failure Trace

Record enough evidence that another maintainer can reproduce the issue:

```text
Prompt:
- [raw user prompt]

Observed failure:
- [what the answer did wrong]

Expected skill behavior:
- [what the skill should have forced]

Likely missing module:
- [file path]

Acceptance check:
- [what must be true after the edit]
```

Do not store long logs inside the skill. Keep only reusable rules, scenarios, and rubrics in `references/`.

## Self-Evolution Answer Pattern

Use this shape when the user asks how to improve, debug, evolve, score, or iterate this skill. The answer should teach the next maintenance move, not rewrite the whole skill.

```text
RED failure trace:
- Prompt:
- Observed failure:
- Expected behavior:
- Why this is a skill failure, not just a weak sample answer:

Rubric diagnosis:
- Failed dimensions:
- Automatic fail signals:
- Score band:

Coverage check:
- Covered / partially covered / uncovered:
- Existing scenario:
- Known gap:

Prior-art scan:
- Candidate mature sources:
- Transferable mechanisms:
- Non-transferable assumptions:
- Adopt / adapt / reject:

Smallest patch:
- Patch first:
- Do not patch:
- Why this module:

Scenario plan:
- Train scenario:
- Validation scenario:
- Adjacent scenario:
- Holdout scenario:

Acceptance gate:
- Must improve:
- Must not regress:
- Stop / no-patch condition:
```

If there is no reproducible failure, say `no patch yet`; add a scenario or ask for the failing output instead of editing.

Keep the answer operational. Do not answer with a broad improvement essay or a generic "add more examples" recommendation.

## Edit Budget

Prefer the smallest edit that changes future behavior:

| Failure Type | Patch First | Avoid |
| --- | --- | --- |
| Wrong route or missing module | `SKILL.md` or `dispatcher.md` | Adding theory content everywhere |
| Answer starts before object, facts, or expected output are clear | `scenario-checkpoints.md`, `fallbacks.md` | Writing a fuller final answer |
| Reinventing an existing workflow or evaluator | `prior-art-scan.md`, `evolution-protocol.md` | Building a custom optimizer before checking mature schemes |
| Slogan or quote pile | `fallbacks.md`, relevant theme | More quotes |
| No concrete action | `practice-cards.md` | A larger plan with no test |
| No metrics | `practice-metrics.md` | Calling an intention a practice test |
| Risky advice | `risk-and-inversion.md` | Encouraging courage or rejection before constraints |
| Current facts hallucinated | `source-policy.md`, scenario criteria | Treating memory as evidence |
| Repeated source anchors | `source-coverage.md`, `source-map.md`, `fallbacks.md` | Stuffing full corpora or more quotes into the skill body |
| Concept used as label | `concept-debugging.md` | Longer textbook definitions |
| Historical tension flattened | `arbitration.md` | "All are correct" synthesis |
| Weak evaluation | `evaluation-rubric.md` or `evaluation-scenarios.md` | Changing expected answers instead of behavior |
| Coverage unclear | `coverage-matrix.md` | Treating one scenario as proof of full coverage |

Only edit figure modules when the failure is about a figure's source, historical task, or calibration boundary. Do not use figure modules to fix theme-level reasoning.

## Validation Gate

Before accepting a skill edit:

1. Run the basic skill validator.
2. Check that every reference named in `SKILL.md` exists.
3. Score at least one affected scenario with `evaluation-rubric.md`.
4. Check `coverage-matrix.md` to choose one adjacent scenario and one holdout scenario.
5. If the patch creates a new workflow, evaluator, automation loop, or borrows from external work, load `prior-art-scan.md` and record the adopt/adapt/reject decision.
6. Run one adjacent scenario that should not have changed.
7. Check automatic-fail signals:
   - roleplay or roundtable voice
   - invented current facts
   - high-stakes advice without downside and stop condition
   - practice plan without metrics
   - contradiction label without stage or revision condition
   - new workflow invented without checking mature prior art

Accept the edit only if it improves the affected scenario without weakening the adjacent one.

## Train, Validation, Holdout

Use the scenario groups in `evaluation-scenarios.md` to prevent overfitting:

| Group | Use | Rule |
| --- | --- | --- |
| Train | Diagnose and design a patch | Pass criteria may be inspected |
| Validation | Check the patch | Do not change criteria during the same iteration |
| Holdout | Sanity check generalization | Do not tune directly to the failure |

When adding a new scenario, place it first as validation or holdout if it came from a surprising real failure.

Default selection:

```text
Affected train scenario:
- [the scenario that exposed the failure]

Validation scenario:
- [nearby but different domain, chosen before editing]

Holdout scenario:
- [reserved scenario not inspected while designing the patch]
```

If the failure starts from a validation or holdout scenario, do not immediately tune to it. First write a failure trace, then add or promote another scenario so one scenario remains reserved as holdout.

## Coverage Review

Before adding a new module or scenario:

1. Read `coverage-matrix.md`.
2. Decide whether the failure is covered, partially covered, or uncovered.
3. If covered, patch the smallest module named in the matrix.
4. If partially covered, add one scenario only when the existing scenario cannot catch the failure.
5. If uncovered, add a scenario before adding broad theory content.

Do not use the matrix as proof that the skill is complete. It is a map of current pressure tests and known gaps.

## When To Stop

Stop editing when:

- The failure has a bounded repair and validation passes.
- The next improvement would require new source research, not skill structure.
- The patch would duplicate information already present in another module.
- The answer quality problem comes from missing user facts rather than missing skill guidance.

If the skill still fails after two bounded edits, add a scenario that captures the failure before expanding the instruction set.
