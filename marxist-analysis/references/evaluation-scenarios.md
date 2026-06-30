# Evaluation Scenarios

Use these scenarios to pressure-test `marxist-analysis` after edits. They are not examples to copy verbatim into normal answers; they are pass/fail cards for checking whether the skill routes, reasons, and outputs correctly.

## How To Test

For each scenario:

1. Start with only `SKILL.md`.
2. Load references only as the workflow requires.
3. Produce a concise answer.
4. Score the answer with `evaluation-rubric.md`.
5. Check scenario pass/fail criteria and automatic-fail signals.
6. Use `coverage-matrix.md` to identify whether the failure mode is covered, partially covered, or uncovered.
7. If the answer fails, use `evolution-protocol.md` to update the smallest relevant reference file, not the expected answer.

Do not leak these pass criteria into a testing subagent. Give the subagent only the skill path and the user prompt.

## Scenario Sets

Use these groups to avoid optimizing the skill only against familiar prompts.

| Group | Scenarios | Use | Rule |
| --- | --- | --- | --- |
| Train | 1. Industry Analysis; 2. Personal Practice; 4. Organization Strategy; 6. Fallback And Practice Cards | Diagnose common failures and design bounded patches | Pass criteria may be inspected while designing the edit |
| Validation | 3. Sinicization Conflict; 7. Constraint And Risk Gate; 8. Concept Debugging; 10. Source Coverage And Argument Reuse; 11. Scenario Checkpoint Gate; 12. Prior-Art Reuse Gate | Check whether a patch generalizes across tension, risk, concept, source-coverage, scenario-gate, and prior-art reuse tasks | Do not change validation criteria in the same iteration |
| Holdout | 5. Source Challenge; 9. Skill Evolution | Catch overfitting to user-facing analysis and self-edit workflows | Do not tune directly against these scenarios during the same iteration |

Default iteration pattern:

```text
1 train scenario -> 1 validation scenario -> 1 holdout scenario
```

If a real user failure matches a holdout scenario, promote that scenario to validation for that iteration and add a new holdout before tuning directly to it.

Use `coverage-matrix.md` before adding scenarios. The matrix records which problem areas and failure modes are already pressured and which gaps are intentionally open.

## Scenario Index

| Scenario | Set | What it catches |
| --- | --- | --- |
| 1. Industry Analysis | Train | Tech-progress slogans, missing value-chain analysis, unsupported current facts |
| 2. Personal Practice | Train | Motivational filler, no small experiment, Mao roleplay leakage |
| 3. Sinicization Conflict | Validation | False all-valid/all-betrayal answers, missing arbitration |
| 4. Organization Strategy | Train | Personality framing, vague discipline advice, no organization experiment |
| 5. Source Challenge | Holdout | Quote piles, missing source boundary, confusing source with inference |
| 6. Fallback And Practice Cards | Train | Forced certainty, abstract advice, missing recovery route |
| 7. Constraint And Risk Gate | Validation | Advice before constraints, action without downside or stop condition |
| 8. Concept Debugging | Validation | Jargon as understanding, no example, no boundary |
| 9. Skill Evolution | Holdout | Whole-skill rewrites, taste-based scoring, no failure trace |
| 10. Source Coverage And Argument Reuse | Validation | Repeated source anchors, hidden corpus gaps, citation padding |
| 11. Scenario Checkpoint Gate | Validation | Answering before object, facts, and expected output are clear |
| 12. Prior-Art Reuse Gate | Validation | Reinventing workflow or optimizer without checking mature schemes |

## Scenario 1: Industry Analysis

**User prompt**

```text
用马哲分析一下 AI 编程工具这个行业：它到底提高了生产力，还是只是换一种方式加强剥削？
```

**Required route**

- `references/dispatcher.md`
- `references/scenario-checkpoints.md`
- `references/source-policy.md`
- `references/constraint-map.md`
- `references/risk-and-inversion.md`
- `references/practice-metrics.md`
- `references/protocols/industry-analysis.md`
- `references/themes/political-economy.md`
- `references/themes/historical-materialism.md`
- `references/figures/marx-engels.md`
- Optional: `references/figures/deng.md`

**Must include**

- State missing current facts if not verified: pricing, user adoption, labor effects, ownership, data/IP, platform power.
- If current studies or market claims are cited, mark whether they were verified in the current session and name the source/date when available.
- Define the commodity/service and value chain.
- Separate productivity increase from surplus capture.
- Name at least one main contradiction.
- Give evidence to seek next, not a confident market thesis without facts.

