# Story Arc Reading Orders

258 comic story arcs with complete reading order, exported from ComicBookList
(`.cbl`) files. Continuity timelines and full-series runs are deliberately
excluded — these are story arcs only.

## Files

| File | Contents |
|---|---|
| `index.json` | every arc: name, slug, issue count, owned count |
| `<slug>.json` | one arc, full ordered entry list |
| `all-arcs.csv` | every entry flattened: `arc, order, series, issue, volume, year, owned` |

## Per-arc shape

```json
{
  "arc": "Secret Wars",
  "slug": "secret-wars",
  "issue_count": 229,
  "owned_count": 118,
  "entries": [
    { "order": 1, "series": "New Avengers", "issue": "1",
      "volume": "2013", "year": "2013", "owned": true }
  ]
}
```

## Notes

- `order` is the **complete** arc reading order taken from the CBL, not a
  subset. Arcs list every issue whether or not it is currently held.
- `owned` reflects the source library at export time and is informational —
  ignore it if you only want the reading order.
- `series` + `volume` + `issue` are the fields to match on. `volume` is the
  series start year, which disambiguates same-named runs (e.g. Batman 1940 vs
  2016 vs 2025).
- Format is intentionally schema-neutral so it can be mapped to whatever an
  importer expects.
