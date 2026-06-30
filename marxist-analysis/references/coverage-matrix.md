# Coverage Matrix

Use this file when deciding whether the evaluation suite is broad enough, where a new failure belongs, or whether to add a new scenario before editing a module.

## Core Rule

```text
One scenario proves one failure mode, not total coverage.
```

Use `evaluation-scenarios.md` to test behavior, `evaluation-rubric.md` to score behavior, and this matrix to see what remains uncovered.

## Problem Coverage

| Problem Area | Current Scenarios | Primary Modules | Covered Failure Modes | Known Gaps |
| --- | --- | --- | --- | --- |
| Scenario gating | 11. Scenario Checkpoint Gate | `scenario-checkpoints.md`, `dispatcher.md`, `fallbacks.md` | Answering before object, facts, and expected output are clear | Automated gate tracing |
| Theory framework and method templates | 14. Framework Synthesis And Method Templates | `theory-framework.md`, `method-templates.md`, `source-policy.md`, `concept-debugging.md` | Raw original-text pile, textbook-only answer, no standard procedure, historical conclusion treated as universal method | More template-specific forward tests |
| Industry or company analysis | 1. Industry Analysis | `scenario-checkpoints.md`, `protocols/industry-analysis.md`, `themes/political-economy.md`, `themes/historical-materialism.md`, `constraint-map.md`, `source-policy.md` | Tech-progress slogans, missing value chain, unsupported current facts | Imperialism/global supply chain, finance/asset pricing, platform governance |
| Personal practice and learning | 2. Personal Practice; 6. Fallback And Practice Cards; 7. Constraint And Risk Gate | `protocols/personal-practice.md`, `practice-cards.md`, `practice-metrics.md`, `risk-and-inversion.md`, `fallbacks.md` | Motivation filler, no small experiment, forced certainty, risky all-in advice | Long-cycle habit review, family/work constraint negotiation |
| Organization and route conflict | 4. Organization Strategy | `protocols/organization-strategy.md`, `themes/class-state-party.md`, `themes/dialectics-contradiction.md`, `practice-cards.md` | Personality framing, vague discipline advice, no organization experiment | Larger institutions, formal authority, coalition and legitimacy analysis |
| Sinicization and historical tension | 3. Sinicization Conflict | `arbitration.md`, `themes/sinicization.md`, `themes/historical-materialism.md`, figure modules | All-valid/all-betrayal answers, missing arbitration | Later Chinese theory modules not yet implemented |
| Source grounding and coverage | 5. Source Challenge; 10. Source Coverage And Argument Reuse; 13. Author-Only Source And Case Calibration | `source-policy.md`, `source-map.md`, `source-coverage.md`, source-index files, `concept-debugging.md` | Quote piles, source-as-proof, missing boundary, repeated source anchors, hidden corpus gaps, secondary commentary treated as author text | Citation depth for long original texts, automated source-use ledger |
| Historical case calibration | 13. Author-Only Source And Case Calibration | `cases/figure-case-calibration.md`, source-index files, `source-policy.md`, affected figure module | Inspirational case stories, false analogy, business metaphor treated as proof, missing condition difference | More domain-specific cases beyond current figure set |
| Concept debugging | 8. Concept Debugging | `concept-debugging.md`, relevant themes, `source-map.md` | Jargon as understanding, no example, no misuse boundary | More concepts beyond productive forces/relations |
| Skill evolution | 9. Skill Evolution | `evolution-protocol.md`, `evaluation-rubric.md`, `evaluation-scenarios.md`, this file | Whole-skill rewrite, taste-based scoring, no validation gate | Automated scoring scripts, real output archive |
| Prior-art reuse | 12. Prior-Art Reuse Gate | `prior-art-scan.md`, `evolution-protocol.md`, `source-policy.md` | Reinventing workflow or optimizer, vague "borrow SkillOpt" claims, copying without fit check | Automated prior-art search and structured source cache |

## Failure-Mode Coverage

