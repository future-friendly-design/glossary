---
term: Arabic script
slug: arabic-script
aliases: [arabic]
tags: [writing-systems-scripts]
level: intermediate
depth: deep
summary: "The Arabic script is a right-to-left abjad whose letters join cursively and change shape depending on their position in a word."
related: [abjad, hebrew-script, harakat, bidirectional-text, text-direction, ligature, complex-text-layout]
status: draft
version_added: 0.1
updated: 2026-06-21
contributors: [sam-gordashko]
further_reading:
  - title: "Arabic script (Wikipedia)"
    url: https://en.wikipedia.org/wiki/Arabic_script
    type: authority
license: CC-BY-4.0
---

# Arabic script

## Definition
The Arabic script is a right-to-left abjad whose letters join cursively and change shape depending on their position in a word.

## Why it matters
The Arabic script is an [abjad](abjad.md), a script that writes consonants and long vowels while short vowels are normally left out, and it is written right to left. Two behaviours make it more demanding than a Latin font swap. First, it is cursive: most letters connect to their neighbours, and a single letter can take a different shape depending on whether it stands alone or sits at the start, middle, or end of a word. Second, because it runs right to left, any product that shows Arabic also has to handle [bidirectional text](bidirectional-text.md) once Latin names, numbers, or symbols appear in the same line. Supporting Arabic is therefore a question about shaping and layout, not just whether your font contains the letters. After Latin, it is one of the most widely used scripts in the world, which makes it a high-value coverage target.

## Example
The letter " haa " is drawn one way on its own and differently when it joins letters on each side, so the same character has several contextual forms that the shaper selects automatically.

## Common mistake
Treating Arabic like a Latin string with the direction flipped. Applying uniform [letter spacing](letter-spacing.md) pulls joined letters apart and breaks the cursive connection; faking a bold weight distorts the stroke shapes; and assuming the text is right to left "everywhere" scrambles embedded Latin words, numbers, and punctuation when the [bidirectional text](bidirectional-text.md) handling is not set up. A font can contain every Arabic code point and still render words wrongly if its shaping rules are missing.

## In practice
- **Verify shaping, not just glyph coverage:** the joining behaviour and contextual forms live in the font's OpenType shaping rules, so test real words and not just a character grid. See Microsoft's [guidance on developing OpenType fonts for Arabic script](https://learn.microsoft.com/en-us/typography/script-development/standard) for what the shaper has to do.
- **Plan for bidirectional layout from the start:** mirror your interface for right-to-left, and isolate embedded Latin or numeric runs so they do not reorder incorrectly. This connects to [text direction](text-direction.md) and [bidirectional text](bidirectional-text.md).
- **Short vowels are optional marks:** when vowel marks ([harakat](harakat.md)) are shown, they are combining marks layered on the consonants, which affects search, matching, and input. Whether and where they appear is language and context specific, so treat it as expert-verified.

## Related terms
[Abjad](abjad.md) · [Hebrew script](hebrew-script.md) · [Harakat](harakat.md) · [Bidirectional text](bidirectional-text.md) · [Text direction](text-direction.md) · [Ligature](ligature.md) · [Complex text layout](complex-text-layout.md)

## Further reading
- Foundations: [Arabic script (Wikipedia)](https://en.wikipedia.org/wiki/Arabic_script)

<!-- NEEDS EXPERT REVIEW: source is Wikipedia (interim). Upgrade to an authoritative primary (Unicode Standard Section 9.2 Arabic, ScriptSource: Arab) vetted by the SILCON cohort. Any specific script-to-language mapping (which languages use the Arabic script) and relative-usage ranking ("one of the most widely used after Latin") must be confirmed; no letter counts are asserted here on purpose. -->
