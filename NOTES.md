# en5 — the judge

*Landed 2026-09-20 → 09-21. 23,213 verses of 23,213.*

## What this pass is

The fifth English pass is not a rendering from scratch. It is the **judge**: for
every verse it is shown the four earlier passes side by side, token by token on
the Hebrew spine — **v1 · v2 · v3** (the seated canon's history) and **en4** (the
blind witness on a different model, in the readings format) — together with both
disciplines verbatim (`prompts/system.md` = `en5.md` + `en4.md`), and it seats one
line and one gloss per token.

Format: every token carries `gloss`; a token **may** carry `readings` (≤ 3, ordered,
`readings[0] == gloss`), `held_by` (which passes held each reading) and `disputed`
(the passes genuinely disagreed and the judge does not pretend otherwise).
See `docs/spec/the-readings-format.md` in the selah repo.

Written ALONGSIDE the live canon (`en`), never over it. Nothing here is seated.

## The burn (its signature)

- Model: the serving lane (9 permits), `:repair` priority, reasoning low.
- **Corpus run** 09-20 14:30 → 18:31, three verses a call, ≈ 85 verses/min:
  22,346 landed, **872 refused** by the validator (a verse dropped from a batch of
  three, or a token count off the spine).
- A first relight over the 380 affected chapters **starved**: ~9,000 queued runs of
  which 8% were real work; `pmap` is ordered, so one or two calls ran at a time —
  2 verses/min with every lane idle. (Cured in `run-chapters!`: it now queues only
  unjudged verses.)
- **Dense passes** over only what was missing, one verse a call, ≈ 50/min:
  739 → 44 (21:43–21:58) → 8 (22:04) → **0** (three tries each, 23:10).
- A hand call on Prov 17:25 showed aligned inputs and a valid answer: the residue
  was the model's occasional stumble, not bad verses.

## Read by eye

- **Ruth 3:9** — כנף restored to *wing* (the earlier passes had smoothed it to
  *skirt / garment*); flagged `disputed`.
- **Isa 49:2** — ברור: *polished* (all four) · *purified* · *chosen* (en4).
- **Hab 2:11** — *a stone from the wall shall cry out, and a rafter from the timber
  shall answer it*; כפיס: *rafter · fastening · beam*.
- **Ps 27:4** — *One thing I have asked… it I seek*; שבתי and ולבקר both `disputed`
  — honestly: they are cruxes.
- **Lev 8:35** — *you shall keep ⟨את⟩ the charge of YHWH*; משמרת: *the charge of ·
  the watch of · the guard duty of*; תשבו: *sit · abide*.
- **2 Sam 14:9** — *“Upon me, my lord the king, ⟨be⟩ the iniquity, and upon the house
  of my father; and the king and his throne ⟨are⟩ innocent.”*

## Forks left for Scott

- **Exod 3:14 אהיה** — *I will be* (en4 alone) was seated over *I AM* (v1 · v2 · v3),
  and flagged `disputed`. The judge followed the form; three passes followed the
  tradition of the rendering. His call.

## The first audit (09-21) and repair pass 1

0 unparsed · 305,507 tokens · **8,373 disputed** · **29,976 multi-reading** · the Name
glossed YHWH on every row that holds it · 13 markers on non-family rows · 56 verses whose
flow has fewer ⟨את⟩ than its rows · and **361 Hebrew surfaces respelled by the judge**
(the Name written where the text has *Joah*, 2 Chr 29:12). Cure, deterministic
(`dev/scripts/en5_surface_restore.py` in the selah repo): surfaces restored from the
canon's spine, glosses untouched, every change in `repair-log.json`; ten verses where
the judge had MOVED tokens were deleted and re-judged. The restore now reports 0 / 0.
*The Hebrew is never the judge's to write* — the next judge prompt should not ask it to.

Most multi-reading forms: הארץ 610 · על 366 · כי 288 · ארץ 221 · רוח 202 · אשר · בני ·
נפשי · אל · נפש · עולם · חסד 75 · כבוד 66. Most disputed: כי · על · אל · אשר · אם · דברי ·
בני · אף · the נפש family · עולם · הדבר · תמים.

## Repair pass 2 (09-21) — the markers

Five ⟨את⟩ on rows whose surface is no family word — stripped. (ומאת ×7 is family and
lawful; Dan 3:12's Aramaic ית is left for the Aramaic ruling.) 56 verses whose flowing
line carried fewer markers than its rows: re-judged; the validator now REQUIRES
flow ⟨את⟩ ≥ row ⟨את⟩ (*the row and the flow are two surfaces*). **Three hand verses** — the
judge would not carry the markers into the sentence in five rounds; the rows are the
judge's, the flow is the shovel's, each file marked `"hand"`: **Ezra 1:5 · 2 Kgs 18:22 ·
Jer 35:14.** After the pass: 23,213 verses · surfaces 0 drifted · 0 short flows · 1 marker
on a non-family row (the Aramaic one).

## Owed

- The audit (as exp 860 did for en4): parse · the Name's count · fabricated markers ·
  flow-vs-row marker parity · token alignment against the canon · doubled fills.
- Tallies of `disputed` slots and multi-reading tokens **by lemma** — the seed list
  for the cross-language sense work.
