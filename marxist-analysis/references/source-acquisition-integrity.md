# Source Acquisition And Integrity

Use this file when supplementing book materials, searching online catalogs or repositories, selecting editions, or checking whether a text may be altered, incomplete, or unreliable.

## Core Rule

```text
Search broadly, ingest narrowly, verify before using.
```

Online search results are leads. They are not source authority. A text enters the toolbox only after its author, edition, publication metadata, source status, and integrity checks are recorded.

## Source Tiering

| Tier | Source type | Use | Risk |
| --- | --- | --- | --- |
| T0 | User-provided local scans/PDFs with visible edition pages | Candidate text for manual verification | May still be OCR-damaged, excerpted, or altered |
| T1 | Official publishers, official collected works pages, government/party theory portals, university press catalogs | Edition metadata and sometimes authoritative text | Site pages can be updated; record access date |
| T2 | Reputable public archives and library catalogs | Cross-check title, author, volume, translation, and table of contents | Not always official; translations vary |
| T3 | Scholarly citations, library records, ISBN databases | Bibliographic verification | Metadata can be incomplete |
| T4 | Book-search/shadow-library sites, mirrors, file-sharing pages, random OCR text | Discovery only: candidate titles, editions, file existence | High risk: copyright issues, missing pages, OCR corruption, malicious edits |

Do not use T4 as evidence. Use it only to discover a candidate that must be checked against higher-tier sources.

## Acquisition Ledger

For every candidate book or text, record:

```text
Title:
Author:
Translator/editor:
Edition/volume:
Publisher:
Year:
ISBN or collection identifier:
Source URL or local path:
Access date:
Source tier:
File/hash if local:
Status: candidate / verified / partial / suspect / rejected
Reason:
```

Do not add a title to `source-index/` unless its status is `verified` or the entry clearly states a limited `partial` status.

## Integrity Check

Before using a candidate text:

1. Check front matter: title page, author, translator/editor, publisher, edition, year, ISBN, copyright page, volume number.
2. Compare bibliographic metadata against at least one higher-tier source.
3. Compare table of contents or chapter order against an authoritative edition when available.
4. Select 3 to 5 anchor passages from important chapters and compare them against a trusted scan, official page, or another independent edition.
5. Check dates, names, terminology, and section headings for anachronisms or inserted language.
6. Check whether the file is abridged, excerpted, machine-translated, OCR-only, or missing pages.
7. Record suspicious differences before using the text.

## Tampering Signals

Treat a text as `suspect` until resolved if it has:

- no title/copyright/edition page;
- mismatched author, title, translator, publisher, or year;
- chapter order that differs from authoritative editions without explanation;
- missing sections, unexplained additions, or modern phrases inserted into old texts;
- inconsistent political terms across chapters in a way that does not match translation history;
- OCR errors that change concepts, negations, numbers, dates, names, or logical connectors;
- page images that do not match the OCR text;
- file metadata claiming an edition that the visible pages do not support;
- search-site metadata only, with no verifiable text or edition page.

## Acceptance Decision

| Status | Meaning | Skill use |
| --- | --- | --- |
| `candidate` | Found but not checked | Do not cite or index |
| `verified` | Edition and anchor passages match reliable sources | Can enter source index |
| `partial` | Some parts verified but text is incomplete or excerpted | Use only the verified part and state boundary |
| `suspect` | Inconsistency exists | Do not use for claims; investigate or replace |
| `rejected` | Altered, wrong, untraceable, or too damaged | Do not use |

## Copyright And Storage Rule

Do not store or redistribute copyrighted full texts inside this skill. Store only:

- bibliographic metadata;
- source status and verification notes;
- short source anchors;
- method extraction and boundaries;
- links to official or lawful access pages when available.

## Minimal Online Search Plan

When more book materials are needed:

1. Search official publisher/library/portal sources first.
2. Search public archives and catalogs next.
3. Use book-search sites only to discover candidate title/edition strings.
4. Prefer edition metadata over file availability.
5. Run the integrity check before adding any new source anchor.

## Output Pattern

When reporting a source acquisition decision:

```text
资料判断：
- 候选书：
- 来源层级：
- 版本信息：
- 校对结果：
- 风险：
- 结论：verified / partial / suspect / rejected
- 入库方式：
```

## Anti-Patterns

- Treating a search result as proof that a text is authentic.
- Adding a book because it is easy to download.
- Using a file with no visible edition page.
- Comparing only title and author while ignoring translator, volume, and year.
- Letting a corrupted OCR passage become a method rule.
- Mixing copyrighted full text into the skill repository.
