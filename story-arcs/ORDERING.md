# A note on ordering quality

Arcs in this folder come from two sources, and they are **not** equally reliable.

## `source: "League of Comic Geeks"` — 13 arcs

Publication-order reading lists curated by LoCG. Issues from different titles are
correctly **interleaved**, and each entry carries a role:
`PROLOGUE` / `CORE ISSUE` / `TIE-IN` / `EPILOGUE`, plus a release date.

These are the ones to trust.

## Everything else — derived from `.cbl` files

The `.cbl` reading lists were the original source. Their quality varies: many are
properly interleaved, but a substantial number **group all issues of a title into
a block** instead of interleaving them, which reads out of sequence.

Scoring all multi-title arcs by the share of entries sitting in a run of 3+
consecutive issues of the same series:

| Quality | Arcs |
|---|---|
| well interleaved (<30% blocked) | 143 |
| mixed (30-59%) | 34 |
| likely collapsed (>=60%) | 50 |
| single-title (nothing to interleave) | 6 |

13 of the 50 collapsed arcs have been replaced with LoCG data. The remaining 37
are **not** available as LoCG events — their catalogue has 328 events and does not
include them.

Example of the problem, from the original `one-world-under-doom.cbl`:

```
  4-8.  Doctor Strange of Asgard #1,2,3,4,5     <- whole mini in a block
 22-26. Thunderbolts: Doomstrike #1..5          <- whole mini in a block
```

versus the LoCG order now published for the same arc, which interleaves those
against the main series by release date.
