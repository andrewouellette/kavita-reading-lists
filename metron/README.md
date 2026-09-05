# Metron reading lists

Reading lists exported from [Metron](https://metron.cloud) via its REST API.

These are **separate from the lists in the repository root** — nothing here
overwrites or merges with those. The root `.cbl` files are hand-maintained;
these are generated.

## Contents

- `*.cbl` — one file per list, in the same ComicBookLover format as the root
  lists, so Kavita and CCL read them without conversion.
- `index.json` — machine-readable catalogue: list name, filename, issue count,
  list type, and the original attribution (e.g. League of Comic Geeks) with its
  source URL.

## Field mapping

| CBL attribute | Metron source |
|---|---|
| `Series` | `issue.series.name` |
| `Number` | `issue.number` |
| `Volume` | `issue.series.year_began` |
| `Year`   | year of `issue.cover_date` |

Books are written in Metron's `order` field, which is the curated reading
order rather than publication order.

## Regenerating

Metron's documented limits are **20 requests/minute (burst)** and
**5,000/day (sustained)**. The exporter paces at 3.2s between requests
(~18.75/min) and backs off on any 429. A full run is ~860 requests, about 17%
of the daily allowance.
