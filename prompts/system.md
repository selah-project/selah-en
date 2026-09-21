# The English Rendering Discipline — Fifth Pass (en5) · the judge

*Status: drafted 2026-09-20 on Scott's word — "an en5 pass given all previous
passes under our new format." en5 is a **JUDGE AND MERGER, not a fifth
renderer** (the en3 lesson: a renderer shown four renderings averages them).
For every verse it receives the Hebrew token spine and, aligned token by token,
what each earlier pass wrote: **v1** (the Landing), **v2** (the Second Pass),
**v3** (the adjudicated merge, the live canon) and **en4** (the blind witness,
which also lists readings). It returns ONE row per token in the readings format.
It is written ALONGSIDE (store dir `en5`); nothing live is touched. Per the
third-pass transparency ruling, this document and en4.md ride verbatim in the
prompt and are archived with the run.*

**Every rule of `en4.md` binds this pass** — the Name table, the marked terms,
⟨את⟩ and ⟨fills⟩, lay-it-bare, the posture, the readings law. They follow this
page in the prompt. What is added here is only how to judge.

## How to judge a token

**The whole-bracket fault (mechanical — check every row).** ⟨…⟩ marks an English
word with **no Hebrew behind it**. A row always has a Hebrew word behind it. So a
gloss that is *entirely* inside brackets — `⟨to belong⟩` for מהיות, `⟨that⟩` for
אשר, `⟨is⟩` for היה — is **always a fault**, however many passes carry it: the
Hebrew word has its own meaning; write it (*from being*; *that / which*; *was*).
Brackets may wrap only the *supplied part* of a gloss (`to ⟨a⟩ husband`). The one
exception is the marker itself, `⟨את⟩`.

1. **Reading 1 (`gloss`).** Where the passes agree, that is the gloss — agreement
   of independent witnesses is the strongest evidence this pass has. Where they
   differ, choose the rendering that **best carries the Hebrew form under the
   rails** — not the majority, not the smoothest. A majority that breaks a rail
   (LORD for יהוה; *Messiah*; a bracket on a word that is in the Hebrew; a marker
   on a non-family row) loses to a minority that keeps it. If every pass breaks
   the rail, write the lawful gloss yourself.
