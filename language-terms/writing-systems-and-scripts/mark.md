---
term: Mark
slug: mark
aliases: []
level: intermediate
depth: deep
summary: >-
  A mark is a kind of symbol that modifies or accompanies another symbol,
  changing how it is pronounced, what it means, or how it functions.
related:
  - combining-mark
  - spacing-combining-mark
  - enclosing-mark
  - diacritic
  - nukta
  - harakat
  - punctuation-mark
status: voice-passed
version_added: 0.1
updated: 2026-06-22T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: 'Unicode Standard Annex #44: General Category Values'
    url: https://www.unicode.org/reports/tr44/#General_Category_Values
    type: code
  - title: Combining Character (Unicode Glossary)
    url: https://www.unicode.org/glossary/#combining_character
    type: authority
license: CC-BY-4.0
tags:
  - characters-encoding
---

# Mark

## Definition

A mark is a kind of symbol that modifies or accompanies another symbol, changing how it is pronounced, what it means, or how it functions.

Symbols (including marks) are the visual elements that make up a [script](script.md). The [script rules](script-rules.md) define how marks can be attached to symbols, how they stack, or where they can be placed within a word.

When a community sets rules on how a script can be used to write their specific language, it becomes an [orthography](orthography.md). The combination of script and orthography is also known as the [writing system](writing-system.md) of a language.

While this glossary doesn't cover every mark for every script, here's the list of marks you may want to explore:

| Mark term                                           | What it does                        |    Example   | Found in                                                                                                                                |
| --------------------------------------------------- | ----------------------------------- | :----------: | --------------------------------------------------------------------------------------------------------------------------------------- |
| [Diacritic](diacritic.md)                           | changes a letter's sound or meaning |   `e` → `é`  | [Latin script](../../terms/latin-script.md)                                                                                             |
| [Tone mark](tone-mark.md)                           | marks the tone of a syllable        |   `a` → `á`  | Vietnamese, Mandarin pinyin                                                                                                             |
| Vowel mark                                          | adds a vowel to a consonant         |  `क` → `कि`  | [Arabic](../../terms/arabic-script.md) ([harakat](../../terms/harakat.md)), [Devanagari](../../terms/devanagari.md) ([matra](matra.md)) |
| [Nukta](nukta.md)                                   | changes a consonant's value         |  `क` → `क़`  | Devanagari                                                                                                                              |
| [Punctuation mark](../../terms/punctuation-mark.md) | structures text, a separate sense   | stands alone | most scripts                                                                                                                            |

[Unicode](../../terms/unicode.md), the standard that gives every character a unique number, groups marks a different way: not by what they do, but by how they sit on the base. A [combining mark](../../terms/combining-mark.md) can be nonspacing, [spacing combining](../../terms/spacing-combining-mark.md), or [enclosing](../../terms/enclosing-mark.md). An enclosing mark wraps all the way around, the way the keycap emoji `1️⃣` puts a box around the digit `1`.<sup>1</sup>

### Why it matters in design systems

Like the [symbol](symbol.md) it attaches to, a mark is rarely where you make a decision; it matters because each discipline a design system spans handles the same mark differently, and a mark the font can draw is still not a mark the system handles correctly.

To a linguist, a mark changes a symbol's meaning or sound.

To typography, a mark is a [glyph](../../terms/glyph.md) the font must both contain and position on its base, and how many marks stack on a letter is set by the language's [orthography](orthography.md), not the shared script: Vietnamese piles a vowel mark and a tone mark where French uses one,<sup>3</sup> so the same Latin script needs more [line height](../../terms/line-height.md) for Vietnamese than for French.

To a computer, a mark is a combining character: the same accented letter can be stored as a single [code point](../../terms/code-point.md) or as a base letter plus a combining mark, which quietly changes how text is searched, counted, and compared.

So covering the marks in the font is necessary, not sufficient: the [shaping](../../terms/text-shaping.md) that positions them and the encoding that stores them have to line up too.

### Common mistake

This one is about software, not type. A computer can store the same accented letter in more than one way: `é` as a single character, or as the letter `e` plus a separate combining mark. On screen they look identical, but to the computer they are different, so two words a person reads as the same can fail to match: a search misses them, a "remove duplicates" step keeps both, a character count comes out wrong. The fix is [normalization](../../terms/normalization.md): the computer rewrites the text into one standard form before it stores or compares it, so the two spellings become equal. This is a storage decision, separate from whether the font draws the mark correctly.<sup>2</sup>

### In practice

* **Check the font covers the marks, not just the base letters:** a typeface can include every letter a language needs and still be missing the marks or the logic to place them, which leaves accented text rendering broken. Set a string with real marks, not just A to Z, before you commit to a font. See [font coverage](../../terms/font-coverage.md).
* **Budget line height for stacked marks:** languages such as Vietnamese put a vowel mark and a tone mark on one letter, and that stack rises higher than a single accent. Give those scripts room in your line-height tokens so marks are not clipped by the line above.
* **Normalize text before you store or compare it:** have the system rewrite incoming text into one standard form, so two spellings that look the same actually match and counts stay correct.

***

### Related terms and mentions

[Arabic script](../../terms/arabic-script.md) · [Code point](../../terms/code-point.md) · [Combining mark](../../terms/combining-mark.md) · [Devanagari](../../terms/devanagari.md) · [Diacritic](diacritic.md) · [Enclosing mark](../../terms/enclosing-mark.md) · [Font coverage](../../terms/font-coverage.md) · [Glyph](../../terms/glyph.md) · [Harakat](../../terms/harakat.md) · [Latin script](../../terms/latin-script.md) · [Line height](../../terms/line-height.md) · [Matra](matra.md) · [Normalization](../../terms/normalization.md) · [Nukta](nukta.md) · [Orthography](orthography.md) · [Punctuation mark](../../terms/punctuation-mark.md) · [Script rules](script-rules.md) · [Spacing combining mark](../../terms/spacing-combining-mark.md) · [Symbol](symbol.md) · [Text shaping](../../terms/text-shaping.md) · [Tone mark](tone-mark.md) · [Unicode](../../terms/unicode.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [Unicode Standard Annex #44: General Category Values](https://www.unicode.org/reports/tr44/#General_Category_Values)
* Foundations: [Combining Character (Unicode Glossary)](https://www.unicode.org/glossary/#combining_character)

### Sources

1. Unicode's top-level General Category "Mark" (M) splits into nonspacing (Mn), spacing combining (Mc), and enclosing (Me) marks - Unicode Standard Annex #44: General Category Values [https://www.unicode.org/reports/tr44/#General\_Category\_Values](https://www.unicode.org/reports/tr44/#General_Category_Values)
2. Precomposed and decomposed spellings of an accented letter are canonically equivalent and normalization removes the difference for comparison - Unicode Glossary: Canonical Equivalence [https://www.unicode.org/glossary/#canonical\_equivalence](https://www.unicode.org/glossary/#canonical_equivalence)
3. Vietnamese "Ẩ" (U+1EA8) decomposes to \<U+0041, U+0302, U+0309>, stacking two marks on one base, and not all rendering systems handle multiple marks on a single base - The Unicode Standard 17.0, Chapter 7 [https://unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/](https://unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/)
