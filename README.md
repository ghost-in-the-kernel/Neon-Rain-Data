# neon-rain-data

The datasets Neon Rain reads, as plain git files. Maintainer: Ghost (GitHub: ghost-in-the-kernel).

This repository is **private**, holds **no code**, and is read only by Neon Rain
(`ghost-in-the-kernel/neon-rain`, also private). It is a subset of Neon Rain: the part that is bytes of
data, kept out of the code repository's history (R-016 (a) in Neon Rain's `theGhost.md`). Everything
about how a dataset was made, checked and hashed lives in Neon Rain; this file only says where to look.

## Layout

One line per folder. "Manifest row" is the row in Neon Rain's `data/MANIFEST.md` that records the hash.

- `raw/wiki/`: Quandl's WIKI prices export, as Nasdaq Data Link gave it (`qopts.export=true`, snapshot
  2026-02-03): one zip (463,198,483 bytes) split into five parts `WIKI_PRICES.zip.part-aa` to `-ae` (each
  under 100 MB), plus `SHA256`, the hash of the joined zip. The zip holds one CSV of 14 columns. Source:
  Quandl WIKI/PRICES via Nasdaq Data Link. License: described as public domain, unverified; Nasdaq Data Link's terms apply; Ghost's check open (2026-10-25).
  Made by: Ghost's session fetch (J-042), split to stay under 100 MB; rejoin with
  `cat WIKI_PRICES.zip.part-* > WIKI_PRICES.zip`. Hash: manifest row `wiki-prices-raw`, sha256
  `d1b89242ebaf629e541f2a3c77c718f01819fa72dc687a30dadc764c8983e3f6`.
- `wiki/prices/`: the sample of the raw export, 1998-01-02 to 2017-11-07 (R-026), one parquet file per
  year (`1998.parquet` to `2017.parquet`, 20 files, none over 30 MB), columns as exported, rows sorted by
  ticker then date; and `index.tsv` (year, file, SHA-256 of each). Source: the raw folder above. License:
  described as public domain, unverified; Nasdaq Data Link's terms apply; Ghost's check open (2026-10-25). Made by: `scripts/fetch/wiki.py` in Neon Rain, which refuses the
  raw parts unless they hash to the row above. Hash: manifest row `wiki-prices`, sha256
  `867d708b43bd772a8f820211885d9e6603b3aaaa602188ce115b950128370a65` (of `index.tsv`, which in turn
  carries each year's hash).

## Rules

1. **Files are never edited in place.** A change is a new file, or a dataset rebuilt by its script; the
   bytes here change only that way, and Neon Rain's manifest row takes the new hash in the same step,
   naming the decision that moved it (R-026 rebuilt one year this way). Every run checks the hash.
2. **Every file is under 100 MB** (R-016 (a)); chunk larger data by year or by ticker range.
3. **No code lives here.** No scripts, workflows, hooks or config. Scripts that read or write this
   data are in Neon Rain (`scripts/fetch/`).
4. **Licenses are checked by Ghost before data enters** (R-016 (d)): the license must permit research, a
   portfolio, and Ghost trading his own money; the manifest row says so.
5. The reviewer pushes; an agent commits (as Ghost) and does not push.

**License status (R-016 (d)):** not yet checked. The data entered before Ghost read WIKI's terms; the
primary text (the WIKI page and Nasdaq Data Link's Terms of Use) could not be read from a session
(2026-10-25). The data stays here, private; no result built on it is reported until Ghost has read the
terms (Neon Rain's HANDOFF).

## What WIKI lacks

Read before using `wiki/prices/` (details and counts in Neon Rain's `docs/FINDINGS.md`):

- It holds no ticker that left before 2014-04-01 (NR-F-03), so 1998 to 2013 is survivor-only; the feed
  also adds almost no new names from 2014 (NR-F-04). Results are reported for the two periods apart (R-026).
- It marks no delisting, and a last row does not say why a name left (NR-F-06). Ticker reuse and
  unrecorded splits cannot be told apart by price alone (NR-F-05).
- The feed decays at its end: corporate actions stop in late 2017 and 2017-11-08 has no rows, hence the
  sample's end (NR-F-07); 120 WIKI dates are not sessions of the calendar (NR-F-08).
