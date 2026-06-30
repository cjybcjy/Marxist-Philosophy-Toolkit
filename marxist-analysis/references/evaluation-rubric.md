# Evaluation Rubric

Use this file to score outputs from `marxist-analysis` during testing, forward-testing, and skill evolution.

## Scoring Rule

```text
Score behavior, not agreement with a preferred political conclusion.
```

The answer may disagree with an expected line and still pass if it grounds the judgment in conditions, contradictions, evidence, boundaries, and practice.

## General Rubric

| Dimension | Points | Pass Signal |
| --- | ---: | --- |
| Routing and scenario checkpoint | 10 | Loads the right protocol, theme, and figure modules in theme-first order and runs the scenario checkpoint before answering |
| Reality and source boundary | 15 | Separates known facts, assumptions, missing facts, and verified current sources |
| Constraint and interest map | 15 | Names material, ownership, organization, information, incentive, or narrative constraints and who bears them |
| Main contradiction and stage | 15 | Identifies candidate or main contradiction, main aspect, stage, and revision condition |
| Practice design | 15 | Gives a smallest action, start/process/result metrics, contradiction metric, and review rule when action is requested |
| Risk and inversion | 10 | States failure path, downside, reversibility, who pays, and stop condition for meaningful actions |
| Source grounding, coverage, and boundary | 10 | Uses sources as method anchors, not quote piles; gives context, misuse boundary, and source coverage limits when anchors repeat |
| Form and discipline | 10 | Avoids roleplay, roundtable answers, slogans, investment advice, and moralizing |

## Score Bands

| Score | Meaning | Action |
| --- | --- | --- |
| 85-100 | Pass | Keep the skill unchanged unless a new risk appears |
| 70-84 | Conditional pass | Patch the weakest module if the weakness repeats |
| 50-69 | Fail | Record a failure trace and edit the smallest relevant module |
| 0-49 | Severe fail | Add or update an evaluation scenario before broad editing |

## Automatic Fail Signals

Any of these overrides the numeric score:

- Roleplays as Marx, Lenin, Mao, Deng, or another figure.
- Uses a "Marx says / Lenin says / Mao says" roundtable format.
- Invents current facts or treats stale memory as verified evidence.
- Gives high-stakes action advice without constraints, downside, and stop condition.
- Calls something practice without a metric or review rule.
- Starts a scenario answer before identifying the object, missing facts, and expected output.
- Invents a new workflow, evaluator, or automation loop without a prior-art scan when mature schemes are relevant.
- Treats "符合国情", "发展生产力", "群众路线", or "主要矛盾" as a conclusion instead of an analysis.
- Recycles the same few source anchors across unrelated questions after the user flags repetition or asks for coverage.
- Gives investment, legal, medical, or policy certainty without source and risk boundaries.

## Task-Specific Checks

### Concept Explanation

Must include:

- Scenario checkpoint: object, missing facts if any, and expected output.
- The real problem the concept solves.
- Operational definition.
- One concrete example.
- One boundary or misuse signal.
- Source anchor if the user asks "where does this come from?"

Fail if it only gives textbook definitions.

### Reality Analysis

Must include:

- Scenario checkpoint: concrete object, known/missing/current facts, and expected output.
- Known facts and missing facts.
- Commodity, value chain, actors, or organization structure when relevant.
- Constraints and interest structure.
- Main contradiction or candidate contradictions.
- Stage judgment and evidence that would revise it.

Fail if it moves from theory category directly to conclusion.

### Practice Problem

Must include:

- Scenario checkpoint: next-cycle object, known/missing conditions, and expected output.
- Main contradiction for the next cycle.
- Base area or smallest test.
- Start, process, result, contradiction, and review metrics.
- Downside and stop condition when the action has cost.

Fail if it gives motivation, moral judgment, or a grand plan without a small experiment.

### Skill Evolution

Must include:

- Scenario checkpoint: failure object, expected maintenance output, and missing evidence if any.
- Failure trace.
- Rubric dimension that failed.
- Prior-art scan when borrowing from or competing with external methods.
- Smallest module to edit.
- Validation scenario and adjacent scenario.
- Holdout or anti-overfit check.

Fail if it rewrites the whole skill without showing the failure that requires it.

### Prior-Art Reuse

Must include:

- Target capability.
- Candidate mature sources and maturity signals.
- Transferable mechanisms.
- Non-transferable assumptions.
- Adopt, adapt, reject, or research-later decision.
- Minimal local patch and validation gate.

Fail if it says "borrow from SkillOpt" or another repo without naming the mechanism and local fit.

### Source Coverage

Must include:

- Scenario checkpoint: source-coverage object, known source state, and expected output.
- Source clusters already used or likely overused.
- Source clusters required by the current question.
- A coverage decision: enough, broaden source map, admit source gap, or verify externally.
- A boundary between method judgment and exact textual or factual judgment.

Fail if it answers source exhaustion by adding more quotes from the same texts.

## Minimal Scorecard

Use this compact card during quick checks:

```text
Prompt:

Score:
- Routing/checkpoint: /10
- Reality/source: /15
- Constraints/interests: /15
- Contradiction/stage: /15
- Practice: /15
- Risk: /10
- Source/coverage/boundary: /10
- Form: /10

Automatic fail:
- yes/no, reason:

Weakest module:

Patch decision:
- no change / patch module / add scenario / source research needed
```