**Fail if**

- Says "technology is progressive" or "capital always exploits" without mapping the value chain.
- Gives investment advice.
- Ignores hidden labor, data, ownership, or platform dependency.
- Uses Marx as a quote source instead of political-economy method.

## Scenario 2: Personal Practice

**User prompt**

```text
我想做一个马哲学习项目，但总是拖延。别给我鸡汤，用实践论和矛盾论帮我拆一个今天能开始的小实验。
```

**Required route**

- `references/dispatcher.md`
- `references/scenario-checkpoints.md`
- `references/protocols/personal-practice.md`
- `references/practice-cards.md`
- `references/practice-metrics.md`
- `references/themes/dialectics-contradiction.md`
- `references/figures/mao.md`

**Must include**

- Name the main contradiction for the next 7 to 14 days.
- Separate direct experience from imagined judgment or hearsay.
- Define a small base area: time, place/tool, minimum artifact.
- Give a test for today and a review rule.
- Avoid moralizing avoidance.

**Fail if**

- Gives motivational slogans.
- Gives a large study plan before a small experiment.
- Says "just persist" without a feedback loop.
- Roleplays as Mao or calls the user "comrade."

## Scenario 3: Sinicization Conflict

**User prompt**

```text
中国化为什么不是背离马克思？是不是只要说符合中国国情就都能算马克思主义？
```

**Required route**

- `references/dispatcher.md`
- `references/scenario-checkpoints.md`
- `references/arbitration.md`
- `references/themes/sinicization.md`
- `references/themes/historical-materialism.md`
- `references/source-map.md`
- `references/figures/mao.md`
- `references/figures/deng.md`
- `references/figures/marx-engels.md`

**Must include**

- Distinguish continuity of method from identity of wording.
- State the continuity test: material conditions, class/production relations, contradiction, practice evidence, stage judgment.
- Explain when "local conditions" is valid and when it becomes an excuse.
- Preserve tension between universal theory and local route.

**Fail if**

- Says "because leaders said so."
- Says all adaptation is betrayal.
- Says all adaptation is valid.
- Avoids the boundary question.

## Scenario 4: Organization Strategy

**User prompt**

```text
一个小团队内部路线不统一：有人想先做产品，有人想先做内容，有人想拉投资。用马哲分析主要矛盾，并给一个一周内能验证的组织实验。
```

**Required route**

- `references/dispatcher.md`
- `references/scenario-checkpoints.md`
- `references/protocols/organization-strategy.md`
- `references/practice-cards.md`
- `references/practice-metrics.md`
- `references/themes/class-state-party.md`
- `references/themes/dialectics-contradiction.md`
- `references/figures/mao.md`
- Optional: `references/figures/lenin.md`

**Must include**

- Identify whether the conflict is line, resource, authority, legitimacy, capacity, or external pressure.
- Map actors by role and consequence, not personality.
- Distinguish surface disagreement from main organizational contradiction.
- Give a one-week experiment with observation and review.

**Fail if**

- Says "more discipline" without legitimacy/capacity analysis.
- Says "vote on it" without identifying the contradiction.
- Turns it into a personality conflict.
- Gives no experiment.

## Scenario 5: Source Challenge

**User prompt**

```text
你说要先找主要矛盾，这个依据是什么？不要只给口号，告诉我方法来自哪里、今天怎么用、边界是什么。
```

**Required route**

- `references/source-policy.md`
- `references/scenario-checkpoints.md`
- `references/source-map.md`
- `references/concept-debugging.md`
- `references/themes/dialectics-contradiction.md`
- `references/figures/mao.md`

**Must include**

- Method name.
- Source anchors, especially contradiction writings.
- Historical task of the source.
- Today-use action: identify decisive relation in concrete stage.
- Boundary: not every visible problem is the main contradiction.

**Fail if**

- Gives only quotes.
- Gives no boundary.
- Treats source text as automatic proof.
- Does not distinguish source from current application.

## Scenario 6: Fallback And Practice Cards

**User prompt**

```text
我给的信息很少：我想换方向，但不知道是继续工作、做内容，还是做一个 AI 项目。你别硬判断，先用马哲帮我搭一个能验证主要矛盾的小框架。
```

**Required route**

