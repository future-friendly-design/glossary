---
term: Arabic script
slug: arabic-script
aliases:
  - arabic
level: intermediate
depth: deep
summary: >-
  The Arabic script is a right-to-left abjad whose letters join cursively and
  change shape depending on their position in a word.
related:
  - abjad
  - hebrew-script
  - harakat
  - bidirectional-text
  - text-direction
  - ligature
  - complex-text-layout
status: voice-passed
version_added: 0.1
updated: 2026-06-22T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Developing OpenType Fonts for Arabic Script (Microsoft)
    url: https://learn.microsoft.com/en-us/typography/script-development/arabic
    type: code
  - title: Arabic script (Wikipedia)
    url: https://en.wikipedia.org/wiki/Arabic_script
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Arabic script

## Definition

The Arabic script is a right-to-left abjad whose letters join cursively and change shape depending on their position in a word.

## Why it matters

The Arabic script is an [abjad](../language-terms/writing-systems-and-scripts/abjad.md), a script that writes consonants and long vowels while short vowels are normally left out, and it runs right to left. If your product has only ever shown Latin text, this is where two of those Latin assumptions break. First, Arabic is cursive: most letters connect to their neighbors, and one letter takes a different shape depending on whether it stands alone or sits at the start, middle, or end of a word. Second, because it runs right to left, the moment a Latin name, number, or symbol shares a line you are also handling [bidirectional text](../language-terms/writing-systems-and-scripts/bidirectional-text.md). So supporting Arabic is a question about shaping and layout, not just whether your font has the letters. It is also one of the most widely used scripts in the world, which makes it a high-value coverage target.

## Example

Take a single Arabic letter and watch it change by position. On its own it has an isolated form; at the start of a word an initial form; in the middle a medial form; at the end a final form. It is the same stored character every time, and the shaper picks the right one automatically from the letters around it.

## Common mistake

Treating Arabic like a Latin string with the direction flipped. Applying uniform [letter spacing](letter-spacing.md) pulls joined letters apart and breaks the cursive connection; faking a bold weight distorts the stroke shapes; and assuming the text is right to left "everywhere" scrambles embedded Latin words, numbers, and punctuation when the [bidirectional text](../language-terms/writing-systems-and-scripts/bidirectional-text.md) handling is not set up. A font can contain every Arabic code point and still render words wrongly if its shaping rules are missing.

## In practice

* **Verify shaping, not just glyph coverage:** the [joining](../language-terms/writing-systems-and-scripts/joining.md) behavior and contextual forms live in the font's OpenType shaping rules, so test real words and not just a character grid. See Microsoft's [guidance on developing OpenType fonts for Arabic script](https://learn.microsoft.com/en-us/typography/script-development/arabic) for what the shaper has to do.
* **Plan for bidirectional layout from the start:** mirror your interface for right-to-left, and isolate embedded Latin or numeric runs so they do not reorder incorrectly. This connects to [text direction](../language-terms/writing-systems-and-scripts/text-direction.md) and [bidirectional text](../language-terms/writing-systems-and-scripts/bidirectional-text.md).
* **Short vowels are optional marks:** when vowel marks ([harakat](../language-terms/writing-systems-and-scripts/harakat.md)) are shown, they are combining marks layered on the consonants, which affects search, matching, and input. Whether and where they appear is language and context specific, so treat it as expert-verified.

## Related terms

[Abjad](../language-terms/writing-systems-and-scripts/abjad.md) · [Hebrew script](hebrew-script.md) · [Harakat](../language-terms/writing-systems-and-scripts/harakat.md) · [Bidirectional text](../language-terms/writing-systems-and-scripts/bidirectional-text.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Ligature](ligature.md) · [Complex text layout](complex-text-layout.md)

## Further reading

* Foundations: [Arabic script (Wikipedia)](https://en.wikipedia.org/wiki/Arabic_script)
