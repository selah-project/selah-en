# PROVENANCE — how this rendering was made

*English. 23,213 verses, 305,508 tokens. Rendered from the Hebrew of the Westminster Leningrad Codex
(OSHB) — the consonants, the points, the cantillation, and the OSHB lemma and morphology for each word.*

This is the record of how the text in this repository was made, and of what had to be repaired in it. A
machine-made rendering has no standing unless you can see how it was made — so this file tells both,
**the faults included.** The verses where a hand or a ruling touched the text are in [NOTES.md](NOTES.md).

---

## The method

Every verse was rendered from its own Hebrew, word by word and then as a flowing sentence, under written
rules (the translation discipline, in the Selah repository). The rules that govern every verse:

1. **The Hebrew comes first.** The English is a window onto it; where the two part, the Hebrew is right.
2. **The Name stays the Name.** יהוה is written **YHWH** in every place — never a title, never a vowelled
   form. Elohim, El, Eloah, Shaddai, Adonai stand as themselves; in the Aramaic of Daniel and Ezra,
   Elah and Mare.
3. **Every את is shown.** The word את — the marker of the definite object (Strong's H853), and the
   preposition 'with' (H854, with its compound מֵאֵת 'from') — is written **⟨את⟩**, exactly once for each
   time it stands in the Hebrew, in the word row and in the flowing verse alike.
4. **Supplied words are bracketed.** Words English needs that the Hebrew does not write stand in
   ⟨angle brackets⟩.
5. **Each verse in its own light.** No later doctrine read back; no verse rendered with knowledge of a
   later one.

Each verse file names the model that wrote it (`"model"`) and when (`"timestamp"`).

## Who wrote the verses

| model | verses | when |
|---|---|---|
| GLM-5.3 (z.ai) | 16,241 | August 2026 — the second pass, through the codified rules |
| GLM-4.5 (z.ai) | 3,470 | May–July 2026 — the first rendering |
| GLM-5.2 (z.ai) | 3,057 | July 2026 — the re-render of flagged verses |
| GLM-5.1 (z.ai) | 283 | May 2026 |
| by hand (Claude, opus-4.8) | 162 | July 2026 — the hard verses, read from the Hebrew |

Ruled by Scott. Rendered and repaired by Claude, the shovel. Assayed by Codex.

## The passes

The rendering was made in passes, each kept as a tag in this repository so any two can be compared:

- **v1** (`v1-final`, 2026-08-27) — the first full rendering, May–August 2026, with its repairs: the Name
  restored where a 'Lord GOD' convention leaked in (92 verses); the divine-name register (Adonai, Elohim,
  El, Eloah, Shaddai) and the Aramaic register (Elah, Mare); 185 hard verses rendered by hand; the
  aleph-tav audits (every את carries its glyph, the from-compound included — 2026-07-24); the four sign
  words (אוֹת 'sign', H226) freed of a glyph that belonged only to the particle.
- **v2** (`v2-final`, 2026-08-30) — the second pass: the whole corpus re-rendered through the codified rules.
- **v3** (`v3-final`, 2026-09-11) — the third pass: v1 and v2 judged verse by verse and composed under six
  rulings (2026-09-02). **v3 is the default English** (Scott, 2026-09-03), and is `main`.
- **v4–v6** — later passes, kept as tags; they do not replace v3.

## Repairs to v3 (main)

- **2026-09-05 → 09-11** — Hebrew surfaces restored where they had drifted from OSHB; instruction text
  that had leaked into two glosses removed (Dan 3:12, 3:29); 932 correction notes unwrapped into their corrections;
  86 'judge-speak' glosses restored.
- **2026-09-06 — flow parity.** 1,163 verses had markers in the word row that the flowing verse lacked;
  they were inserted. **This insertion was done badly in many verses** — markers set inside words
  ('Elo⟨את⟩ him'), before verbs, or with no object after them. That damage was found on 2026-10-06 and
  repaired (below).
- **2026-10-04** — 1 Sam 17:4, 17:23: הַבֵּנַיִם, 'the-man-of-the-between-two' — the dual made audible.
- **2026-10-06 → 10-07 — the marker repair.** Begun from Scott's reading of ראשיהם ('their heads'):
  - **790 rows in 704 verses**: where the object marker carries a pronoun (אֹתוֹ, אֹתָם …), the row says
    the pronoun — '⟨את⟩ him', '⟨את⟩ them' (Ezek 7:18).
  - **28 rows in 26 verses**: brackets glued into words, parted ('⟨the⟩ir' → 'their', Exod 38:17).
  - **124 verses** of the 2026-09-06 damage cured where the fix was certain; then **843 verses** by a
    proven model repair in three runs (GLM, through the tier gate). The model could only move ⟨את⟩; every
    answer was checked before it was kept — the words the same once markers and prepositions are set
    aside; markers in the verse equal to marker rows; none glued to a letter, none before punctuation.
    Run 3's prompts and raw answers are kept in the Selah repository; runs 1 and 2's answer records were
    overwritten by a later run, and their results live only in these commits.
  - **36 verses** read by hand against their Hebrew (Num 20:28 'and Aaron died'; Gen 35:3 'the El who
    answered ⟨את⟩ me'; Jer 41:9 'the pit').
- **THE CORRECTION — 2026-10-07.** During that repair, the preposition את 'with' (H854) was wrongly
  treated as if the glyph belonged only to the object marker: **420 verses** had ⟨את⟩ removed from
  'with'/'from' rows (`e6d1f5c03`), and the model repair, told the same, turned more of them into bare
  prepositions. That broke the rule above — every את is shown. It was caught the same night and
  **restored** (`1cc3f8ab1`): **685 rows in 610 verses** take ⟨את⟩ back, placed after the preposition and
  before its object, as Scott ruled — 'with ⟨את⟩ him', 'from ⟨את⟩ my lord the king', 'away from ⟨את⟩ me'.
  Each verse was proven: the verse with the restored markers taken out is the verse as it was; markers in
  the verse equal marker rows; none glued, stranded, or inside a bracket.

After the restore, across all 23,213 verses: every verse carries as many ⟨את⟩ in its flow as in its rows;
none is glued to a letter; none stands before punctuation. Of the 888 H854 words, 746 carry the glyph;
the rest are listed as open in [NOTES.md](NOTES.md).

## Two lenses kept

In 45 verses the OSHB lemma and the TAHOT tagging disagree on whether an את is the object marker or the
preposition 'with'. Both readings are kept as lenses; the glyph is shown either way.

## License

CC BY-SA 4.0 — The Selah English Rendering.
