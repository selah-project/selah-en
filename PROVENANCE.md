# PROVENANCE — how this rendering came to be

*English, sixth pass — en6, THE CLEAN ROOM. Rendered 2026-10-05, 02:05 → 07:44 US Eastern, the last corrections
16:1x–16:2x. 23,213 verses of 23,213. Branch `v6` of selah-en, tag `v6-final`. The main English rendering is v3
(`main`); this pass is read beside it, never over it.*

A rendering made by a machine does not stand unless you can see how it was made. This file says how, and what
had to be corrected.

## The method

Every earlier Selah rendering, in every language, was made with seven English translations of each verse and the
King James neighbouring verses in the model's prompt. **This pass saw no translation of any kind, and no earlier
pass of ours.** It was made from the Hebrew and a lexicon alone, to learn what they give on their own.

For each group of up to four verses the model saw:
- the Hebrew, pointed and as bare consonants, and the neighbouring verses **in Hebrew**;
- for every word its dictionary form, its Strong's number and the Strong's **definition** (never the King James
  list of renderings), and its form spelled out (dual, construct, the verb's stem and person);
- the qere where the reading tradition reads otherwise than it is written;
- its sense in the Semantic Dictionary of Biblical Hebrew, with the literal picture where SDBH gives one, or the
  choices side by side where the occurrence is ambiguous. SDBH's notes that tell what happens later in the story
  were removed;
- where else a rare word occurs, and who a pronoun or verb points to;
- for a proper name, the familiar English form;
- the accents' pauses, and parallel passages in Hebrew.

The rules (`prompts/system.md`, sha-256 `7880f37a…`): the Name is YHWH; אלהים is Elohim; names take their
familiar English form; ordinary words are translated, never transliterated; a word's shape is its meaning (a dual
stays two, a construct stays bound); the object marker is ⟨את⟩; supplied words wear ⟨…⟩; each gloss names the
dictionary sense it rendered.

## Sources

| source | role | license |
|---|---|---|
| OpenScriptures Hebrew Bible (WLC 4.20) | the Hebrew text, lemmas, morphology | CC BY 4.0 |
| Strong's Hebrew Dictionary | definitions | public domain |
| Semantic Dictionary of Biblical Hebrew 0.9.3 (UBS) | senses, literal pictures | CC BY-SA 4.0 |
| MACULA Hebrew (Clear Bible) | sense assignment per word, through SDBH's own occurrence lists | CC BY 4.0 |

Model: glm-5.3 (Zhipu). This rendering: CC BY-SA 4.0.

## What held

- Hebrew forms of names or transliterated ordinary words (*Moshe*, *Davar*): **0**.
- The Name: **YHWH** 6,834 times; *the LORD* or *God* in its place: 0.
- Every verse's glosses match the Hebrew word for word.
- 221,275 of 305,226 glosses name the dictionary sense they render.

## What was corrected

- **1,430 verses rendered again**: 76 whose glosses did not match the Hebrew word for word; 964 whose text had
  dropped an ⟨את⟩ that the glosses kept; and those whose answer could not be read the first time.
- **Answers malformed but complete** (a brace doubled, a bracket left open, a piece of program code written into
  the answer) were repaired mechanically, never rewritten. Fifteen kinds were met, and each repair was tested
  against every failed answer kept.
- **182 Hebrew surfaces** restored to the bare-consonantal text.
- Every request and raw answer from 02:37 on is kept; each verse rendered after it carries its prompt hash, code
  version and evidence file.

## What is still open

- **Supplied words are seldom marked:** about 0.13 per verse against about 1 in the main rendering.
- **⟨את⟩** in the text and the glosses disagree in 686 verses.
- Names outside the names table take the model's own spelling.
- **נפש** is left as *nefesh* 194 times.

The full record: *English — the sixth rendering, the clean room* in the Selah documentation; the run's notes are
`NOTES.md`.