- `references/dispatcher.md`
- `references/scenario-checkpoints.md`
- `references/fallbacks.md`
- `references/practice-cards.md`
- `references/practice-metrics.md`
- `references/constraint-map.md`
- `references/protocols/personal-practice.md`
- `references/themes/dialectics-contradiction.md`

**Must include**

- State that current facts are insufficient for a final judgment.
- List 2 to 3 candidate contradictions instead of forcing one.
- Use one practice card or a compact equivalent.
- Define a 7 to 14 day evidence-gathering action.
- State what result would revise the contradiction judgment.

**Fail if**

- Decides the route confidently without facts.
- Gives generic career advice.
- Gives only theory categories with no experiment.
- Ignores the user's "别硬判断" constraint.

## Scenario 7: Constraint And Risk Gate

**User prompt**

```text
我想辞职全职做一个 AI 项目，手上现金够撑 8 个月。用马哲帮我判断是不是该 all-in，但别只讲理想，先帮我拆现实约束和失败路径。
```

**Required route**

- `references/dispatcher.md`
- `references/scenario-checkpoints.md`
- `references/constraint-map.md`
- `references/risk-and-inversion.md`
- `references/practice-cards.md`
- `references/practice-metrics.md`
- `references/protocols/personal-practice.md`
- `references/themes/historical-materialism.md`
- Optional: `references/themes/dialectics-contradiction.md`

**Must include**

- Map constraints: cash runway, skill/product capability, market/user evidence, family or social reproduction cost, organization/support system, information gaps.
- Do not treat the problem as courage versus fear.
- Identify at least one candidate main contradiction.
- Define downside, reversibility, who bears consequences, and stop condition.
- Prefer a barbell or staged experiment over all-in unless ruin risk is clearly bounded.

**Fail if**

- Encourages or rejects resignation without mapping constraints.
- Treats cash runway as the only constraint.
- Gives generic startup motivation.
- Gives a practice plan with no stop condition.

## Scenario 8: Concept Debugging

**User prompt**

```text
我总听到生产力和生产关系，但感觉只是背术语。你别讲教材定义，用一个现实例子说明它们怎么区分、怎么用、什么时候会被误用。
```

**Required route**

- `references/dispatcher.md`
- `references/scenario-checkpoints.md`
- `references/concept-debugging.md`
- `references/source-map.md`
- `references/themes/historical-materialism.md`
- Optional: `references/figures/marx-engels.md`

**Must include**

- State the real problem the concepts solve.
- Give operational definitions for productive forces and relations of production.
- Use one concrete example.
- Give one boundary or misuse signal.
- Return to how the user can use the distinction in analysis.

**Fail if**

- Only gives textbook definitions.
- Uses the terms to end the discussion.
- Gives no concrete example.
- Gives no boundary or misuse check.

## Scenario 9: Skill Evolution

**User prompt**

```text
这个 skill 回答行业问题时总是喊“资本逐利”和“技术进步”，但不拆价值链和利益结构。请按 SkillOpt-lite 的方式告诉我应该怎么迭代，不要直接重写整个 skill。
```

**Required route**

- `references/evolution-protocol.md`
- `references/scenario-checkpoints.md`
- `references/evaluation-rubric.md`
- `references/evaluation-scenarios.md`
- `references/fallbacks.md`
- `references/protocols/industry-analysis.md`
- Optional: `references/dispatcher.md`

**Must include**

- A RED failure trace shape.
- The rubric dimensions likely failing: constraint and interest map, reality/source boundary, main contradiction.
- The smallest likely module to patch first.
- A validation scenario and one adjacent scenario.
- A holdout or anti-overfit check.

**Fail if**

- Rewrites the whole skill immediately.
- Changes expected answers instead of skill behavior.
- Gives only a generic "add more examples" answer.
- Does not define how to know the iteration worked.

## Scenario 10: Source Coverage And Argument Reuse

**User prompt**

```text
我发现你讲毛选相关问题时总是用《矛盾论》《实践论》《论持久战》这几篇。继续分析群众路线、组织路线、改革发展时，怎么避免只复用这几篇？如果材料不够，要怎么说？
```

**Required route**

- `references/source-policy.md`
- `references/scenario-checkpoints.md`
- `references/source-map.md`
- `references/source-coverage.md`
- `references/fallbacks.md`
- Relevant figure or theme modules only after the coverage decision

**Must include**

