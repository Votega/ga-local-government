# ga-local-government
Machine readable data on county/city legislative bodies and elected officials. 

## Georgia local-government topic dataset
What Georgia county and city governments are discussing on their published agendas and minutes — surveillance cameras (ALPR), data centers, and land use — classified by keyword, with the source document for every mention.

## Read this before you use it
A mention marks discussion, not action. A topic appearing on an agenda means it came up — not that the government approved, funded, or plans to pursue it. It may have been raised in public comment, mentioned in passing, tabled, or voted down. Follow the sourceUrl for context.
Excerpts are only included for structured sources, excerpts from OCR'd PDF agendas are withheld: those hits are often public-comment rosters that name residents. OCR mentions still carry tags, matched terms, vendors, confidence, and the source URL. Confidence. high = a named vendor or a spelled-out capability; medium = a bare keyword. ALPR excerpts are published only for high.

Published by VoteGA.org. Start with latest.json.

## Local officials

`data/officials/officials.json` (and `.csv`) is each county commission's and city council's board **as of** `metadata.asOf`: who holds each seat that day. `data/officials/officials-history.json` keeps every recorded holder of every seat, one row per person per term, with `takes_office` and `leaves_office` (exclusive) dates. History is not backfilled; it starts at `metadata.historyStartsAt`. `data/officials/manifest.json` lists the files.

**January 2027:** officials elected in 2026 take office on 1 January 2027, and 47 current officials leave that day. The current-board file changes at the first publish on or after that date (publishes run Mondays and Thursdays, so Monday 4 January). The outgoing officials stay in `officials-history`.

Both files carry `term_provenance`, which says how a row's term dates were established: `verified` (a person confirmed them against a source), `assumed` (derived from the election year and the body's term rules), `unknown` (no basis), or blank (`null`, not yet reviewed). Most rows are not yet reviewed.

## School districts

`data/school-districts/districts.json` (and `.csv`, with `districts.schema.json`) lists every Georgia school district: 159 county systems and 21 independent city systems, keyed by `districtId`, the state's own district code. `data/school-districts/manifest.json` lists the files.

- `countyFips` is every county a system is recorded as serving; join it to `fips` in `data/places.json`. It is **not** a boundary and does not say which district serves a given address.
- `boardSize`, `termYears`, `partisan` and `officialUrl` are `null` where not yet recorded.
- Board members are not included.
- `metadata.generatedAt` is when the registry last changed, not when it was last published.
- District identifiers come from [Georgia Civic Data](https://georgiacivicdata.org) (CC BY 4.0; GOSA and NCES codes). Service counties were checked against Georgia Department of Revenue millage reports.

## Linking to this data

- **A fixed point in time:** use `officials-history`, filtered by `takes_office` and `leaves_office`, or link a commit (`https://raw.githubusercontent.com/Votega/ga-local-government/<commit>/...`) for an exact copy.
- **Whatever is current:** read `data/officials/officials.json` or `latest.json`. They are rewritten in place; `metadata.asOf` says which day the board describes.

Changes that affect consumers are listed in [`CHANGES.md`](CHANGES.md).

# License, Reuse, and attribution
The data in this repository is published by VoteGA.org under the Creative Commons Attribution-ShareAlike 4.0 International license [CC-BY-SA-4.0](https://github.com/Votega/ga-local-government?tab=CC-BY-SA-4.0-1-ov-file). 

You are free to share and adapt this data, including commercially, provided you give appropriate credit and license any adaptations you distribute under the same terms (CC BY-SA 4.0). VoteGA's license covers the compilation, cleaning, and joins in this repository. The underlying facts come from the published agendas and minutes of Georgia county and municipal governments.

The data is provided as is, with no warranty. 

# Provenance
Generated and published automatically from https://github.com/Votega/votega.org. Do not edit files here by hand — the next publish overwrites them.

# Contact
Spotted an error? Open an issue on this repository, or email admin@votega.org.