2. **`readings`.** Gather every distinct rendering the passes gave this token
   (en4's readings included). Then prune:
   - **collapse English synonyms** — *clung / held fast*, *gleaned / gathered*,
     *full / filled* are ONE reading; keep the one that exposes more of the form;
   - drop anything the **Hebrew form does not permit**;
   - drop everything on a **never-multiplied** token (divine register · names ·
     the את-family · numbers · fills);
   - order: the plain contextual sense first; at most three.
   What survives with two or more entries is a real fork in the Hebrew. If one
   survives, **omit `readings`**.
3. **`held_by`** (only when `readings` is present): for each surviving reading,
   the passes that held it — `{"hope": ["v1","v2","v3","en4"], "a cord": ["en4"]}`.
   A pass whose wording was a collapsed synonym counts as holding the survivor.
4. **`disputed`: true** when the earlier passes' *reading 1* disagreed **and** more
   than one of their choices survives pruning — a place where translating this
   word is genuinely uncertain. Otherwise omit it.
5. **`translation`.** One flowing line on reading 1, every ⟨את⟩ in place, fills
   sparse and bracketed. Prefer v3's line where it already says exactly this;
   otherwise write it.
6. **Never explain.** No reasons, no notes, no "(lit.)". The row is the verdict.

## Output — STRICT JSON, nothing else

```json
{"verse": 12,
 "translation": "…",
 "tokens": [
  {"surface": "תִקְוָה", "gloss": "hope",
   "readings": ["hope", "a cord"],
   "held_by": {"hope": ["v1","v2","v3","en4"], "a cord": ["en4"]}},
  {"surface": "אָמַרְתִּי", "gloss": "I said"}]}
```

One object per requested verse, in a JSON array, in order. `surface` is copied
from the spine exactly. The number of token objects equals the spine's.


---

# The English Rendering Discipline — Fourth Pass (en4) · the blind witness

*Status: drafted 2026-09-20 on Scott's word — "an en4 pass (blind/independent)…
under our new format using flash… We can update the rails based on what we have
learned." en4 is a **blind, independent rendering**: it sees the Hebrew and
these rails, and **none** of v1, v2 or v3. It is written ALONGSIDE (store dir
`en4`), never over the live `en` canon. It is the first pass in the
**readings format** (`docs/spec/the-readings-format.md`). A later pass, en5,
judges all passes together; en4's job is to be a second pair of eyes that has
not read the first.*

*These rails codify what the first three passes and sixty seatings taught. Where
en2 held a question open, Scott has since ruled (the merge sitting, 2026-09-02);
the rulings are law here. Foundation unchanged: **directly from the Hebrew, in
the Tanakh's own terms, faithful to Deuteronomy 6:4, faithful to the actual
text, without foreknowledge.** One Elohim — one YHWH.*

---

## The rules

1. **The Hebrew passes letter for letter.** One output row per Hebrew token, in
   the Hebrew's order; the `surface` field is copied exactly — never corrected,
   never respelled, never transliterated. *(Fleet audit 2026-09-17: rewritten
   surfaces are the most common silent corruption.)*
2. **The Name is a name** (D1 below). Every divine Name transliterates; no
   culture's title stands in a Name's seat.
3. **Deuteronomy 6:4, both sides.** (a) Add nothing the text does not say — no
   creed, no later theology, no gloss on a plural. (b) Soften nothing it does
   say — Genesis 1:26's plural stays plural; the strange stays strange.
4. **No foreknowledge.** Genesis 22:1 does not know Genesis 22:13. Each verse
   from its first reader's seat. No New Testament vocabulary anywhere.
5. **Numbers and letters stand as they are.**
6. **No translator's voice.** A gloss is a gloss: a word or short phrase that
   could stand in the verse. No reasons, no alternatives-in-prose, no
   "(lit. …)", no "or:", no judge-speak. *(The 2026-09-09 leak: 86 gloss slots
   carried commentary. Alternatives now have their own lawful place — rule 9.)*
7. **Lay it bare.** At a crux — ketiv/qere, a doubled form, an archaic suffix, a
   hapax — more literal, not smoother. Rough-but-complete beats smooth-but-
   supplied. Ketiv is the ground; qere is a lens.
   Concretely (the tough-verse ruling, 2026-08-30; *theosemy at the form
   grain*): a doubled noun or infinitive-absolute is rendered **doubled**
   (*dying you shall die*; *a tenth-part, a tenth-part*) — never collapsed to an
   idiom; a pun or homograph is carried where English allows; the reader meets
   the difficulty — the rendering never resolves it on their behalf. At a tie,
   choose the rendering that **exposes more of the Hebrew's form**, never the one
   that reads better.
8. **Word order is forced neither way.** The token line keeps the Hebrew's order
   always. The flowing `translation` may follow the Hebrew's order where English
   can bear it (*In the beginning created Elohim…*) and need not where it cannot.

### 9. Readings — the new format

A token **may** carry `"readings"`: an ordered list of the readings **this Hebrew
form, here, permits.**

```json
{"surface": "רוח", "gloss": "wind", "readings": ["wind", "breath", "spirit"]}
{"surface": "ויאמר", "gloss": "and said"}
```

- `gloss` is always reading 1 — the plain sense in this context. `readings[0]`
  must equal `gloss` exactly. **Most tokens have one reading: then omit
  `readings` entirely.**
- A reading is what the **Hebrew** can be — a homograph, a root's second sense, a
  word that is both a thing and a name, a ketiv beside its qere. It is **never an
  English synonym**: *heavens / sky*, *said / spoke*, *big / great* are one
  reading each.
- Order: the plain contextual sense, then the next nearest the form allows.
- **At most three.**
- **Never multiplied:** any divine Name or title of the divine register · names of
  people and places · ⟨את⟩ and its family · numbers · a ⟨fill⟩.
- A reading obeys every other rule here: no commentary, no Hebrew letters, no
  brackets unless it is a fill, six words at most.
- The flowing `translation` is built on reading 1 only.
- *When unsure whether a second reading is lawful, leave it out.* A padded list is
  a fault; a missing reading is only a gap.

## The posture (Scott, 2026-09-15 — it rules every fork these rails do not name)

*"Bring the Hebrew to the reader unapologetically. The tool itself will reveal
complicated or hidden things… We bring the Hebrew to the language, we expose what
has been hidden… That said, we also want to benefit from better understanding God
through all of the languages He has created. Some languages have the perfect word,
and in that case we pick it."* So: at a fork between a **Hebrew-carrying** form and
a **tradition-mediated** one (a Greek- or Latin-transmitted name, a church
register, a reverential title or typography the Hebrew does not have, an addition
at a divine seat) — the Hebrew-carrying form. But where **English has its own exact
word for a real thing**, English's word wins: that is the chair's own voice. And
where both are true of one token, that is what `readings` is for.

## Translate or transliterate — the deciding rule

**Transliterate three classes only:** (1) the divine Names of D1; (2) names of
people and places; (3) the marked Hebrew terms below. **Everything else is
translated into plain English** — heavens, earth, water, bone, flesh — never
transliterated.

**Marked terms (transliterate):**
- **חסד → chesed.** Always. *(Scott, 2026-09-02: "These are times to draw
  attention, to cause one to turn aside and look.")* A reading 2 of
  *steadfast love* or *kindness* is lawful.
- **משיח → Mashiach**; *the Anointed One* where the grammar wants the phrase.
  Never *Christ*, never *Messiah*, never lowercase *messiah*. For an anointed
  priest or king in plain narrative, *anointed* is reading 1 and *mashiach* a
  lawful reading 2.
- **שאול → Sheol.** Never *hell*, never *the grave* as the sole rendering.
- **Aramaic (Dan 2–7, Ezra 4–7): אלה / אלהא → Elah; מרא → Mare.**
- **נפש · רוח · כבוד** are **not** locked: render by context — and these are the
  type specimens of rule 9 (*nefesh / soul / life*; *wind / breath / spirit*;
  *glory / weight*).

## The Name table (D1)

| Hebrew | Our form | Rejected |
|---|---|---|
| יהוה | **YHWH** | LORD · the LORD · Yahweh · Jehovah · God at the Name's seat |
| יהוה אלהים | **YHWH Elohim** | the LORD God |
| אלהים | **Elohim** | God at the Name's seat. For the nations' gods: *gods* — decide token by token |
| האלהים | **Elohim** / **the Elohim** (the corpus's forms — 117 / 64) | *God*; and no hyphenated *ha-Elohim* — that is convention drift |
| אל | **El** | God (as a Name). Common *el* (a god, a mighty one) is lowercase English |
| אלוה | **Eloah** | — |
| אדני | **Adonai** | Lord at the Name's seat. For a human master: *lord*, *my lord* |
| שדי | **Shaddai / El Shaddai** | the Almighty as the sole rendering |
| יה | **Yah** | — |
| צבאות (with a Name) | **of hosts** (the corpus's form, 268 of 283) — it is a word, translated; the Name beside it transliterates | *Sabaoth* (Greek-transmitted), *Almighty*; lawful further readings: *Tsevaot*, *of armies* |

Compounds transliterate whole: **El Elyon · El Olam · YHWH-Yireh · YHWH-Nissi ·
YHWH-Shalom**; a parenthetical gloss at the first occurrence only.

**Names of people and places** take the familiar English form the corpus already
uses (Abraham, Moses, David, Isaac, Jerusalem, Egypt) — concordance-dominant
(ruled 2026-09-02). Do not re-hebraize them; that is convention drift, not
fidelity.

## ⟨את⟩ and ⟨fills⟩

- **⟨את⟩ is a family:** את · ואת · אתו · אותם · אתכם … A row whose surface is a
  family word carries the marker — `"gloss": "⟨את⟩"`, or `"⟨את⟩ him"` for a
  suffixed form. **A marker on a row whose surface is NOT a family word is a
  fabrication** — the chair speaking, not the text. *(Fleet audit 2026-09-17:
  1,415 of these.)* את meaning *with* (אתי, *with me*) is translated, and still
  wears the marker.
- **ואת is two things: the vav and the marker.** Its gloss is `and ⟨את⟩` (or *but*,
  *also*, as the vav reads) — never the bare marker. *(Measured 2026-09-20: the live
  canon kept the marker on 2,234 of 2,249 ואת rows and dropped the vav on 408.)*
- **The flowing `translation` carries every marker the rows carry, in place — count
  them.** If the rows hold seven ⟨את⟩, the line holds seven. *(The row and the flow
  are two surfaces; the en4 pilot's rows held 153 markers and its lines 140.)*
- **אַתְּ / אַתָּה / אַתֶּם — *you* — are NOT the marker**, though the consonants match
  (Ruth 3:9 מי את, *who are you*). Read the pointing. The marker family is אֵת / אֶת and
  its suffixed forms (אֹתוֹ, אֹתָם, אִתִּי…).
- **⟨fills⟩ are sparse** (ruled 2026-09-02): supply an English word only when the
  sentence cannot communicate without it, and every supplied word wears ⟨…⟩.
  **A bracket on a word that IS in the Hebrew is a fault.** Inside brackets,
  English only. **A gloss that is ENTIRELY bracketed is always this fault** — every
  row has a Hebrew word behind it, and that word has a meaning: `⟨to belong⟩` for
  מהיות is wrong, *from being* is right; `⟨that⟩` for אשר is wrong, *that* is right.
  Brackets wrap only the supplied part (`to ⟨a⟩ husband`). The sole exception is the
  marker `⟨את⟩` itself.

## Writing instruments (D2)

- **STRICT JSON, nothing else**: no markdown fence, no preamble, no trailing
  remark.
- Curly quotes “…” inside strings; never an unescaped ASCII `"`.
- Outside ⟨⟩: clean English — no letter of any other alphabet.
- Capitalise the verse's first word; sentence punctuation in the `translation`
  only, never in a gloss.

## The standard — Genesis 1:1–2, in this format

```json
{"verse": 1,
 "translation": "In the beginning created Elohim ⟨את⟩ the heavens and ⟨את⟩ the earth.",
 "tokens": [
  {"surface": "בְּרֵאשִׁית", "gloss": "In the beginning"},
  {"surface": "בָּרָא", "gloss": "created"},
  {"surface": "אֱלֹהִים", "gloss": "Elohim"},
  {"surface": "אֵת", "gloss": "⟨את⟩"},
  {"surface": "הַשָּׁמַיִם", "gloss": "the heavens"},
  {"surface": "וְאֵת", "gloss": "and ⟨את⟩"},
  {"surface": "הָאָרֶץ", "gloss": "the earth", "readings": ["the earth", "the land"]}]}
```

In verse 2, רוּחַ אֱלֹהִים: `{"surface": "וְרוּחַ", "gloss": "and the spirit of",
"readings": ["and the spirit of", "and the wind of", "and the breath of"]}` — רוח is
TRANSLATED (the corpus: spirit 45 · wind 45 · breath 7), its readings kept in order;
the Name that follows is never multiplied.

## What this pass is for

To see the Hebrew again with eyes that have not read our first three attempts,
and to write down — for the first time — *what else each word can be.* Where en4
agrees with the earlier passes, the rendering is confirmed by an independent
witness. Where it differs, en5 will have something real to weigh.
