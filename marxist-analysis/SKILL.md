---
name: marxist-analysis
description: Use when the user asks for Marxist or Marxism-based analysis of real problems, industries, companies, policy, organization, class, state, contradiction, development stage, reform, mass line, sinicization, or practice-tested action plans. Trigger on Chinese prompts such as 马哲, 马克思主义分析, 毛主席, 毛泽东, 毛选, 教员, 实事求是, 邓论, 辩证分析, 批判思维, 主要矛盾, and 实践检验. Do not use for generic political roleplay, slogan writing, or historical trivia unless the user asks to analyze the trivia through Marxist method.
---

# Marxist Analysis

## Overview

Use this skill as a Marxist analysis toolbox. It turns a user's real question into a structured analysis of conditions, contradictions, interests, development stage, and a practice-testable next step.

This is not a persona skill. Do not roleplay as Marx, Engels, Lenin, Mao, Deng, or any political figure. Use figure modules as source lenses and historical calibration, not as voices.

## Core Rule

Always preserve this distinction:

```text
Themes are the entry point.
Figures are source modules.
Arbitration resolves tensions.
Practice tests the conclusion.
```

Do not merge figure modules into one "Marxist personality." Do not stage a roundtable answer. The output should be one analytical frame, with sources used only where they clarify the method.

## Workflow

### Step 1: Classify the Question

Read `references/dispatcher.md` when the question involves any real-world problem, mixed theory-and-practice problem, or uncertain route selection.

Classify the request:

| Type | Signal | Action |
| --- | --- | --- |
| Concept | Asks what a theory means, uses jargon, or challenges a concept | Load `references/scenario-checkpoints.md`, `references/concept-debugging.md`, the relevant theme, and source-map entries when grounding is needed |
| Reality analysis | Mentions a company, industry, policy, organization, career, family, project, or social problem | Load `references/scenario-checkpoints.md`; gather facts first, load `references/constraint-map.md`, load `references/source-policy.md` when using current facts, then load themes |
| Practice problem | User wants to act, decide, learn, stop avoiding, or run an experiment | Load `references/scenario-checkpoints.md`, `references/protocols/personal-practice.md`, `references/practice-cards.md`, `references/practice-metrics.md`, `references/risk-and-inversion.md`, plus relevant themes |
| Conflict | Asks why one route differs from another, or whether a theory was betrayed | Load `references/scenario-checkpoints.md` and `references/arbitration.md` |
| Source check | Asks "where does this come from" or asks for original texts | Load `references/source-policy.md` and `references/source-map.md` |
| Source coverage | Says answers repeat the same texts, arguments, slogans, or examples; asks whether the skill has enough source material | Load `references/source-coverage.md`, `references/source-map.md`, and `references/source-policy.md` |
| Prior-art reuse | Asks to borrow from another skill, repo, framework, SkillOpt, Darwin, Nuwa, X Mentor, or says not to reinvent the wheel | Load `references/prior-art-scan.md`, `references/source-policy.md`, then `references/evolution-protocol.md` if editing this skill |
| Skill evolution | Asks to improve, test, score, evolve, debug, or extend this skill | Load `references/evolution-protocol.md`, `references/prior-art-scan.md` when new mechanisms or external methods are involved, `references/evaluation-rubric.md`, `references/coverage-matrix.md`, and affected scenarios |

If concrete facts would materially change the answer, ask for the minimum missing facts or search/verify when tools are available. Do not pretend to know current facts.

### Step 2: Load References Narrowly

Use progressive disclosure:

1. Start with one protocol or one theme.
2. Add `references/scenario-checkpoints.md` before answering real-world, practice, conflict, concept, or source-coverage scenarios that need a pre-answer gate.
3. Add figure modules only when they clarify the method or historical condition.
4. Add `references/arbitration.md` only when sources or routes conflict.
5. Add `references/source-map.md` when the user wants original-text grounding.
6. Add `references/source-coverage.md` when the answer may be reusing the same source anchors, the user flags repeated arguments, or a figure module is stretched beyond its corpus.
7. Add `references/prior-art-scan.md` before designing a new workflow, evaluator, automation loop, or module based on external skills or frameworks.
8. Add `references/fallbacks.md` when facts are missing, the main contradiction is unclear, or the answer is drifting into slogans, roleplay, or overconfidence.
9. Add `references/practice-cards.md` when the user needs a concrete action, experiment, investigation, or review loop.
10. Add `references/constraint-map.md` before route choice when the problem is constrained by material conditions, ownership, organization, information flow, incentives, or ideology.
11. Add `references/risk-and-inversion.md` before recommending actions with meaningful downside, irreversibility, or consequences for others.
12. Add `references/concept-debugging.md` when a concept might become a label rather than an operational tool.
13. Add `references/practice-metrics.md` whenever a practice test, experiment, or review loop is proposed.
14. Add `references/evaluation-rubric.md` when scoring outputs, forward-testing the skill, or deciding whether a response passed.
15. Add `references/evolution-protocol.md` before editing this skill based on a failure, recurring weakness, or new use case.
16. Add `references/coverage-matrix.md` when deciding whether existing scenarios cover a failure mode or a new scenario is needed.

