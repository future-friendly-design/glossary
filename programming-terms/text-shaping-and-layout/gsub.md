---
term: GSUB
slug: gsub
aliases:
  - Glyph Substitution table
level: advanced
depth: core
summary: >-
  GSUB is the part of a font file that lists which shapes to swap for other
  shapes, and when.
related:
  - gpos
  - opentype
  - opentype-features
  - ligature
  - text-shaping
status: voice-passed
version_added: 0.1
updated: 2026-10-13T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: 'GSUB: Glyph Substitution Table (Microsoft)'
    url: https://learn.microsoft.com/en-us/typography/opentype/spec/gsub
    type: code
  - title: Why do I need a shaping engine? (HarfBuzz)
    url: https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html
    type: authority
license: CC-BY-4.0
tags:
  - shaping-layout
---

# GSUB

## Definition

GSUB is the part of a font file that lists which shapes to swap for other shapes, and when.<sup>1</sup>

GSUB is one of the tools of [text shaping](text-shaping.md). Text shaping is the step in which software picks the right shapes from a font for a piece of text and decides where each one goes. A [shaping engine](shaping-engine.md), the software that does it, reads GSUB from the font.<sup>2</sup>

The name is short for Glyph Substitution. A [glyph](../text-for-digital-products-and-the-web/glyph.md) is one of the shapes stored in a [font](../text-for-digital-products-and-the-web/font.md), and substitution means swapping one thing for another. GSUB belongs to [OpenType](../../design-terms/typography/opentype.md), the most widely used font format.<sup>3</sup>

### Why it matters in design systems

When you type a word, the glyphs on screen are not always the ones you would get by showing each character on its own. Two characters can appear as one combined glyph, and a symbol can look different because of the symbol beside it.

| What is typed                                                                     | What appears                         | Why                                                                                                 |
| --------------------------------------------------------------------------------- | ------------------------------------ | --------------------------------------------------------------------------------------------------- |
| `f` then `i`                                                                      | One merged "fi" glyph, in many fonts | The pair looks tidier as one glyph. This swap is optional.<sup>4</sup>                              |
| The Arabic letters lam (ل) then alef (ا)                                          | لا                                   | Arabic writes this pair as one shape. This swap is required.<sup>5</sup>                            |
| The Arabic letters kāf ك, tāʾ ت and bāʾ ب                                         | كتب                                  | An Arabic letter has several forms, and the right one depends on its place in the word.<sup>6</sup> |
| The Devanagari consonant क, the mark that removes its vowel, then the consonant ष | क्ष                                  | Devanagari writes these two consonants as one merged shape, called a conjunct.<sup>7</sup>          |

In each row, the software starts with one glyph for each character, then swaps some of those glyphs for others. The list of swaps has to be kept somewhere, and it is kept in the font, because every font has its own set of glyphs. GSUB is that list.

The font does not do the swapping. A font is a file, and a file does nothing by itself. The software that displays text, called a shaping engine, reads the list and follows it.<sup>8</sup>

A swap can be small or large. The simplest kind replaces one glyph with one other glyph.<sup>9</sup> Another kind replaces several glyphs with a single glyph, and a glyph made that way is called a [ligature](ligature.md).<sup>10</sup> The "fi" glyph and the Arabic لا in the table are both ligatures.

Some swaps are required and some are optional. The font sorts its swaps into named groups, called [OpenType features](../../design-terms/typography/opentype-features.md). The group for required ligatures is applied without asking you, and tools are advised not to offer a switch for it.<sup>11</sup> The group for standard ligatures, which holds "fi", is switched on to begin with and can be switched off.<sup>12</sup>

GSUB only swaps glyphs. Two jobs that sit close to it belong somewhere else:

* **Moving a glyph**, such as setting a mark above a symbol, is the job of a second list in the font, called [GPOS](gpos.md).<sup>13</sup>
* **Changing the order of glyphs**, as Devanagari does when a vowel mark appears before the consonant it follows, is done by the shaping engine and is not stored in the font.<sup>14</sup>

Swapping also leaves the stored text alone. The text is still saved as the same characters, and only the glyphs shown for them change.<sup>15</sup>

