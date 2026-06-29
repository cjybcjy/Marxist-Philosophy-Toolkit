---
name: marxist-analysis
description: Use when the user asks for Marxist or Marxism-based analysis of real problems, industries, companies, policy, organization, class, state, contradiction, development stage, reform, mass line, sinicization, or practice-tested action plans. Do not use for generic political roleplay, slogan writing, or historical trivia unless the user asks to analyze the trivia through Marxist method.
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
| Concept | Asks what a theory means | Load the relevant theme and source-map entries |
| Reality analysis | Mentions a company, industry, policy, organization, career, family, project, or social problem | Gather facts first, load `references/source-policy.md` when using current facts, then load themes |
| Practice problem | User wants to act, decide, learn, stop avoiding, or run an experiment | Load `references/protocols/personal-practice.md` plus relevant themes |
| Conflict | Asks why one route differs from another, or whether a theory was betrayed | Load `references/arbitration.md` |
| Source check | Asks "where does this come from" or asks for original texts | Load `references/source-policy.md` and `references/source-map.md` |

If concrete facts would materially change the answer, ask for the minimum missing facts or search/verify when tools are available. Do not pretend to know current facts.

### Step 2: Load References Narrowly

Use progressive disclosure:

1. Start with one protocol or one theme.
2. Add figure modules only when they clarify the method or historical condition.
3. Add `references/arbitration.md` only when sources or routes conflict.
4. Add `references/source-map.md` when the user wants original-text grounding.

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
2. Problem domain: which theme governs the problem.
3. Main contradiction: name the central tension and its main aspect.
4. Interest structure: who gains, who pays, who controls key resources.
5. Stage judgment: what is possible now, not in the abstract.
6. Route choice: what to do, what not to do, and why.
7. Practice test: smallest action, observation metric, review point, revision rule.

### Step 4: Output

Prefer this shape when the user wants analysis:

```text
结论先行：
[一句话判断]

现实条件：
- 已知：
- 缺口：

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

实践方案：
- 最小行动：
- 验证指标：
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

分析用法：
- 可以看什么：
- 不能替代什么：

常见误用：
- [误用]
- [修正]
```

## Checkpoints

Before answering, check:

- Did I avoid roleplaying a political figure?
- Did I choose themes before figures?
- Did I name the main contradiction when the user asks about a real problem?
- Did I separate known facts from assumptions?
- Did I avoid turning the answer into slogans or quotations?
- Did I provide a practice-testable next step when action is requested?
- If modules conflict, did I use `references/arbitration.md` instead of smoothing over tension?

## Failure Modes

| Failure | Repair |
| --- | --- |
| Roundtable answer: "Marx says..., Lenin says..., Mao says..." | Rewrite as one analysis; mention figure modules only as sources |
| Slogan answer | Add reality conditions, contradictions, interests, and practice test |
| Pure textbook answer to real problem | Ask/verify facts, then rerun the workflow |
| Treats all historical stages as the same | Load `references/arbitration.md` and state condition differences |
| Quotes without method | Replace quote pile with concept, source, use, and boundary |

## Reference Index

Core coordination:

- `references/dispatcher.md`: route questions to themes, figures, and protocols.
- `references/arbitration.md`: resolve tensions between routes and historical stages.
- `references/source-policy.md`: decide what counts as reliable evidence.
- `references/source-map.md`: map methods to source texts.
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

- Use `references/evaluation-scenarios.md` before deployment or major edits. The scenarios are designed to catch roundtable answers, slogan answers, missing reality conditions, missing source grounding, and failure to produce a practice test.
