# Georgia local-government topic dataset

What Georgia county and city governments are discussing on their published agendas and minutes — surveillance cameras (ALPR), data centers, and land use — classified by keyword, with the source document for every mention.

Published by [VoteGA.org](https://votega.org). Start with `latest.json`.

## Coverage

- **25** jurisdictions scanned, of Georgia's 159 counties and ~537 cities.
- Last scan: **2026-09-09**
- Only governments with an automated agenda feed are scanned; a place that is absent is **not covered yet**, which is different from *no mentions found*.

## Mentions by topic

| Topic | Mentions | Jurisdictions |
| --- | --- | --- |
| ALPR / surveillance | 27 | 9 |
| Data centers | 84 | 15 |
| Land use | 508 | 25 |

## ALPR vendors named

| Vendor | Mentions |
| --- | --- |
| Flock Safety | 15 |
| Genetec | 3 |
| Elsag (Leonardo) | 2 |
| Vigilant (Motorola) | 1 |

## Read this before you use it

- **A mention marks discussion, not action.** A topic appearing on an agenda means it *came up* — not that the government approved, funded, or plans to pursue it. It may have been raised in public comment, mentioned in passing, tabled, or voted down. Follow the `sourceUrl` for context.
- **Excerpts are only included for structured sources** (Legistar and Granicus agenda items). Excerpts from OCR'd PDF agendas are withheld: those hits are often public-comment rosters that name residents. OCR mentions still carry tags, matched terms, vendors, confidence, and the source URL.
- **Confidence.** `high` = a named vendor or a spelled-out capability; `medium` = a bare keyword. ALPR excerpts are published only for `high`.
- **Accuracy.** Provided as is, no warranty. Spotted an error? Open an issue.
