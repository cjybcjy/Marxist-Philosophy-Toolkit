# Prior-Art Scan

Use this file before inventing a new workflow, evaluation method, automation loop, or major module for this skill. The goal is to reuse mature patterns when they fit and avoid building a private theory of skill evolution from scratch.

## Core Rule

```text
Search before designing.
Adapt mechanisms, not branding.
Do not copy a tool if its assumptions do not match this skill.
```

Prior art is useful only when it changes a concrete maintenance decision: what to borrow, what to reject, what to validate, and what not to build.

## When To Load

Load this with `evolution-protocol.md` when:

- The user mentions SkillOpt, Darwin-style skill evolution, Nuwa-generated skills, X Mentor, or another implemented skill.
- A proposed patch would create a new workflow, evaluator, scenario system, scoring method, or automation loop.
- The maintainer is tempted to add a custom mechanism without checking existing repos, papers, docs, or mature skills.
- A failure looks common enough that another skill or framework may already have solved it.

Use `source-policy.md` when external repos, papers, docs, or current tool behavior are cited. Verify current external sources when tools are available.

## Prior-Art Ledger

Before editing, fill this compact ledger:

```text
Target capability:
- [what behavior we need]

Candidate mature sources:
- [repo / paper / skill / docs]

Maturity signals:
- [tests, docs, examples, adoption, active maintenance, clear evaluation loop]

Transferable mechanisms:
- [specific rules or workflow pieces worth borrowing]

Non-transferable assumptions:
- [what does not fit marxist-analysis]

Adoption decision:
- adopt / adapt / reject / research later

Minimal patch:
- [smallest local module change]

Validation:
- [affected scenario, adjacent scenario, holdout]
```

Do not store long research notes in this skill. Keep only reusable rules and links to source clusters.

## Reuse Decision Table

| External Pattern | Borrow | Do Not Borrow |
| --- | --- | --- |
| SkillOpt-style optimization | Test set, evaluator, bounded edit, validation gate, holdout, early stopping | Blind metric chasing or optimizing one sample answer |
| Darwin-style automatic skill evolution | Reproducible failure trace, one-dimension patch, keep/revert decision, evolution log | Fully autonomous edits without source, rubric, or human-readable rationale |
| Nuwa-style skill generation | Persona/theme distinction, extraction framework, source boundaries | Merging voices into one persona or copying style DNA into method skills |
| Mature theme skills | Scenario routing, operation layer vs research layer, STOP/checkpoint gates | Treating another domain's checklist as universal content |
| Existing local modules | Extend the smallest matching module | Creating a parallel module for the same failure mode |

## Maturity Signals

Prefer prior art with at least two of these:

- Clear problem statement and usage examples.
- Evaluation prompts, tests, or scoring rubric.
- Separation between training/design cases and validation or holdout cases.
- Documented failure modes and rejected approaches.
- Evidence that the workflow has been run on real outputs, not only described.
- Boundaries that say when not to use the method.

If maturity is weak, use it as inspiration only and validate locally before adding it to the skill.

## Integration Rules

- Add a new module only when no existing module owns the failure.
- Patch `evolution-protocol.md` when the improvement changes the maintenance loop.
- Patch `evaluation-rubric.md` or `evaluation-scenarios.md` when the improvement changes how success is judged.
- Patch `coverage-matrix.md` when the improvement creates a new first-class failure mode.
- Do not add external-tool requirements unless the skill can still degrade gracefully without them.

## Output Pattern

When the user asks how to borrow an external method, use:

```text
先查成熟方案：
- 目标能力：
- 已查方案：
- 可借鉴机制：
- 不适配部分：

本地适配：
- 最小补丁：
- 不做什么：
- 验证场景：
- 保留/回滚条件：
```

## Anti-Patterns

- Saying "参考 SkillOpt" without naming which mechanism is being reused.
- Reimplementing an optimizer before defining evaluation prompts and acceptance gates.
- Copying a persona-skill pattern into a theme-skill workflow.
- Adding a new module because an external repo has one, rather than because a local failure requires it.
- Treating GitHub popularity or a polished README as proof of fit.
