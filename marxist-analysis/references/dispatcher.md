# Dispatcher

Use this file to route a user question before loading detailed modules.

## First Split

| User asks | Treat as | Load first |
| --- | --- | --- |
| "What does X mean?" | Concept explanation | Relevant theme, then `source-map.md` |
| "Analyze this industry/company/policy" | Reality analysis | Relevant protocol, then themes |
| "What is the main contradiction?" | Contradiction diagnosis | `themes/dialectics-contradiction.md` |
| "What should I do?" | Practice problem | `protocols/personal-practice.md` |
| "Why did A differ from B?" | Route conflict | `arbitration.md` |
| "Where does this come from?" | Source grounding | `source-policy.md`, `source-map.md` |

If the question includes a current company, market, law, policy, price, schedule, election, war, or public figure's current position, verify current facts before analysis when tools are available.

## Routing Table

| Problem domain | Themes | Figures | Notes |
| --- | --- | --- | --- |
| Capital, commodity, labor, profit, exploitation | `political-economy`, `historical-materialism` | `marx-engels` | Start from production relation and value chain, not morality |
| Imperialism, state machine, party, revolutionary organization | `class-state-party` | `lenin`, `marx-engels` | Ask what apparatus controls coercion and coordination |
| Main contradiction, strategy, investigation, mass line | `dialectics-contradiction`, `mass-line` | `mao` | Move from contradiction to concrete practice |
| Development stage, productivity, reform, opening, policy tradeoff | `reform-development`, `historical-materialism` | `deng`, optional `mao` | Ask what stage permits and blocks |
| Sinicization, practice standard, adapting theory to conditions | `sinicization`, `historical-materialism` | `mao`, `deng`, then `marx-engels` | Explain continuity through method, not identical conclusions |
| Personal execution, avoidance, learning loop, small experiment | `dialectics-contradiction`, optional `mass-line` | `mao`, optional `deng` | Convert issue into "main contradiction -> base area -> practice test" |
| Organization conflict | `class-state-party`, `mass-line`, `dialectics-contradiction` | `lenin`, `mao` | Separate line conflict, resource conflict, and communication conflict |

## Minimal Fact Questions

Ask only what changes the analysis:

- What is the concrete object: person, organization, company, industry, policy, or personal problem?
- What is the current stage: early exploration, growth, crisis, transition, or consolidation?
- Who are the main actors and what resources do they control?
- What decision must be made now?
- What would count as a small successful test in 7 to 14 days?

If the user gives enough context, proceed without turning the interaction into a questionnaire.
