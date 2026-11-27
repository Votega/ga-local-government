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

- **68** jurisdictions scanned, of Georgia's 159 counties and ~537 cities.
- Last scan: **2026-11-27**
- Only governments with an automated agenda feed are scanned; a place that is absent is **not covered yet**, which is different from *no mentions found*.

## Mentions by topic

| Topic | Mentions | Jurisdictions |
| --- | --- | --- |
| ALPR / surveillance | 84 | 32 |
| Data centers | 180 | 39 |
| Land use | 766 | 65 |
| Local taxes & referenda | 572 | 64 |

## ALPR vendors named

| Vendor | Mentions |
| --- | --- |
| Flock Safety | 26 |
| ShotSpotter (SoundThinking) | 3 |
| Genetec | 2 |
| Skydio | 2 |
| Verra Mobility | 1 |
| Fusus (Axon) | 1 |
| Axon Fleet | 1 |

## Read this before you use it

- **A mention marks discussion, not action.** A topic appearing on an agenda means it *came up* — not that the government approved, funded, or plans to pursue it. It may have been raised in public comment, mentioned in passing, tabled, or voted down. Follow the `sourceUrl` for context.
- **What the minutes record (`followThrough`, `outcomes`).** Where we read a place's recorded votes (CivicClerk, Legistar and IQM2 portals), a mention carries the same meeting's recorded items whose caption names the topic, joined on the portal's own meeting id: the body's result wording (`resultText`), vote counts, and where the item goes next. `result` is `passed`/`failed` only for adopted or failed wording; held, referred and committee recommendations are steps, not outcomes. `followThrough` null means we hold no recorded-votes record for that meeting, which says nothing about what happened. `textDisagrees` marks a vote whose minutes contradict themselves; read the minutes.
- **A quoted excerpt is included only when `context` is `agenda-action`** — the topic surfaced as government business (an item, motion, resolution, or a formal public hearing). Excerpts for `public-comment` and `unknown` context are withheld: public-comment hits are often sign-up rosters that name residents. Those mentions still carry tags, matched terms, vendors, confidence, context, and the source URL — everything but the quote.
- **Confidence.** `high` = a named vendor or a spelled-out capability; `medium` = a bare keyword. ALPR excerpts are published only for `high`.
- **How it is classified.** Keyword rules, published in full in `data/keywords.json`. A keyword list has false positives (a word that means something else) and false negatives (a document that discusses the topic in words we do not list) — a missing mention is not proof of absence. Proposed additions or corrections are welcome as issues.
- **Accuracy.** Provided as is, no warranty. Spotted an error? Open an issue.