- A source coverage judgment: what has likely been overused and what the current question actually needs.
- A decision to broaden source clusters, route back to themes, admit a source gap, or verify an external corpus.
- A boundary between method judgment and exact textual grounding.
- A warning that more quotations from the same text do not solve coverage.
- A concrete routing example for at least two problem types, such as mass line and reform-development.

**Fail if**

- Replies with more quotes from the same few texts.
- Says "add more examples" without a coverage decision.
- Treats citation count as source diversity.
- Pretends exact original-text coverage exists when the source corpus is unavailable.
- Expands a figure voice instead of routing through themes or source maps.

## Scenario 11: Scenario Checkpoint Gate

**User prompt**

```text
平台经济到底是不是剥削？你先别急着下结论，告诉我回答前要过哪几个检查点，然后给一个条件化的小框架。
```

**Required route**

- `references/dispatcher.md`
- `references/scenario-checkpoints.md`
- `references/fallbacks.md`
- `references/source-policy.md`
- `references/constraint-map.md`
- Optional: `references/protocols/industry-analysis.md`
- Optional: `references/themes/political-economy.md`

**Must include**

- Run the shared gate: object, facts, expected output.
- Choose the relevant scenario gate, such as industry/company analysis or policy/social issue.
- State at least one missing current fact before making a strong judgment.
- Give a conditional framework instead of a final verdict if facts are incomplete.
- Explain whether to answer now, ask one question, or give a conditional answer.

**Fail if**

- Immediately answers "yes" or "no" without the gate.
- Treats "平台经济" as a complete object without defining platform, service, labor relation, and value chain.
- Gives a slogan about capital or technology instead of checkpointed analysis.
- Ignores the user's request to explain the pre-answer checks.

## Scenario 12: Prior-Art Reuse Gate

**User prompt**

```text
我们想让这个 skill 像 darwin-skill 那样自动进化，也参考 SkillOpt。请你先别自己设计一套新机制，先说明要查哪些成熟方案、借哪些机制、哪些不能照搬，再给最小本地改法和验证门。
```

**Required route**

- `references/dispatcher.md`
- `references/source-policy.md`
- `references/prior-art-scan.md`
- `references/evolution-protocol.md`
- `references/evaluation-rubric.md`
- `references/coverage-matrix.md`
- Optional: `references/evaluation-scenarios.md`

**Must include**

- Target capability: automatic or semi-automatic skill evolution.
- Candidate mature sources, such as SkillOpt-style optimization, Darwin-style skill evolution, and relevant implemented theme/persona skills.
- Maturity signals and source-status boundary for external repos or docs.
- Transferable mechanisms: test set, evaluator, bounded edit, validation/holdout, keep/revert, early stopping, or evolution log.
- Non-transferable assumptions: blind metric chasing, full autonomy, persona-style voice transfer, or external tool dependency.
- Minimal local patch and validation gate.

**Fail if**

- Designs a new optimizer without checking existing schemes.
- Says only "borrow SkillOpt" without naming the mechanism.
- Copies an external repo's structure without checking fit.
- Ignores verification, validation, holdout, or revert conditions.
- Treats current GitHub repo behavior as known without verification when current sources are available.

## Global Pass Criteria

Across all scenarios, a passing answer must:

- Avoid figure roleplay.
- Load themes before figures.
- Run scenario checkpoints before answering scenario-heavy questions.
- Separate known facts from assumptions.
- Preserve tensions instead of smoothing them into slogans.
- End with a practice-testable step when the prompt asks for action.
- Define metrics when a practice test is proposed.
- Name missing facts when current reality matters.
- Expose source-coverage limits when the user flags repeated arguments or thin source material.
- Use fallback handling instead of forced certainty when facts are insufficient.
- Check decisive constraints and downside before recommending high-stakes action.
- Use failure traces, rubrics, bounded edits, and holdout checks when improving the skill itself.
- Check mature prior art before inventing a new workflow, evaluator, or automation loop.

## Global Failure Signals

- "Marx would say... Lenin would say... Mao would say..." roundtable format.
- "坚持马克思主义" as a conclusion without analysis.
- A quote pile with no method.
- A theory explanation that ignores the user's concrete conditions.
- A grand plan with no smallest next action.
- A skill edit proposal with no RED failure trace or validation gate.
- Repeated use of the same source anchors as universal proof after a source-coverage complaint.
- A new workflow or optimizer designed without a prior-art scan.
