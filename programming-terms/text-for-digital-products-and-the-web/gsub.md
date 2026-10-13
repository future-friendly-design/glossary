---
term: GSUB
slug: gsub
aliases:
  - Glyph Substitution table
level: advanced
depth: core
summary: GSUB is the part of a font file that lists which shapes to swap for other shapes, and when.
related:
  - gpos
  - opentype
  - opentype-features
  - ligature
  - text-shaping
status: voice-passed
version_added: 0.1
updated: 2026-10-13
contributors:
  - sam-gordashko
further_reading:
  - title: "GSUB: Glyph Substitution Table (Microsoft)"
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

The name is short for Glyph Substitution. A [glyph](glyph.md) is a shape that a [font](font.md) draws for a character, and substitution means swapping one thing for another. GSUB belongs to [OpenType](../../design-terms/typography/opentype.md), the font file format most fonts use today.<sup>2</sup>

### Why it matters in design systems

When you type a word, the shapes on screen are not always the ones you would get by drawing each character on its own. Two characters can be drawn as one joined shape. A letter can be drawn differently because of the letter beside it.

| What is typed | What is drawn | Why |
| ------------- | ------------- | --- |
| `f` then `i` | One joined "fi" shape, in many fonts | The pair looks tidier joined. This swap is optional.<sup>3</sup> |
| The Arabic letters lam then alef: ل then ا | لا | Arabic writes this pair as one shape. This swap is required.<sup>4</sup> |
| The Arabic letters kāf, tāʾ, bāʾ: ك ت ب | كتب | An Arabic letter has several forms. The right one depends on its place in the word.<sup>5</sup> |
| The Devanagari letter क, the mark that removes its vowel, then ष | क्ष | Devanagari merges these consonants into one shape, called a conjunct.<sup>6</sup> |

In each row, the software starts with one shape for each character, then swaps some of those shapes for others. The list of swaps has to be kept somewhere. It is kept in the font, because every font has its own set of shapes. GSUB is that list.

The font does not do the swapping. A font is a file, and a file does nothing by itself. The software that draws text, called a [shaping engine](shaping-engine.md), reads the list and follows it.<sup>7</sup>

A swap can be small or large. The simplest kind replaces one shape with one other shape.<sup>8</sup> Another kind replaces several shapes with a single shape.<sup>9</sup> A shape made that way is called a [ligature](ligature.md). The "fi" shape and the Arabic لا in the table are both ligatures.

Some swaps are required and some are optional. The font sorts its swaps into named groups, called [OpenType features](../../design-terms/typography/opentype-features.md). The group for required ligatures is applied without asking you, and tools are advised not to offer a switch for it.<sup>10</sup> The group for standard ligatures, which holds "fi", is switched on to begin with and can be switched off.<sup>11</sup>

GSUB only swaps shapes. Two jobs that sit close to it belong somewhere else:

* **Moving a shape**, such as setting a mark above a letter, is the job of a second list in the font, called [GPOS](gpos.md).<sup>12</sup>
* **Changing the order of shapes**, as Devanagari does when a vowel mark is drawn before the letter it follows, is done by the shaping engine. It is not stored in the font.<sup>13</sup>

Swapping also leaves the stored text alone. The text is still saved as characters, and GSUB only changes which shapes are drawn for them.<sup>14</sup>

What this means for your work: a font can contain every character of a script and still lack the swaps that script needs.<sup>15</sup> When that happens the characters do appear, but in the wrong shapes. Arabic letters stand apart instead of joining. So do not judge a font's [coverage](font-coverage.md) of a script by whether the characters show up. Type a real word, and check that it looks right to someone who reads the script.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Character](../text-in-software/character.md) · [Conjunct](../../language-terms/writing-systems-and-scripts/conjunct.md) · [Devanagari script](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [GPOS](gpos.md) · [Joining](../../language-terms/writing-systems-and-scripts/joining.md) · [Ligature](ligature.md) · [Mark](../../language-terms/writing-systems-and-scripts/mark.md) · [Matra](../../language-terms/writing-systems-and-scripts/matra.md) · [OpenType](../../design-terms/typography/opentype.md) · [OpenType features](../../design-terms/typography/opentype-features.md) · [Reordering](reordering.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Shaping engine](shaping-engine.md) · [Text shaping](text-shaping.md) · [Virama](../../language-terms/writing-systems-and-scripts/virama.md) · [Text shaping & layout](../text-shaping-and-layout/)

