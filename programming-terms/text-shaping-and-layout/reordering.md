---
term: Reordering
slug: reordering
aliases:
  - glyph reordering
  - character reordering
level: advanced
depth: deep
summary: >-
  Reordering is a step in displaying text in which software shows some symbols
  in a different order from the order they are stored in.
related:
  - matra
  - reph
  - stacking-script
  - complex-text-layout
  - bidirectional-text
status: voice-passed
version_added: 0.1
updated: 2026-10-13T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Developing OpenType Fonts for Devanagari Script (Microsoft)
    url: https://learn.microsoft.com/en-us/typography/script-development/devanagari
    type: authority
license: CC-BY-4.0
tags:
  - shaping-layout
---

# Reordering

## Definition

Reordering is a step in displaying text in which software shows some symbols in a different order from the order they are stored in.<sup>1</sup>

Reordering is one part of [text shaping](text-shaping.md). Text shaping is the step in which software picks the right shapes from a font for a piece of text and decides where each one goes. A [shaping engine](shaping-engine.md), the software that does this job, does the reordering by rules it holds for each [script](../../language-terms/writing-systems-and-scripts/script.md).<sup>2</sup> The instructions in the font do not do it.<sup>3</sup>

The stored order is usually the order in which the text is typed and spoken.<sup>4</sup> For example, the [Devanagari](../../language-terms/writing-systems-and-scripts/devanagari.md) syllable कि (ki) is stored as the consonant क followed by a vowel mark, but the vowel mark appears first, on the left.<sup>5</sup>

### Why it matters in design systems

Watch someone type a word in Devanagari, a script used to write Hindi. They press the key for a consonant, and it appears. They press the key for the vowel "i", and the new [symbol](../../language-terms/writing-systems-and-scripts/symbol.md) appears on the left of the consonant, not on the right where the next symbol would normally go.

Nothing has gone wrong. The text is stored in the order it is spoken, consonant first and vowel second.<sup>6</sup> The script's own rule is that this vowel mark is written on the left. So the software that displays the text has to put it there. That move is reordering. The rule belongs to the script, as one of its [script rules](../../language-terms/writing-systems-and-scripts/script-rules.md), and reordering is what software does to follow the rule.

A vowel mark of this kind is called a [matra](../../language-terms/writing-systems-and-scripts/matra.md). A [mark](../../language-terms/writing-systems-and-scripts/mark.md) is a symbol that attaches to another symbol.

Whether a script reorders has to be checked one script at a time. This glossary does not cover every script, so here are four cases to start with. Select a linked term to go to its glossary page.

| Script                                                                    | What is stored                                                        | What appears | Is anything reordered?                                                                                                                                                                                                                                            |
| ------------------------------------------------------------------------- | --------------------------------------------------------------------- | ------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Devanagari                                                                | The consonant क, then the vowel mark for "i"                          | कि           | Yes. The vowel mark appears to the left of the consonant. It is the only vowel mark in modern Devanagari that is written on the left.<sup>7</sup>                                                                                                                 |
| Devanagari                                                                | The consonants क, र and म, with a mark after र that removes its vowel | कर्म         | Yes. The consonant र is stored before म, and it appears as a small hook above म. That hook is called a [reph](../../language-terms/writing-systems-and-scripts/reph.md).<sup>8</sup> The software moves it to its place while it shapes the syllable.<sup>9</sup> |
| [Tamil](../../language-terms/writing-systems-and-scripts/tamil-script.md) | The consonant க, then the vowel mark for "e"                          | கெ           | Yes. The vowel mark appears to the left of its consonant.<sup>10</sup>                                                                                                                                                                                            |
| [Thai](../../language-terms/writing-systems-and-scripts/thai-script.md)   | The vowel symbol ไ, then the consonant ก                              | ไก           | No. In Thai, a vowel that is written on the left is also typed and stored first, so the stored order already matches the order on screen.<sup>11</sup>                                                                                                            |

The Thai row is there on purpose. Thai is a relative of the other two scripts, and it handles its left-side vowels in a different way from them.<sup>12</sup> Other relatives differ again: Telugu and Kannada have no vowel mark that is written on the left at all.<sup>13</sup> So a rule you have learned for one script cannot be carried over to the scripts related to it.

In Devanagari and Tamil, reordering is not stored in the font. A [font](../text-for-digital-products-and-the-web/font.md) is a file of shapes, called [glyphs](../text-for-digital-products-and-the-web/glyph.md), together with instructions for swapping those glyphs and placing them. Changing the order is a different kind of work. It is done by the shaping engine, the software that chooses and places a font's glyphs, using rules it holds for each script.<sup>14</sup> A Devanagari font in the [OpenType](../../design-terms/typography/opentype.md) format is expected to leave the order alone: its instructions are written for glyphs that are already in the order they appear in, and instructions for reordering do not belong in it.<sup>15</sup>