| Failure Mode | Covered By | Patch First | Add Scenario When |
| --- | --- | --- | --- |
| Missing checkpoint gate | Scenario 11 | `scenario-checkpoints.md`, `SKILL.md` | A new scenario family needs its own pre-answer questions |
| Raw original texts with no system or procedure | Scenario 14 | `theory-framework.md`, `method-templates.md` | A new theory family needs its own template |
| Textbook framework treated as primary proof | Scenario 14 | `source-policy.md`, `theory-framework.md` | A specific textbook corpus becomes first-class |
| Figure roleplay or roundtable | Global criteria, scenarios 2 and 9 | `SKILL.md`, `fallbacks.md` | It appears in a new domain not covered by current prompts |
| Slogan answer | Scenarios 1, 6, 9 | `fallbacks.md`, affected theme/protocol | The slogan comes from a specific new concept or domain |
| Current-fact hallucination | Scenario 1 | `source-policy.md`, affected protocol | The topic involves policy, law, market data, war, election, or public office |
| Repeated source anchors or argument overfit | Scenario 10 | `source-coverage.md`, `source-map.md`, `fallbacks.md` | The repetition appears in a new source family or external corpus |
| Secondary commentary treated as primary text | Scenarios 5, 10, and 13 | `source-policy.md`, source-index files | A new figure source family is added |
| False historical analogy | Scenario 13 | `cases/figure-case-calibration.md`, affected figure module | Case analogies become a recurring answer pattern in a new domain |
| Missing value chain or interest map | Scenario 1 | `protocols/industry-analysis.md`, `themes/political-economy.md`, `constraint-map.md` | The failure appears outside industry/company analysis |
| Forced main contradiction | Scenario 6 | `fallbacks.md`, `themes/dialectics-contradiction.md` | The answer forces certainty in a new task family |
| No action or experiment | Scenarios 2, 4, 6 | `practice-cards.md`, affected protocol | The task has a new action context |
| Practice without metrics | Scenarios 2, 4, 6, 7 | `practice-metrics.md` | Metrics need a new type, not just a missing fill-in |
| Risky advice without downside | Scenario 7 | `risk-and-inversion.md` | New high-stakes domain appears |
| Concept used as label | Scenario 8 | `concept-debugging.md`, relevant theme | A recurring concept lacks example/boundary guidance |
| Historical tension flattened | Scenario 3 | `arbitration.md`, relevant theme/figure | A new historical stage or figure module is added |
| Self-evolution without evidence | Scenario 9 | `evolution-protocol.md`, `evaluation-rubric.md` | A new maintenance workflow appears |
| Reinventing mature workflow | Scenario 12 | `prior-art-scan.md`, `evolution-protocol.md` | A new external method family is being borrowed |

## Gap Backlog

Add scenarios before adding large new modules for these areas:

| Gap | Why It Matters | Likely Scenario Type |
| --- | --- | --- |
| Policy analysis | Policy questions are current-fact sensitive and can become slogan answers | Validation |
| Imperialism and global supply chains | Lenin module exists but no dedicated modern supply-chain pressure test | Train |
| Finance, asset pricing, and financialization | Industry answers may miss capital markets and rent extraction | Train |
| Ideology, media, and cultural leadership | Current MVP does not include Gramsci or ideology-specific routing | Holdout or validation |
| Mass investigation with real users | `mass-line.md` exists, but there is no scenario testing调查研究 versus polling | Train |
| Later Chinese theory modules | `jiang`, `hu`, `xi` are not implemented; avoid pretending coverage exists | Add only after source modules exist |
| More source-index depth | Current source indexes are navigation maps, not full bibliographies or citation databases | Validation |
| More case families | Current case map covers core figure methods but not finance, platform governance, or later Chinese theory cases | Validation |
| Textbook framework source selection | The framework layer does not yet name a specific edition or corpus of official textbooks | Validation |

## Maintenance Rule

Update this matrix only when:

- A scenario is added, removed, or regrouped.
- A new module becomes a first-class route.
- A recurring failure reveals an uncovered problem area.
- A gap is intentionally deferred so future maintainers do not mistake absence for coverage.

Do not update it for one-off wording changes.