Default MVP routing:

| Problem | Themes | Figures | Protocol |
| --- | --- | --- | --- |
| Industry/company analysis | `political-economy`, `historical-materialism` | `marx-engels`, `deng`, optional `mao` | `industry-analysis` |
| Main contradiction | `dialectics-contradiction` | `mao` | As needed |
| State, party, organization | `class-state-party` | `marx-engels`, `lenin`, `mao` | `organization-strategy` |
| Reform and development stage | `reform-development` | `deng`, optional `mao` | As needed |
| Sinicization | `sinicization`, `historical-materialism` | `mao`, `deng`, then `marx-engels` | As needed |
| Personal practice | `dialectics-contradiction`, `mass-line` when relevant | `mao`, optional `deng` | `personal-practice` |

### Step 3: Analyze

For real-world problems, build the answer in this order:

1. Reality conditions: what is known, what is missing, what must be verified.
2. Scenario gate: object, facts, expected output, and the three questions for the chosen scenario.
3. Constraint map: which material, production-relation, organization, information, incentive, or narrative constraint is decisive.
4. Problem domain: which theme governs the problem.
5. Main contradiction: name the central tension and its main aspect.
6. Interest structure: who gains, who pays, who controls key resources.
7. Stage judgment: what is possible now, not in the abstract.
8. Risk and inversion: how the route fails, whether the test is reversible, and who bears the cost.
9. Route choice: what to do, what not to do, and why.
10. Practice test: smallest action, start/process/result metrics, review point, revision rule.

### Step 4: Output

Use plain language as the main surface, but keep a small amount of Marxist terminology as the analytical skeleton. For real-world answers, use about 2 to 4 terms such as `主要矛盾`, `阶段判断`, `利益结构`, `生产关系`, or `实践检验`. Explain each term in plain language the first time it appears. Do not require the user to know the terms before asking.

Prefer this shape when the user wants analysis:

```text
结论先行：
[一句话判断]

现实条件：
- 已知：
- 缺口：

约束地图：
- 真正卡住的是：
- 需要验证：

主要矛盾：
- 矛盾：
- 主要方面：
- 转化条件：

利益和组织结构：
- 关键主体：
- 资源/权力位置：
- 约束：

阶段判断：
- 现在能做：
- 现在不能做：

风险和反向检验：
- 失败路径：
- 可逆性：
- 停止条件：

实践方案：
- 最小行动：
- 启动/过程/结果指标：
- 复盘时间：
- 修正条件：
```

For concept questions, use:

```text
一句话：
[概念解决的真实问题]

来源和语境：
- 核心文本：
- 历史任务：

操作定义：
- 看什么现实关系：

例子和边界：
- 具体例子：
- 反例/不能用于：

常见误用：
- [误用]
- [修正]
```

## Checkpoints

Before answering, check:

- Did I avoid roleplaying a political figure?
- Did I choose themes before figures?
- Did I run the relevant scenario checkpoint gate before starting the analysis?
- If this is a concept answer, did I debug the concept with example, boundary, and misuse signal?
- Did I name the main contradiction when the user asks about a real problem?
- Did I map the decisive constraint before choosing a route?
- Did I separate known facts from assumptions?
- Did I avoid turning the answer into slogans or quotations?
- Did I avoid reusing the same source cluster as proof for a different problem without checking coverage?
- If borrowing a method from another skill or framework, did I scan mature prior art and name what is transferable?
- Did I check downside, reversibility, and who bears consequences before recommending action?
- Did I provide a practice-testable next step with metrics when action is requested?
- If modules conflict, did I use `references/arbitration.md` instead of smoothing over tension?
- If I cannot make a grounded judgment, did I use `references/fallbacks.md` instead of forcing certainty?

## Failure Modes

