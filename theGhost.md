# theGhost.md: the decisions about this data

The record of the licence of every dataset in this repository, and of the decisions Ghost made about
it. Ghost's direction, 2026-10-26: "license data should live with the data, and decisions around the
license data should live with the data's ghost record. that keeps the data and its usage clearly
boxed into one visible area." So a dataset's licence, its check and the use it is accepted for are
written here, beside the bytes, and nowhere else. Neon Rain's `theGhost.md` (R-016 (d)) and
`data/MANIFEST.md` point here.

This file is a second decision log. Claude Fable advised earlier against a second decision log in this
repository (one log, Neon Rain's); Ghost's direction overrides that advice, for the data's licences.

Prefix **D** (D-001): "D" for data. Neon Rain uses R and J, Katana R, Suite Builder G, Employee
Evaluator E, and Ghost-Core C (Ghost-Core `docs/LINEAGE.md`); no project uses D. A citation of this
file from another repository is written `Data D-001`.

Same entry shape as Neon Rain's `theGhost.md`: Decision, Why, Held by, Source, Status, See also,
subject. Statuses: `proposed`, `in force`, `superseded by D-nnn`, `withdrawn`, `refused`. A reversed
decision is marked `superseded by D-nnn` in the same commit that adds its successor. A change to an
entry's Decision, Why or Status is Ghost's alone, or an agent's with his explicit word in the same
session. Ids are never reused.

**A later dataset gets its own entry when it enters** (D-003, D-004 and on): its source, its licence
as read, what was and was not verified, the use it is accepted for, and Ghost's word. No dataset
enters without one (D-001).

No market data is written here: counts, dates and hashes only. Neon Rain references are to its
`docs/journal/` (J-nnn) and `theGhost.md` (R-nnn).

---

### D-001: The licence of a dataset is checked by Ghost before it enters, and recorded here
- **Decision:** (a) The licence of every dataset is checked by Ghost before the dataset enters this
  repository. (b) The licence must permit this project's use: research, a portfolio piece, and Ghost
  trading his own money if he does. A licence that forbids the last is noted, and that use waits on
  it. (c) The dataset's licence as read, what of it could not be verified, the check and Ghost's word
  are recorded in an entry of this file, one per dataset (D-002 is the first), and each folder of the
  README has a one-line licence status that names the entry. Neon Rain's `data/MANIFEST.md` carries a
  short licence value and the entry's id. (d) If the project's use changes, the checks that rest on
  the old use reopen.
- **Why:** On 2026-10-23 a dataset's licence had to permit commercial use (J-036); on 2026-10-24
  Ghost relaxed it, because a solo experiment and a portfolio piece is not a firm gaming a market,
  and the stricter rule ruled out most free datasets for no reason this project has (J-040). The rule
  and the decisions about each licence were then spread over Neon Rain's R-016 (d), its manifest and
  five journal entries. Ghost, 2026-10-26: "license data should live with the data, and decisions
  around the license data should live with the data's ghost record. that keeps the data and its usage
  clearly boxed into one visible area."
- **Held by:** this file; `README.md` (Rules, and each folder's licence line); `CLAUDE.md` (Rules);
  Neon Rain's `test/test_manifest.py` (every manifest row has a licence value).
- **Source:** Neon Rain R-016 (d), 2026-10-24 (J-040), from the commercial-use rule of 2026-10-23
  (J-036, withdrawn); moved here by Ghost, 2026-10-26 (Neon Rain J-059).
- **Status:** in force
- **See also:** D-002; Neon Rain R-011, R-016
- **subject:** license

### D-002: WIKI prices: public domain as described, unverified, accepted for private research
- **Decision:** (a) The licence of Quandl's WIKI prices (`raw/wiki/`, `wiki/prices/`; manifest rows
  `wiki-prices-raw` and `wiki-prices`) is described as public domain. The primary text was not read:
  the WIKI page and the Terms of Use are script shells from this workspace and the archive is
  refused, and the keyed metadata call has no licence field, so "public domain" rests on secondary
  sources (J-048). (b) WIKI entered on 2026-10-24 before Ghost's check (J-042), against D-001 (a):
  the one exception, an oversight in staging it, and it stayed, private. (c) Ghost closed the check on
  2026-10-26 (J-058). The data is accepted for private research and a portfolio piece, with no
  licensing of the project's work and no commercial use. (d) Between 2026-10-25 and 2026-10-26 the
  check was marked open and every WIKI result was held (J-048); the hold ended with (c). (e) If the
  project's use changes (licensing, commercial use), this check reopens.
- **Why:** Ghost cannot afford a source with real delistings (J-041), and WIKI is free. Reading the
  terms was not possible here and, for the use above, not needed. Ghost, 2026-10-26: "The license
  text is the license text and we dont care about it, because we are not going to license the neon
  rain protocol to anyone nor are we going to use it commercially." (J-058).
- **Held by:** `README.md` (the licence lines of `raw/wiki/` and `wiki/prices/`); Neon Rain
  `data/MANIFEST.md` (the two rows' licence cells, which name this entry).
- **Source:** the fetch, Ghost's session, 2026-10-24 (J-042); the unverified marking, Ghost, 2026-10-25:
  "Yes to wiki reccomendations" (J-048); the closing, Ghost, 2026-10-26 (J-058). Moved here by Ghost,
  2026-10-26 (Neon Rain J-059).
- **Status:** in force
- **See also:** D-001; Neon Rain R-016, R-026
- **subject:** license
