# Source Coverage

Use this file when an answer may be overusing the same source anchors, the user says the skill has too few arguments, or a figure module is being stretched beyond its source base.

## Core Rule

```text
Do not treat the same famous texts as proof for every problem.
Use sources to locate a method, then test whether that method actually covers the user's object.
```

Source coverage means the answer has enough relevant source clusters for the task. It does not mean adding more quotations.

## When To Load

Load this with `source-map.md` and `source-policy.md` when:

- The user complains that answers repeat the same articles, slogans, or examples.
- A long conversation keeps returning to the same source anchors.
- A figure module has only a small built-in corpus and no external text repository is available.
- The answer must compare themes, figures, stages, or historical tasks.
- The user asks for original-text grounding beyond the current source map.

## Coverage Ledger

Before answering, make this quick ledger:

```text
Question type:
- concept / reality analysis / practice / source challenge / skill evolution

Source clusters already used:
- [text or cluster]

Source clusters required by this question:
- [theme source]
- [figure source if needed]
- [current fact source if needed]

Coverage decision:
- enough / broaden source map / admit source gap / verify externally
```

Do not show the full ledger unless the user asks how the answer is sourced. Use it to prevent silent repetition.

## Decision Rules

| Situation | Do |
| --- | --- |
| Same source supports the same method across turns | Reuse the method, not the quote; add new facts or a new application boundary |
| Same source is being used for unrelated domains | Broaden to another theme, figure module, or source cluster in `source-map.md` |
| Figure module has too few anchors | State the coverage boundary and route through the relevant theme module |
| Exact textual support is requested but unavailable | Say the corpus is not available in the current context and name what must be checked |
| Current facts are needed | Use `source-policy.md`; do not replace current evidence with classic texts |
| More citations would all come from the same text | Do not pad; one precise anchor plus boundary is better than a quote pile |

## Minimum Diversity Rules

- For a single concept answer, one primary source cluster is enough if the method and boundary are clear.
- For a real-world analysis, use at least one method source cluster plus the user's concrete facts or verified current facts.
- For a cross-theme answer, use one source cluster per theme that materially changes the analysis.
- For a figure-led answer, name the figure's historical task and say when the figure module is insufficient.
- Do not count multiple passages from one text as diverse evidence.

## Output Pattern

Use this compact pattern when the user explicitly asks about source coverage:

```text
来源覆盖判断：
- 已用来源：
- 这次问题还需要：
- 当前不足：
- 怎么补：

本轮回答边界：
- 可以作方法判断：
- 暂不能作事实/原文判断：
```

## Anti-Patterns

- Reusing `On Contradiction`, `On Practice`, or `On Protracted War` as a universal answer key.
- Treating citation count as source diversity.
- Hiding a source gap behind confident theory language.
- Expanding a figure's voice when the problem needs a theme, protocol, or current facts.
- Adding full-text corpora into the skill body instead of routing to searchable references.
