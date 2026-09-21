# en4 — the blind fourth pass (English)

*Rendered 2026-09-20. 23,213 verses, 39 books. Written ALONGSIDE the live `en`
canon — never over it. Not seated, not served.*

- **What it is:** an independent rendering from the Hebrew. The model saw the
  Hebrew tokens and the rails (`prompts/en4.md`) and **none** of v1, v2 or v3.
  Its job is to be a second pair of eyes that has not read the first; a later
  pass (en5) judges all passes together.
- **Format:** the readings format (`docs/spec/the-readings-format.md` in the
  selah repo): every token keeps `gloss` (reading 1) and MAY carry an ordered
  `readings` list (≤ 3) of what the Hebrew form permits — never target-language
  synonyms; never for the divine register, names, the את-family, numbers, fills.
- **Model:** glm-5.3-flash, batch size 4, thinking disabled.
- **The burn's signature:** lit 05:33 local at fan-out 40; ended 07:10 on its own
  with 4,518 api-errors of 6,167 runs (6,130 verses landed). Relit 08:16 at
  fan-out 20 as an engine-side loop of passes, each pass re-running only what
  had not landed. The api-errors were HTTP 429s — flash refuses even 20 in
  flight, so each pass landed about half of what the last was refused:
  2,163 · 1,099 · 585 · 317 · 181 · 99 · 54 · 29 · 13 · 10 → **complete at 13:55,
  ten passes, residue zero.** Sustained rate ≈ 50–65 verses/min.
- **Audit:** see the selah repo, `dev/experiments/860_*` (run after this commit).
- **Known from the pilot (Ruth · Song · Lev 8):** flash drops ≈ 8 % of the flow's
  ⟨את⟩ markers against its own rows; verb errors and register drift are more
  frequent than in the serving model; structure (JSON, token counts, the Name)
  holds.

## Audit (selah repo, dev/experiments/860_the_en4_audit.clj — 2026-09-20)

Parse failures 0 · the Name 6,826 / 6,826 · bare את 7,321 / 7,368 keep the
marker · ואת 2,237 / 2,249 carry marker and vav · fabricated markers 57 ·
**35 verses disagree with the canon's token count** (Gen 19:7, Ps 150:6 among
them — batch bleed; re-render before any use) · **851 verses' flowing lines
carry fewer ⟨את⟩ than their rows** (≈ 8.6 % of markers) · tokens with readings
20,601 of 305,526 (6.7 %); readings[0] ≠ gloss 291 ×; one Name row multiplied
(Ps 91:2) · whole-bracket glosses 6.

## The 35 (09-21) — token alignment closed

The audit found 35 verses whose token count differed from the canon's spine (Gen 19:7
came back with 34 tokens for 5; Ps 139:1–4 shifted by one; several Psalm titles). The
input was not at fault — the batch feeds the canon's own graph tokens; the model had
slipped verse boundaries inside four-verse calls. Cure: each re-rendered ALONE, same
rails, blind as before, on the serving lane. All 35 now align; the token-count diff
against the spine is 0. (These 35 are therefore the serving model's hand, not flash's —
recorded in each file's `tier`.)