This explains a failure that looks like a font problem and is not one. If the vowel mark in कि appears on the right of the consonant, changing the font will not help. The text has passed through a tool that did not shape it.

Needing reordering is also one of the things that gets a script called a complex script.<sup>16</sup> The shaping work in those scripts is called [complex text layout](complex-text-layout.md).

There is a second change of order that is easy to confuse with this one. It is made for [bidirectional text](../../language-terms/writing-systems-and-scripts/bidirectional-text.md), where [right-to-left](../../language-terms/writing-systems-and-scripts/right-to-left.md) writing such as [Arabic](../../language-terms/writing-systems-and-scripts/arabic-script.md) or [Hebrew](../../language-terms/writing-systems-and-scripts/hebrew-script.md) shares a line with [left-to-right](../../language-terms/writing-systems-and-scripts/left-to-right.md) writing, and the right-to-left part has to be laid out starting from its right-hand end.<sup>17</sup> The two are separate, and one can happen without the other.<sup>18</sup> The reordering on this page moves one symbol inside a syllable, and the shaping engine does it. Sorting out mixed directions works on whole stretches of a line, and a shaping engine such as HarfBuzz expects other software to have done it first.<sup>19</sup>

For your work, the point is that the order text is stored in and the order it appears in are two different things in these scripts.

### Common mistake

Retyping text to make it look right. If a mark is on the wrong side, the stored [characters](../text-in-software/character.md) are probably correct and the tool is not shaping them. Putting the characters into the order they appear in breaks the text in every tool that does shape: a vowel mark stored ahead of its consonant attaches to the consonant before it, which is the wrong one. At the start of a word it has no consonant to attach to, and may be shown on a dotted circle.<sup>20</sup> Leave the stored order as it is.

### In practice

* **Do not shorten text by counting stored characters.** Cut the last stored character from कि and the symbol that disappears is the one on the left, not the one at the end. Software has a unit for symbols that belong together, called a [grapheme cluster](../text-in-software/grapheme-cluster.md), and splitting text into those units is called [segmentation](../text-in-software/segmentation.md). Ask for text to be cut and counted that way.
* **Test a word that reorders.** Put a real word with a left-side vowel mark, and one with a reph, into each tool your text passes through, and ask a reader of the script whether every symbol is where it belongs.
* **Check both changes of order.** A product that handles reordering inside a syllable may still get mixed directions wrong, or the other way round, so check the two separately.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Bidirectional text](../../language-terms/writing-systems-and-scripts/bidirectional-text.md) · [Brahmic scripts](../../language-terms/writing-systems-and-scripts/brahmic-scripts.md) · [Character](../text-in-software/character.md) · [Complex text layout](complex-text-layout.md) · [Devanagari script](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Font](../text-for-digital-products-and-the-web/font.md) · [Glyph](../text-for-digital-products-and-the-web/glyph.md) · [Grapheme cluster](../text-in-software/grapheme-cluster.md) · [Hebrew script](../../language-terms/writing-systems-and-scripts/hebrew-script.md) · [Language](../../language-terms/linguistics/language.md) · [Left-to-right](../../language-terms/writing-systems-and-scripts/left-to-right.md) · [Mark](../../language-terms/writing-systems-and-scripts/mark.md) · [Matra](../../language-terms/writing-systems-and-scripts/matra.md) · [OpenType](../../design-terms/typography/opentype.md) · [Reph](../../language-terms/writing-systems-and-scripts/reph.md) · [Right-to-left](../../language-terms/writing-systems-and-scripts/right-to-left.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../../language-terms/writing-systems-and-scripts/script-rules.md) · [Segmentation](../text-in-software/segmentation.md) · [Shaping engine](shaping-engine.md) · [Stacking script](../../language-terms/writing-systems-and-scripts/stacking-script.md) · [Symbol](../../language-terms/writing-systems-and-scripts/symbol.md) · [Tamil script](../../language-terms/writing-systems-and-scripts/tamil-script.md) · [Text shaping](text-shaping.md) · [Thai script](../../language-terms/writing-systems-and-scripts/thai-script.md) · [Virama](../../language-terms/writing-systems-and-scripts/virama.md) · [Text shaping & layout terms](./)

### Further reading

* Foundations: [Developing OpenType Fonts for Devanagari Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/devanagari)

### Sources

