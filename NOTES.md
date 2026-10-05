# en6 — the clean room

*Rendered 2026-10-05, 02:05 → 07:44 (US Eastern), corrections to 16:2x. 23,213 verses of 23,213.*

## What this pass is

The sixth English pass is the first made **from the Hebrew and a lexicon alone**: no translation of any kind and no
earlier pass of ours in the prompt. Every earlier pass (v1–v5) was made with seven English translations of each verse
in its prompt (Wycliffe, Geneva 1599, King James, Young's Literal, the American Standard, JPS 1917, the Berean
Standard) and the King James neighbouring verses; en6 saw none.

For each group of up to four verses the model saw: the Hebrew, pointed and bare; the neighbouring verses **in
Hebrew**; for every word its lemma, Strong's number and Strong's *definition* (never the King James usage list), its
form spelled out (dual, construct, stem, person), the qere where the reading tradition differs, its sense in the
**Semantic Dictionary of Biblical Hebrew** (UBS, v0.9.3 — resolved through each sense's own list of occurrences; the
literal picture where SDBH gives one; the choices side by side where the occurrence is ambiguous; SDBH's ► clauses
that tell what happens later removed), where else a rare word occurs, who a pronoun points to, the familiar English
form of a proper name, the accents' pauses, and parallel passages in Hebrew. The system message is
`prompts/system.md` (sha-256 7880f37a…).

Format: every token carries `gloss`, may carry `readings` (≤ 3, ordered, `readings[0] == gloss`), and names the
dictionary sense it rendered (`sense`: S1, S2 … of the evidence line). Verses rendered after 02:37 carry the model's
`notes` and a `provenance` block (prompt hashes, code version, model, evidence file).

Written alongside the main English rendering (v3, `main`), never over it. Nothing here is seated.

## The run

- Model glm-5.3; runs of up to four verses; book by book; ~85 verses/min.
- First pass 02:05–06:45; the residue pass (06:45–07:44) re-rendered 1,430 verses: 76 whose glosses did not match the
  Hebrew word for word, 964 whose text had dropped an ⟨את⟩ the glosses kept, and those whose answer was unreadable.
  The last 20 (and one with a moved token) at 16:1x–16:2x.
- The model's JSON broke in small regular ways (a doubled brace, an unclosed note, a bracket left open, program code
  written into a value); fifteen kinds were repaired mechanically, never rewritten; irregular answers were rendered
  again.
- 182 Hebrew surfaces restored to the bare-consonantal floor.

## Measured against v3 (exp 1122)

Glosses agree 64 % (with en5 69 %); 1,333 verses identical. YHWH 6,834 (the LORD / God in its place 0); Hebraized
names and transliterated common nouns 0; *soul* 222 → 141, *mercy* 26 → 5; senses named on 221,275 glosses.

## Open

- Supplied words are seldom marked ⟨…⟩ (0.13 per verse; v3 1.07) — inherited from en4's rules; for en7.
- ⟨את⟩ in the text and the glosses disagree in ~686 verses.
- *nefesh* left untranslated 194 times (Gen 2:7 *a living nefesh*).
- Names outside the names table take the model's own spelling (*Shichor*).
- Verses rendered before 02:37 (Genesis–mid-Leviticus, ~2,900) carry no notes or provenance block.