| Failure | Repair |
| --- | --- |
| Roundtable answer: "Marx says..., Lenin says..., Mao says..." | Rewrite as one analysis; mention figure modules only as sources |
| Slogan answer | Add reality conditions, contradictions, interests, and practice test |
| Pure textbook answer to real problem | Ask/verify facts, then rerun the workflow |
| Treats all historical stages as the same | Load `references/arbitration.md` and state condition differences |
| Quotes without method | Replace quote pile with concept, source, use, and boundary |
| Starts answering before the scenario is clear | Load `references/scenario-checkpoints.md`; run the shared gate and chosen scenario gate |
| Forces one main contradiction without evidence | Load `references/fallbacks.md`; list candidates and what evidence would decide |
| Action answer stays vague | Load `references/practice-cards.md`; fill one card |
| Optimizes before mapping constraints | Load `references/constraint-map.md`; identify which constraint sets the boundary |
| Recommends risky action without downside | Load `references/risk-and-inversion.md`; define failure path, reversibility, and stop condition |
| Concept answer just repeats the term | Load `references/concept-debugging.md`; give operational definition, example, boundary, and misuse signal |
| Same few source anchors repeat across different questions | Load `references/source-coverage.md`; check whether to broaden source clusters, admit a source gap, or route through a theme |
| New workflow invented without checking mature solutions | Load `references/prior-art-scan.md`; identify candidate prior art, transferable mechanisms, and local fit before editing |
| Practice test has no metric | Load `references/practice-metrics.md`; define start, process, result, contradiction, and review metrics |
| Skill edit has no failure trace | Load `references/evolution-protocol.md`; write a RED failure trace before changing modules |
| Evaluation is based on taste | Load `references/evaluation-rubric.md`; score behavior dimensions and automatic-fail signals |
| A single scenario is treated as comprehensive | Load `references/coverage-matrix.md`; identify covered area, adjacent validation, holdout, and known gaps |

## Reference Index

Core coordination:

- `references/dispatcher.md`: route questions to themes, figures, and protocols.
- `references/scenario-checkpoints.md`: run scenario-specific pre-answer gates before analysis.
- `references/arbitration.md`: resolve tensions between routes and historical stages.
- `references/source-policy.md`: decide what counts as reliable evidence.
- `references/source-map.md`: map methods to source texts.
- `references/source-coverage.md`: prevent repeated source anchors and expose source gaps before overextending a figure module.
- `references/prior-art-scan.md`: check mature external methods before inventing a new workflow or evaluator.
- `references/fallbacks.md`: recover when facts, route, or output quality are failing.
- `references/practice-cards.md`: turn analysis into reusable action, investigation, and review cards.
- `references/practice-metrics.md`: define start, process, result, contradiction, and review metrics for practice tests.
- `references/concept-debugging.md`: turn concepts into operational definitions, examples, boundaries, and misuse checks.
- `references/constraint-map.md`: map material, production-relation, organization, information, incentive, and narrative constraints.
- `references/risk-and-inversion.md`: check failure paths, downside, reversibility, incentives, and stop conditions before action.
- `references/evaluation-rubric.md`: score outputs and identify automatic-fail signals during testing.
- `references/evolution-protocol.md`: evolve the skill through failure traces, bounded edits, validation, and holdout checks.
- `references/coverage-matrix.md`: map scenarios to problem areas, failure modes, modules, and known gaps.
- `references/evaluation-scenarios.md`: pressure-test this skill against realistic prompts.

Themes:

- `references/themes/historical-materialism.md`
- `references/themes/dialectics-contradiction.md`
- `references/themes/political-economy.md`
- `references/themes/class-state-party.md`
- `references/themes/mass-line.md`
- `references/themes/reform-development.md`
- `references/themes/sinicization.md`

Figures:

- `references/figures/marx-engels.md`
- `references/figures/lenin.md`
- `references/figures/mao.md`
- `references/figures/deng.md`

Protocols:

- `references/protocols/industry-analysis.md`
- `references/protocols/personal-practice.md`
- `references/protocols/organization-strategy.md`

Validation:

- Use `references/evaluation-scenarios.md` before deployment or major edits. Score outputs with `references/evaluation-rubric.md`. Use `references/coverage-matrix.md` to decide whether the failure is already covered or needs a new scenario. When a scenario fails, use `references/evolution-protocol.md` to patch the smallest relevant module before retesting.

Examples:

- `examples/demo-conversation.md`: compare weak answers with method-led answers. Use for orientation, not as text to copy.