All of this matters when you choose a font, because every swap has to come from the font itself.<sup>16</sup> A font can have a glyph for every character of a script and still lack the swaps that script needs. When that happens the characters do appear, but with the wrong glyphs, and Arabic letters stand apart instead of joining. So do not judge a font's [coverage](../text-for-digital-products-and-the-web/font-coverage.md) of a script by whether the characters show up. Type a real word, and check that it looks right to someone who reads the script.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Character](../text-in-software/character.md) · [Complex text layout](complex-text-layout.md) · [Conjunct](../../language-terms/writing-systems-and-scripts/conjunct.md) · [Devanagari script](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Font](../text-for-digital-products-and-the-web/font.md) · [Font coverage](../text-for-digital-products-and-the-web/font-coverage.md) · [Glyph](../text-for-digital-products-and-the-web/glyph.md) · [GPOS](gpos.md) · [Joining](../../language-terms/writing-systems-and-scripts/joining.md) · [Ligature](ligature.md) · [Mark](../../language-terms/writing-systems-and-scripts/mark.md) · [Matra](../../language-terms/writing-systems-and-scripts/matra.md) · [OpenType](../../design-terms/typography/opentype.md) · [OpenType features](../../design-terms/typography/opentype-features.md) · [Reordering](reordering.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Shaping engine](shaping-engine.md) · [Symbol](../../language-terms/writing-systems-and-scripts/symbol.md) · [Text shaping](text-shaping.md) · [Virama](../../language-terms/writing-systems-and-scripts/virama.md) · [Text shaping & layout terms](./)

### Further reading

* Code & specs: [GSUB: Glyph Substitution Table (Microsoft)](https://learn.microsoft.com/en-us/typography/opentype/spec/gsub)
* Foundations: [Why do I need a shaping engine? (HarfBuzz)](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)

### Sources

1. "The Glyph Substitution (GSUB) table provides data for substitution of glyphs for appropriate rendering of scripts, such as cursively-connecting forms in Arabic script, or for advanced typographic effects, such as ligatures" - GSUB: Glyph Substitution Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gsub](https://learn.microsoft.com/en-us/typography/opentype/spec/gsub)
2. "Apply OpenType GSUB font features to get the correct glyph shape" - Developing OpenType Fonts for Devanagari Script (Microsoft), Shaping Engine [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
3. "There are several font formats that a program might encounter, each of which has a set of standard text-shaping rules. The dominant format is OpenType" - What is HarfBuzz?, HarfBuzz Manual [https://harfbuzz.github.io/what-is-harfbuzz.html](https://harfbuzz.github.io/what-is-harfbuzz.html)
4. "In other language systems, glyph substitutes are aesthetic options for the user, such as the use of ligature glyphs in the English language" - GSUB: Glyph Substitution Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gsub](https://learn.microsoft.com/en-us/typography/opentype/spec/gsub)
5. "The Arabic character lam followed by alef will always form a ligated lam-alef form. This ligated form is a requirement of the script’s shaping" - Registered features, p-t: 'rlig', OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/features\_pt](https://learn.microsoft.com/en-us/typography/opentype/spec/features_pt)
6. "in the Arabic script, the glyph shape that depicts a particular character varies according to its position in a word or text string" - GSUB: Glyph Substitution Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gsub](https://learn.microsoft.com/en-us/typography/opentype/spec/gsub)
7. "Using the 'akhn' feature, Ka + halant + Ssa is substituted with the KaSsa ligature" - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
8. "The GSUB table provides a way to describe such substitutions, enabling applications to apply such substitutions during text layout and rendering to achieve desired results" - GSUB: Glyph Substitution Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gsub](https://learn.microsoft.com/en-us/typography/opentype/spec/gsub)
9. Lookup type 1, Single: "Replace one glyph with one glyph" - GSUB: Glyph Substitution Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gsub](https://learn.microsoft.com/en-us/typography/opentype/spec/gsub)
10. Lookup type 4, Ligature: "Replace multiple glyphs with one glyph" - GSUB: Glyph Substitution Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gsub](https://learn.microsoft.com/en-us/typography/opentype/spec/gsub)
11. "UI suggestion: Control of this feature should not generally be exposed to the user" - Registered features, p-t: 'rlig', OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/features\_pt](https://learn.microsoft.com/en-us/typography/opentype/spec/features_pt)
12. "This feature serves a critical function in some contexts and should be active by default" - Registered features, k-o: 'liga', OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/features\_ko](https://learn.microsoft.com/en-us/typography/opentype/spec/features_ko)
13. GPOS "Contains information about X and Y positioning of glyphs to handle single glyph adjustment, adjustment of paired glyphs, cursive attachment, mark attachment, and contextual glyph positioning" - Advanced typographic tables: OpenType Layout, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/ttochap1](https://learn.microsoft.com/en-us/typography/opentype/spec/ttochap1)
14. "OpenType fonts should not have substitutions that attempt to perform the re-ordering" - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
15. "The backing string of Unicode characters is not changed; only the visual presentation is changed" - Windows glyph processing for OpenType fonts, part 1 (Microsoft) [https://learn.microsoft.com/en-us/typography/develop/processing-part1](https://learn.microsoft.com/en-us/typography/develop/processing-part1)
16. "All the information controlling the substitution and relative positioning of glyphs during glyph processing is contained within the font itself" - Windows glyph processing for OpenType fonts, part 1 (Microsoft) [https://learn.microsoft.com/en-us/typography/develop/processing-part1](https://learn.microsoft.com/en-us/typography/develop/processing-part1)
