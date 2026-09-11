# Contributing to the Selah English rendering

Thank you for helping this rendering become more accurate, clear, and useful.
You do not need to be a professional scholar to report a problem. Please say
what you know, show your evidence, and distinguish certainty from suggestion.

## Choose an issue or a pull request

- Open an **issue** when a reading needs discussion, when several renderings
  are possible, or when you are unsure how the aligned record should change.
- Open a **pull request** when the error and exact replacement are clear.
- For a visual or application bug rather than a corpus correction, use
  [Selah support](https://selahproject.com/support).
- Never report security problems, account details, private correspondence, or
  personal information in a public issue. Use Selah support privately.

## What to include

Identify:

- the book, chapter, verse, and affected Hebrew token;
- the current English wording;
- the proposed wording;
- why it should change; and
- the lexical, grammatical, contextual, or published source supporting it.

Native-speaker judgment is evidence too. Tell us whether English is your first
language and whether you are also reading the Hebrew directly.

## Editing a verse record

Verse files live at `<book>/<chapter>/<verse>.json`. Keep each correction
narrow and preserve the record's structure.

- Edit `translation` and the applicable token `gloss` together when both are
  affected.
- Preserve `book`, `chapter`, `verse`, `ref`, Hebrew `surface` values, token
  order, and token count unless the issue is specifically an alignment defect.
- Do not rewrite model, tier, timestamp, or other provenance fields merely to
  make a correction look newly generated.
- Keep angle-bracket conventions, divine-name conventions, and the visible
  `⟨את⟩` discipline described in the README.
- Avoid formatting-only changes and unrelated corrections in the same pull
  request.

Validate edited JSON before submitting:

```bash
python3 -m json.tool genesis/1/1.json >/dev/null
```

## Translation discipline

The Hebrew comes first. A correction should make the target-language window
clearer without silently removing information carried by the Hebrew. When two
readings are defensible, explain the tradeoff instead of presenting preference
as certainty.

Do not copy a modern copyrighted translation as the replacement text. Brief
quotation for evidence may be appropriate; the submitted wording must be yours
to contribute.

## AI-assisted work

Disclose material use of a language model or automated translation tool. Name
the tool and describe the human review performed. Do not submit an unreviewed
bulk-generated rewrite. The contributor remains responsible for every proposed
word.

## License and attribution

By submitting a contribution, you represent that you have the right to submit
it and agree that accepted material will be distributed under this repository's
[CC BY-SA 4.0 license](LICENSE.md). Git history preserves the public record of
accepted contributions.

## Review

Maintainers review corrections against the Hebrew, repository conventions,
sources, and effects on token alignment. Corrections are not decided by vote or
force of rhetoric. A proposal may be accepted, revised through discussion,
left open for more evidence, or declined with an explanation.

Please be patient and kind. Critique the reading, not the reader.

## Conduct

Be honest, be kind, show your evidence. Distinguish certainty from
suggestion. The maintainers weigh and decide.
