# Source Policy

Use this file when grounding claims in texts, history, policy, or current facts.

## Evidence Hierarchy

```text
Primary texts and documents
> authoritative collected works or official document collections
> official or authoritative framework synthesis for taxonomy
> historical records and speeches with context
> peer-reviewed or serious scholarly research
> high-quality secondary interpretation
> web summaries and popular commentary
```

## Author-Only Source Rule

When building source indexes or grounding a figure module, include only the figure's own works:

- works, articles, books, reports, speeches, talks, letters, instructions, prefaces, and jointly authored texts;
- authoritative collected works when they preserve the authored text;
- verbatim excerpts from a biography or chronology only when the titled original work is identifiable.

Exclude:

- biographies, memoirs about the figure, textbooks, readers' guides, popular explainers, business-strategy reinterpretations, and AI summaries;
- later party, academic, or commentator interpretations unless the answer explicitly asks for later interpretation;
- book-search metadata, covers, catalog blurbs, and table-of-contents snippets as evidence.

External book-search sites can help identify candidate titles or editions, but a search result is only a bibliographic hint. Do not treat it as `primary-text`.

## Framework Synthesis Rule

Basic-principles textbooks and systematic theory courses can be used as `framework-synthesis`:

- Use them to organize concept families, teaching order, and standard distinctions.
- Use them to decide whether a question belongs to dialectical materialism, epistemology, historical materialism, political economy, or reform-development.
- Use them to standardize reusable templates.

Do not use them as proof that Marx, Engels, Lenin, Mao, or Deng personally made a claim. For source authority, return to primary texts and source indexes.

## Source Rules

- Distinguish text, context, later interpretation, and inference.
- Do not quote without explaining the method the quote supports.
- Do not use isolated slogans as proof.
- Do not treat repeated use of the same source cluster as stronger evidence; load `source-coverage.md` when anchors repeat across unrelated questions.
- For translated texts, note that translation may affect terms.
- For current facts, verify with current sources when tools are available.
- When evidence is weak, say what is missing.

## Current-Fact Rule

If an answer uses a current fact, market claim, study result, law, price, company status, public figure position, or recent policy:

1. Verify it with current tools when available.
2. Mark it as `current-fact`.
3. Name the source or source type and date if known.
4. If not verified in the current session, say so and treat it as an evidence gap.

Do not mix current-fact claims into theoretical analysis as if they were stable background knowledge.

## Source Status Tags

Use these labels when grounding an answer:

| Tag | Meaning |
| --- | --- |
| `primary-text` | Direct work, speech, report, letter, or official document |
| `historical-context` | Material conditions, political conflict, institutional setting around the text |
| `framework-synthesis` | Textbook or systematic theory framework used for taxonomy, ordering, or standard method extraction |
| `later-interpretation` | A scholar, party document, commentator, or later tradition interpreting the text |
| `inference` | The agent's own application of a method to the user's problem |
| `current-fact` | A fact about today's market, law, company, person, or policy that may change |

Never present `inference` as if it were `primary-text`.

## Source Index Protocol

When the user asks for source grounding, method granularity, or whether a figure corpus is strong enough:

1. Load `source-map.md`.
2. Load the relevant source-index file.
3. Identify whether the needed support is `primary-text`, `historical-context`, `later-interpretation`, or `inference`.
4. If only secondary material is available, say the author-only source is missing.
5. If using a case analogy, load `cases/figure-case-calibration.md` and name both the shared mechanism and the different conditions.

## Citation Use

Use citations to support:

- a concept's origin,
- the historical problem it answered,
- the boundary of the method,
- a disputed interpretation.

Do not use citations to decorate a generic conclusion.

## Grounding Protocol

When the user challenges the evidence or asks "where does this come from":

1. Name the method being used.
2. Give the source cluster, not a quote pile.
3. Explain the historical problem the source addressed.
4. State what part is direct source and what part is your application.
5. State the boundary and missing facts.

For current events, current law, current policy, prices, leadership positions, and market facts, browse or otherwise verify before making a factual claim.

## Source Gap Language

When evidence is incomplete, use:

```text
这里可以先作方法判断，但事实判断还缺 X。
如果 X 为真，结论倾向 A；如果 X 不成立，结论要改成 B。
```

## Translation And Term Caution

Terms like "productive forces," "relations of production," "state," "class," "practice," and "contradiction" carry translation and tradition-specific meanings. When precision matters, avoid overloading a single English or Chinese keyword; explain the operational meaning in the answer.
