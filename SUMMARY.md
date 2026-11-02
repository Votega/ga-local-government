# Georgia local-government topic dataset

What Georgia county and city governments are discussing on their published agendas and minutes — surveillance cameras (ALPR), data centers, and land use — classified by keyword, with the source document for every mention.

Published by [VoteGA.org](https://votega.org). Start with `latest.json`.

**This repository carries more than one dataset.** `latest.json` and the files
it names are the agenda-mention dataset, refreshed twice weekly. Property tax
millage rates are published here too, on their own annual cadence. Each dataset
describes itself in `data/<dataset>/manifest.json`, so listing
`data/*/manifest.json` tells you what is here. A manifest's `generatedAt` is
when the DATA was produced, which is not when it was last mirrored — which is
why no single file in this repo claims to state the freshness of all of it.
Manifests carry no wall-clock time, so an unchanged dataset republishes
identically; when a file was last written is in this repo's git history.

## Coverage

- **59** jurisdictions scanned, of Georgia's 159 counties and ~537 cities.
- Last scan: **2026-11-02**
- Only governments with an automated agenda feed are scanned; a place that is absent is **not covered yet**, which is different from *no mentions found*.

## Mentions by topic

| Topic | Mentions | Jurisdictions |
| --- | --- | --- |
| ALPR / surveillance | 76 | 29 |
| Data centers | 159 | 33 |
| Land use | 686 | 55 |
| Local taxes & referenda | 493 | 56 |

## ALPR vendors named

| Vendor | Mentions |
| --- | --- |
| Flock Safety | 23 |
| Genetec | 2 |
| Skydio | 2 |
| Fusus (Axon) | 2 |
| ShotSpotter (SoundThinking) | 2 |
| Avigilon (Motorola) | 1 |
| Axon Fleet | 1 |

## Read this before you use it

- **A mention marks discussion, not action.** A topic appearing on an agenda means it *came up* — not that the government approved, funded, or plans to pursue it. It may have been raised in public comment, mentioned in passing, tabled, or voted down. Follow the `sourceUrl` for context.
- **A quoted excerpt is included only when `context` is `agenda-action`** — the topic surfaced as government business (an item, motion, resolution, or a formal public hearing). Excerpts for `public-comment` and `unknown` context are withheld: public-comment hits are often sign-up rosters that name residents. Those mentions still carry tags, matched terms, vendors, confidence, context, and the source URL — everything but the quote.
- **Confidence.** `high` = a named vendor or a spelled-out capability; `medium` = a bare keyword. ALPR excerpts are published only for `high`.
- **How it is classified.** Keyword rules, published in full in `data/keywords.json`. A keyword list has false positives (a word that means something else) and false negatives (a document that discusses the topic in words we do not list) — a missing mention is not proof of absence. Proposed additions or corrections are welcome as issues.
- **Accuracy.** Provided as is, no warranty. Spotted an error? Open an issue.