### Further reading

* Code & specs: [GSUB: Glyph Substitution Table (Microsoft)](https://learn.microsoft.com/en-us/typography/opentype/spec/gsub)
* Foundations: [Why do I need a shaping engine? (HarfBuzz)](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)

### Sources

1. "The Glyph Substitution (GSUB) table provides data for substitution of glyphs for appropriate rendering of scripts, such as cursively-connecting forms in Arabic script, or for advanced typographic effects, such as ligatures" - GSUB: Glyph Substitution Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gsub](https://learn.microsoft.com/en-us/typography/opentype/spec/gsub)
2. "There are several font formats that a program might encounter, each of which has a set of standard text-shaping rules. The dominant format is OpenType" - What is HarfBuzz?, HarfBuzz Manual [https://harfbuzz.github.io/what-is-harfbuzz.html](https://harfbuzz.github.io/what-is-harfbuzz.html)
3. "In other language systems, glyph substitutes are aesthetic options for the user, such as the use of ligature glyphs in the English language" - GSUB: Glyph Substitution Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gsub](https://learn.microsoft.com/en-us/typography/opentype/spec/gsub)
4. "The Arabic character lam followed by alef will always form a ligated lam-alef form. This ligated form is a requirement of the script’s shaping" - Registered features, p-t: 'rlig', OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/features_pt](https://learn.microsoft.com/en-us/typography/opentype/spec/features_pt)
5. "in the Arabic script, the glyph shape that depicts a particular character varies according to its position in a word or text string" - GSUB: Glyph Substitution Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gsub](https://learn.microsoft.com/en-us/typography/opentype/spec/gsub)
6. "Apply feature 'cjct' to substitute conjunct forms" - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
7. "The GSUB table provides a way to describe such substitutions, enabling applications to apply such substitutions during text layout and rendering to achieve desired results" - GSUB: Glyph Substitution Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gsub](https://learn.microsoft.com/en-us/typography/opentype/spec/gsub)
8. Lookup type 1, Single: "Replace one glyph with one glyph" - GSUB: Glyph Substitution Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gsub](https://learn.microsoft.com/en-us/typography/opentype/spec/gsub)
9. Lookup type 4, Ligature: "Replace multiple glyphs with one glyph" - GSUB: Glyph Substitution Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gsub](https://learn.microsoft.com/en-us/typography/opentype/spec/gsub)
10. "UI suggestion: Control of this feature should not generally be exposed to the user" - Registered features, p-t: 'rlig', OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/features_pt](https://learn.microsoft.com/en-us/typography/opentype/spec/features_pt)
11. "This feature serves a critical function in some contexts and should be active by default" - Registered features, k-o: 'liga', OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/features_ko](https://learn.microsoft.com/en-us/typography/opentype/spec/features_ko)
12. GPOS "Contains information about X and Y positioning of glyphs to handle single glyph adjustment, adjustment of paired glyphs, cursive attachment, mark attachment, and contextual glyph positioning" - Advanced typographic tables: OpenType Layout, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/ttochap1](https://learn.microsoft.com/en-us/typography/opentype/spec/ttochap1)
13. "OpenType fonts should not have substitutions that attempt to perform the re-ordering" - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
14. "text is encoded as sequences of characters, and the 'cmap' table provides a mapping from that character to a single default glyph" - GSUB: Glyph Substitution Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gsub](https://learn.microsoft.com/en-us/typography/opentype/spec/gsub)
15. "These shaping models depend on the font incorporating certain features as lookups in its GSUB and GPOS tables" - What is HarfBuzz?, HarfBuzz Manual [https://harfbuzz.github.io/what-is-harfbuzz.html](https://harfbuzz.github.io/what-is-harfbuzz.html)
