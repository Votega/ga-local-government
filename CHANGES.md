# Changes

Changes to this repo's files that a consumer may need to act on. Routine data refreshes are not listed.

## New: school districts

- `data/school-districts/` publishes every Georgia school district (JSON, CSV, JSON Schema, manifest). Schema 1.0.0.

## Officials schema 1.1.0: `term_provenance`

- `officials.json`, `officials.csv`, `officials-history.json` and `officials-history.csv` gain `term_provenance` (`verified`, `assumed`, `unknown` or blank). It is the **last** column of each CSV; no existing column moved. No new required field.

## Coming: January 2027, new local officials

- Officials elected in 2026 take office on 1 January 2027. From the first publish on or after that date (Monday 4 January), `data/officials/officials.json` and `.csv` list them, and the 47 officials leaving that day drop out of the current board.
- The outgoing officials stay in `data/officials/officials-history.json` and `.csv`, with `leaves_office` set to 2027-01-01.