1. "A reordering operation moves a glyph from its original ("logical") position in the sequence to some other ("visual") position" - Shaping operations, HarfBuzz Manual [https://harfbuzz.github.io/shaping-operations.html](https://harfbuzz.github.io/shaping-operations.html)
2. "For many of the scripts supported in Unicode, these steps involve script-specific layout rules, including complex joining, reordering, and positioning behavior. Implementing these rules is the job of the shaping engine" - Why do I need a shaping engine?, HarfBuzz Manual [https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)
3. "OpenType fonts should not have substitutions that attempt to perform the re-ordering" - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
4. Logical Order: "The order in which text is stored in the memory representation. For the most part, logical order corresponds to the typing order and the phonetic order" - Unicode Glossary [https://www.unicode.org/glossary/#logical\_order](https://www.unicode.org/glossary/#logical_order)
5. "Because Devanagari and other Indic scripts have some dependent vowels that must be depicted to the left side of their consonant letter, the software that renders the Indic scripts must be able to reorder elements in mapping from the logical (character) store to the presentational (glyph) rendering" - The Unicode Standard, Version 18.0, Chapter 12: South and Central Asia-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/)
6. "The storage of plain text in Devanagari and all other Indic scripts generally follows phonetic order; that is, a CV syllable with a dependent vowel is always encoded as a consonant letter C followed by a vowel sign V in the memory representation" - The Unicode Standard, Version 18.0, Chapter 12: South and Central Asia-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/)
7. "In modern usage the Devanagari script has only one character denoting a left-side dependent vowel sign" - The Unicode Standard, Version 18.0, Chapter 12: South and Central Asia-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/)
8. "Reph - The above-base form of the letter "Ra" that is used in Devanagari when "Ra" is the first consonant in the syllable and is not the base consonant" - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
9. "Reph's original position is always at the beginning of the syllable, (i.e. it is not reordered at the character reordering stage). However, it will be reordered according to the basic-forms shaping results" - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
10. Of three Tamil vowel marks, U+0BC6, U+0BC7 and U+0BC8: they "are reordered in front of the consonant to which they are applied. When occurring in a syllable, these vowels are rendered to the left side of their consonant" - The Unicode Standard, Version 18.0, Chapter 12: South and Central Asia-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/)
11. "In the Thai encoding, the letter-sized glyphs that are placed before (left of) the base consonant letter, in full or partial representation of a vowel sign, are, in fact, encoded as separate characters that are typed and stored before the base consonant character" - The Unicode Standard, Version 18.0, Chapter 16: Southeast Asia-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-16/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-16/)
12. "This encoding for left-side Thai vowel sign glyphs (and similarly in Lao and in Tai Viet) differs from the conventions for all other Indic scripts, which uniformly encode all vowels after the base consonant" - The Unicode Standard, Version 18.0, Chapter 16: Southeast Asia-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-16/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-16/)
13. "Other Indic scripts either have no such vowel signs (Telugu and Kannada) or include as many as three of these signs (Bengali/Bangla, Tamil, and Malayalam)" - The Unicode Standard, Version 18.0, Chapter 12: South and Central Asia-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/)
14. "For many of the scripts supported in Unicode, these steps involve script-specific layout rules, including complex joining, reordering, and positioning behavior. Implementing these rules is the job of the shaping engine" - Why do I need a shaping engine?, HarfBuzz Manual [https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)
15. "The OpenType lookups in an Indic font must be written to match glyph sequences after re-ordering has occurred. OpenType fonts should not have substitutions that attempt to perform the re-ordering" - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
16. "Standard Script - Any non-complex script; any script that does not require re-ordering or contextual analysis in the shaping process" - Developing OpenType Fonts for Standard Scripts (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/standard](https://learn.microsoft.com/en-us/typography/script-development/standard)
17. "Some of the clearest examples are situations where a right-to-left script (such as Arabic or Hebrew) is mixed with a left-to-right script (such as Latin or Greek)" and "The logical start character of the Hebrew text, however, is represented by the Hebrew glyph closest to the right margin" - The Unicode Standard, Version 18.0, Chapter 2: General Structure [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-2/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-2/)
18. "This reordering is not commonly seen in non-Indic scripts and occurs independently of any bidirectional character reordering that might be required" - The Unicode Standard, Version 18.0, Chapter 12: South and Central Asia-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/)
19. "HarfBuzz won't help you with bidirectionality" and "Before sending your string to HarfBuzz, you may need to apply the bidi algorithm to it" - What HarfBuzz doesn't do, HarfBuzz Manual [https://harfbuzz.github.io/what-harfbuzz-doesnt-do.html](https://harfbuzz.github.io/what-harfbuzz-doesnt-do.html)
20. "Combining marks and signs that do not occur in conjunction with a valid base are considered invalid" and "a shaping engine implementation might treat an invalid mark as a separate cluster and display the stand-alone mark positioned on some default base glyph, such as a dotted circle" - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
