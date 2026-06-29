# Evaluation Scenarios

Use these scenarios to pressure-test `marxist-analysis` after edits. They are not examples to copy verbatim into normal answers; they are pass/fail cards for checking whether the skill routes, reasons, and outputs correctly.

## How To Test

For each scenario:

1. Start with only `SKILL.md`.
2. Load references only as the workflow requires.
3. Produce a concise answer.
4. Check pass/fail criteria.
5. If the answer fails, update the relevant reference file, not the expected answer.

Do not leak these pass criteria into a testing subagent. Give the subagent only the skill path and the user prompt.

## Scenario Index

| Scenario | What it catches |
| --- | --- |
| 1. Industry Analysis | Tech-progress slogans, missing value-chain analysis, unsupported current facts |
| 2. Personal Practice | Motivational filler, no small experiment, Mao roleplay leakage |
| 3. Sinicization Conflict | False all-valid/all-betrayal answers, missing arbitration |
| 4. Organization Strategy | Personality framing, vague discipline advice, no organization experiment |
| 5. Source Challenge | Quote piles, missing source boundary, confusing source with inference |

## Scenario 1: Industry Analysis

**User prompt**

```text
用马哲分析一下 AI 编程工具这个行业：它到底提高了生产力，还是只是换一种方式加强剥削？
```

**Required route**

- `references/dispatcher.md`
- `references/source-policy.md`
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
- `references/protocols/personal-practice.md`
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
- `references/protocols/organization-strategy.md`
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
- `references/source-map.md`
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

## Global Pass Criteria

Across all scenarios, a passing answer must:

- Avoid figure roleplay.
- Load themes before figures.
- Separate known facts from assumptions.
- Preserve tensions instead of smoothing them into slogans.
- End with a practice-testable step when the prompt asks for action.
- Name missing facts when current reality matters.

## Global Failure Signals

- "Marx would say... Lenin would say... Mao would say..." roundtable format.
- "坚持马克思主义" as a conclusion without analysis.
- A quote pile with no method.
- A theory explanation that ignores the user's concrete conditions.
- A grand plan with no smallest next action.
