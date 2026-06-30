# Scenario Checkpoints

Use this file after the question is roughly classified and before writing the answer. It prevents the skill from starting with theory when the scenario still lacks the minimum conditions for analysis.

## Core Rule

```text
Run the scenario gate before the analysis.
If a gate fails, ask one minimum question, state the gap, or switch to a conditional answer.
```

The checkpoints are not an output template. They are a pre-answer gate.

## Shared Gate

Every scenario starts with three checks:

```text
Object:
- What concrete object, relation, decision, or concept is being analyzed?

Facts:
- What is known, missing, current-fact sensitive, or assumed?

Expected output:
- Does the user need explanation, diagnosis, decision support, source grounding, or a practice test?
```

If the object is unclear, do not choose a route yet. Ask one clarifying question or use `fallbacks.md`.

## Scenario Gates

| Scenario | Three Questions Before Answering | If Missing |
| --- | --- | --- |
| Industry or company analysis | What is the commodity or service? Where is the value chain and bottleneck? Who captures surplus and who bears risk? | Load `protocols/industry-analysis.md`, `constraint-map.md`, and `source-policy.md`; mark missing market facts |
| Policy or social issue | What policy, institution, or relation is being judged? Who gains, pays, administers, or resists? Are current laws, data, or implementation facts verified? | Treat as conditional analysis; verify current facts before strong claims |
| Personal practice | What is the next-cycle candidate contradiction? What is the smallest base area today? What start, process, result, and review metrics will test it? | Load `practice-cards.md`, `practice-metrics.md`, and `risk-and-inversion.md` |
| Organization strategy | Is the conflict about line, resources, authority, legitimacy, capacity, or external pressure? Who bears consequences? What one-week experiment can reveal the main contradiction? | Load `protocols/organization-strategy.md`; avoid personality framing |
| Concept explanation | What real problem does the concept solve? What is the operational definition? What example and misuse boundary will prove understanding? | Load `concept-debugging.md` and `source-map.md` |
| Source challenge | Which method needs grounding? What source cluster and historical task apply? What is direct source and what is current application? | Load `source-policy.md`, `source-map.md`, and `source-coverage.md` when anchors repeat |
| Source acquisition or edition integrity | What book/text is needed? Which edition/source tier is available? What metadata and anchor passages can verify or reject it? | Load `source-acquisition-integrity.md`; treat online search results as bibliographic hints only |
| Framework or method-template design | Is the user asking for taxonomy, source authority, repeatable procedure, or modern application? Which layer is framework-synthesis, primary text, template, current fact, or inference? | Load `theory-framework.md`, `method-templates.md`, and `source-policy.md`; do not answer with textbook definitions alone |
| Sinicization or route conflict | Which routes or stages are in tension? What conditions make each route valid? What would turn local adaptation into an excuse? | Load `arbitration.md` and preserve tension |
| Skill evolution | What is the RED failure trace? Which rubric dimension failed? What smallest module, validation scenario, adjacent scenario, and holdout will test the patch? | Load `evolution-protocol.md`, `evaluation-rubric.md`, and `coverage-matrix.md` |

## Gate Decision

After the scenario gate, choose one:

| Decision | Use When | Answer Behavior |
| --- | --- | --- |
| Answer now | The gate has enough facts and route clarity | Give the analysis in the normal output shape |
| Ask one question | One missing fact controls the route | Ask the minimum clarifying question before analysis |
| Conditional answer | Facts are incomplete but useful branches are clear | State assumptions, candidates, and what evidence would revise them |
| Practice-first | The user wants action and theory would stall | Give a small experiment with metrics and review rule |
| Source-boundary answer | The user asks for evidence or sources are thin | Separate method judgment from exact textual or current-fact judgment |

## Anti-Patterns

- Starting with "according to Marxism" before naming the concrete object.
- Declaring the main contradiction before checking facts and stage.
- Giving a practice plan without metrics.
- Treating a concept explanation as a textbook definition instead of an operational tool.
- Answering a source challenge with more quotations but no boundary.
- Offering route advice before downside, reversibility, and who bears consequences are named.
