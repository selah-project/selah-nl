# Vertaalnotities — Translation Notes

*Dit bestand toont elk vers waar een mensenhand of een beslissing de weergave
raakte. De overige notities zijn in het Engels — zij gaan over de Hebreeuwse
structuur en de verwijzingen.*

This file records every verse where a human hand or a ruling touched the Dutch
rendering — so any verse can be audited: machine-pressed under the rails,
hand-rendered, or ruled, and why. Rails: the Selah Dutch discipline (Jahweh /
Elohim at the Name seat; ⟨את⟩ total; ⟨…⟩ marks supplied words only; Sjeool
never *hel*; Masjiach never *Christus*; Jehova / HEERE / God-at-the-Name-seat
rejected).

## The burn and the gleaning (2026-08-31)

The altar-fire relay rendered the corpus in one pass and a retry, then moved on
with **77 residue** verses, which were pressed one per call. The census flagged
content faults and every flagged verse was deleted and re-rendered through the
rails, round by round: **248 → 23 → 8 → 0**. The eight that survived three
renders were repaired by hand (below). Final census: Jahweh 5,795 · Elohim
2,180 · ⟨את⟩ in 7,453 verses · every leak class zero.

## Hand-repaired verses (2026-08-31)

Scripts in the Selah repo hold every pair: `dev/scripts/nl_hand_fixes.clj`,
`nl_at_hand_fixes.clj`.

- **Raw Hebrew left inside a fill-bracket** — *Zech 10:2* ⟨און⟩ ⟨הבל⟩ dropped;
  *Exod 29:40* ⟨עשרון⟩ dropped; *Isa 40:17* ⟨אין⟩ dropped and ⟨מ⟩אפס → **als
  minder dan niets**; *Amos 5:5* ⟨און⟩〈nietigheid〉 → **tot nietigheid**;
  *1 Kgs 18:10* ⟨אדני⟩ dropped (the gloss *mijn heer* already carried it).
- **HTML leaked whole** — *1 Chr 26:32* a `<span class="gloss">` around
  *krijgsdeugd*; stripped.
- **Mixed bracket** — *2 Chr 35:9* pesach-<offeranden⟩ → **pesach-offeranden**.
- **Garbled fill** — *Exod 35:22* ⟨א ontbreekt niet: geen⟩ dropped.
- **Translator-note parentheticals in glosses** (rails: none) — *Exod 29:40*
  "(eifatijd)", "(puur)" removed.
- **Hebrew in the text after round three** — *2 Sam 22:36* ענוה →
  **zachtmoedigheid**; *Num 33:55* 〈gezicht〉 → ⟨aangezicht⟩; *Mic 5:11* an
  ascii `<zeg ik: zijn>` aside and its echo removed.

## Per-token review — the God/Heer floors (2026-08-31)

- **God**: 43 verses carried the word. Read per token against the Hebrew seat
  (`dev/scripts/nl_tekoa_fixes.clj`): **5** with capital *God* on an
  אלהים-family surface and no idol word → **Elohim** (2 Sam 10:12; Ps 20:6,
  20:8, 40:4, 42:4); **19 lawful** (lowercase *god / goden*, idol seats, the
  gods of the nations — kept); **9 garble** re-rendered through the rails.
  Floor after the round: 19 lawful.
- **Heer**: 215 verses. Token-level against the surfaces: **יהוה → Heer: 0;
  אֲדֹנָי (Adonay) → Heer: 0.** All 229 *heer / mijn heer* glosses sit on
  אֲדֹנִי, the human "my lord" — lawful. (Checked token-level from the start,
  the lesson of the Malagasy chair's dead regex.)

## The aleph-tav audit (2026-08-31)

Against the graph's H853/H854 token indices: 101 verses examined; the repairer
stripped 35 stray markers and patched 17 sentences; **66 misaligned** (token
count differed from the Hebrew) were re-rendered; **6 unresolved** were read
one by one:

- *Song 6:4* — יפה **את** רעיתי: את the PRONOUN (H859), *you* — un-marked →
  **jij**. The bride's את-you, again the chair's straggler.
- *Jer 8:16* — בה *in it* glossed as the marker → **erin**.
- *Dan 3:12* — Aramaic יתהון *them* → **hen**.
- *1 Kgs 16:3* — אחרי *after* glossed as the marker (twice) → **achter**; מבעיר
  → **brand ik weg**. **A slip of the hand is exposed here**: the first repair
  swept every ⟨את⟩ gloss in the verse to *achter* and thereby overwrote the
  verse's one TRUE marker (ונתתי **את** ביתך); the audit caught it and the
  marker was restored. Blanket replacements are not allowed near true
  markers; the script now carries the indexed form.
- *2 Sam 2:8*, *2 Chr 13:5* — token counts equal but token content not the
  graph's; re-rendered individually.
- *Ps 78:20* — the render had inserted a **phantom את** (the verse has none;
  16 tokens vs 15): tokens written by hand against the Hebrew.
- *1 Kgs 22:47* — the render carried the **next verse's tokens** (ולא היה מלך
  באדום…) under a translation about the Qedeshim — a versification slip;
  tokens written by hand against the graph's ten surfaces.

Final alignment: **0 misaligned, 0 stray, 0 missing.**

## Issues met on the way (exposed on purpose)

- The English ⟨the⟩-class stoplist flagged **1,681** Dutch verses on the first
  census — because *is, was, in, of* are ordinary Dutch words (*of* = "or").
  Stoplist made Dutch-aware; true count 6.
- The 1 Kgs 16:3 blanket-replacement slip, above.
- One re-render produced Cyrillic **and** Chinese in a single word (Gen 26:12,
  "маat收获了") — gleaned in round 1.

## Open flags

- Catalog straggler flags (ui/nl.edn): 24, registered at lighting
  (`docs/language/stragglers/nl.md`), including two register calls for Scott:
  `:word/sig.26` written **JHWH** (zu/mg keep YHWH) and the surfaced-by band
  titled *AANGEDRAGEN DOOR* while the tab keeps HOSTWORDS.
- *God/god* witness column: 19 lawful stand; a native reader's pass is welcome
  on the 5 seat-corrections and on this file's Dutch prose.
