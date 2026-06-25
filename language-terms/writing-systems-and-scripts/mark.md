---
term: Mark
slug: mark
aliases: []
level: intermediate
depth: deep
summary: >-
  A mark is a symbol that modifies or accompanies another symbol, changing how
  it is pronounced, what it means, or how it functions.
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

A mark is a kind of symbol, that modifies or accompanies another symbol, changing how it is pronounced, what it means, or how it functions.

Symbols (including marks) are the visual elements that makes up a [script](script.md). The [script rules](script-rules.md) define how marks can be attached to symbols, how it stacks, or where it can be placed within a word.&#x20;

When a community sets rules on how a script can be used to write their specific language it becomes an [orthography](orthography.md). The combination of script and orthography is also known as the [writing system](writing-system.md) of a language.

While this glossary doesn't cover every mark for every script, heres the list of marks you may want to explore:

| Mark term                                           | What it does                        | Examples                                                                          |
| --------------------------------------------------- | ----------------------------------- | --------------------------------------------------------------------------------- |
| [Diacritic](../../terms/diacritic.md)               | changes a letter's sound or meaning | é, ñ                                                                              |
| [Tone mark](../../terms/tone-mark.md)               | marks the tone of a syllable        | tonal languages                                                                   |
| Vowel mark                                          | adds a vowel to a consonant         | [harakat](../../terms/harakat.md) (Arabic), [matra](../../terms/matra.md) (Indic) |
| [Nukta](../../terms/nukta.md)                       | changes a consonant's value         | Devanagari                                                                        |
| [Punctuation mark](../../terms/punctuation-mark.md) | structures text, a separate sense   | comma, question mark                                                              |

Unicode gathers the technical senses under a top-level [combining mark](../../terms/combining-mark.md) category, split by how the mark occupies space into nonspacing, [spacing combining](../../terms/spacing-combining-mark.md), and [enclosing](../../terms/enclosing-mark.md) marks.<sup>1</sup>

### Why it matters in design systems

Like the [symbol](symbol.md) it attaches to, a mark is rarely where you make a decision; it matters because each discipline a design system spans handles the same mark differently, and a mark the font can draw is still not a mark the system handles correctly.

To a linguist, a mark modifies meaning or sound: it is a diacritic, a tone mark, or a script-specific mark like the Arabic harakat.&#x20;

To typography, a mark is a [glyph](../../terms/glyph.md) the font must both contain and position on its base, and how many marks stack on a letter is set by the language's [orthography](orthography.md), not the shared script: Vietnamese piles a vowel mark and a tone mark where French uses one,<sup>3</sup> so the same Latin script needs more [line height](../../terms/line-height.md) for Vietnamese than for French.&#x20;

To a computer, a mark is a combining character: the same accented letter can be stored as one precomposed [code point](../../terms/code-point.md) or as a base letter plus a combining mark, which quietly changes how text is searched, counted, and compared.

So covering the marks in the font is necessary, not sufficient: the [shaping](../../terms/text-shaping.md) that positions them and the encoding that stores them have to line up too.

#### Examples

**One mark.** The acute over "é" is a single diacritic mark on a base letter `e`. A computer may store it as one [character](../../terms/character.md) `"é"`, or as the letter `e` plus a separate combining mark. .<sup>2</sup>

**Stacked marks.** Vietnamese stacks two marks on one base letter `Ẩ`. In this example, the typography system may decide to have a larger line height for body fonts when supporting the Vietnamese language compared to English or French, even though all three languages use the same script (Latin).<sup>3</sup>

**Enclosing marks.** An enclosing mark surrounds its base instead of sitting over it.<sup>1</sup> For example, the keycap emoji `1️⃣` is the digit "1" with an enclosing mark drawn around it.

### Common mistake

Comparing two strings that look identical and getting "not equal." The accented "é" a user types might be one code point or a base "e" plus a combining acute; on screen they are indistinguishable, but as stored bytes they differ, so a search, a deduplication check, a uniqueness constraint, or a length count can quietly fail on real input. The fix is [normalization](../../terms/normalization.md): convert text to a single canonical form (NFC is the usual choice) before you store, compare, or count it. This is an encoding decision, separate from whether the font draws the mark correctly.<sup>2</sup>

### In practice

* **Check the font covers the marks, not just the base letters:** a typeface can include every letter a language needs and still be missing the marks or the logic to place them, which leaves accented text rendering broken. Set a string with real marks, not just A to Z, before you commit to a font. See [font coverage](../../terms/font-coverage.md).
* **Budget line height for stacked marks:** languages such as Vietnamese put a vowel mark and a tone mark on one letter, and that stack rises higher than a single accent. Give those scripts room in your line-height tokens so marks are not clipped by the line above.
* **Normalize text before you store or compare it:** pick a canonical form (commonly NFC) and apply it on input, so two visually identical strings match and counts stay correct no matter how the marks were entered.



***

### Related terms and mentions

[Code point](../../terms/code-point.md) · [Combining mark](../../terms/combining-mark.md) · [Diacritic](../../terms/diacritic.md) · [Enclosing mark](../../terms/enclosing-mark.md) · [Font coverage](../../terms/font-coverage.md) · [Glyph](../../terms/glyph.md) · [Harakat](../../terms/harakat.md) · [Line height](../../terms/line-height.md) · [Matra](../../terms/matra.md) · [Normalization](../../terms/normalization.md) · [Nukta](../../terms/nukta.md) · [Orthography](orthography.md) · [Punctuation mark](../../terms/punctuation-mark.md) · [Script rules](script-rules.md) · [Spacing combining mark](../../terms/spacing-combining-mark.md) · [Symbol](symbol.md) · [Text shaping](../../terms/text-shaping.md) · [Tone mark](../../terms/tone-mark.md) · [Writing systems & scripts](./)



### Further reading

* Code & specs: [Unicode Standard Annex #44: General Category Values](https://www.unicode.org/reports/tr44/#General_Category_Values)
* Foundations: [Combining Character (Unicode Glossary)](https://www.unicode.org/glossary/#combining_character)



### Sources

1. Unicode's top-level General Category "Mark" (M) splits into nonspacing (Mn), spacing combining (Mc), and enclosing (Me) marks - Unicode Standard Annex #44: General Category Values [https://www.unicode.org/reports/tr44/#General\_Category\_Values](https://www.unicode.org/reports/tr44/#General_Category_Values)
2. Precomposed and decomposed spellings of an accented letter are canonically equivalent and normalization removes the difference for comparison - Unicode Glossary: Canonical Equivalence [https://www.unicode.org/glossary/#canonical\_equivalence](https://www.unicode.org/glossary/#canonical_equivalence)
3. Vietnamese "Ẩ" (U+1EA8) decomposes to \<U+0041, U+0302, U+0309>, stacking two marks on one base, and not all rendering systems handle multiple marks on a single base - The Unicode Standard 17.0, Chapter 7 [https://unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/](https://unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/)
