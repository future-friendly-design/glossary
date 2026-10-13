---
term: Complex text layout
slug: complex-text-layout
aliases:
  - CTL
  - complex script
  - complex script rendering
level: advanced
depth: deep
summary: Complex text layout is the extra work software does to display writing in which the shape or position of a character depends on the characters around it.
related:
  - text-shaping
  - reordering
  - stacking-script
  - bidirectional-text
  - matra
status: voice-passed
version_added: 0.1
updated: 2026-10-13
contributors:
  - sam-gordashko
further_reading:
  - title: Shaping concepts (HarfBuzz)
    url: https://harfbuzz.github.io/shaping-concepts.html
    type: authority
license: CC-BY-4.0
tags:
  - shaping-layout
---

# Complex text layout

## Definition

Complex text layout is the extra work software does to display writing in which the shape or position of a character depends on the characters around it.<sup>1</sup>

It is often shortened to CTL. A [script](../../language-terms/writing-systems-and-scripts/script.md) is a set of symbols and rules used to write one or more languages, and the scripts that need this extra work are often called complex scripts. [Arabic](../../language-terms/writing-systems-and-scripts/arabic-script.md), [Devanagari](../../language-terms/writing-systems-and-scripts/devanagari.md) and [Thai](../../language-terms/writing-systems-and-scripts/thai-script.md) are three of them.<sup>2</sup>

### Why it matters in design systems

Type an English word and each letter appears as you press its key. The first letter sits at the left, the next one to its right, and no letter changes because of the one beside it. The letters can be drawn in the same order they are stored.<sup>3</sup>

Many scripts do not work this way. What is drawn depends on the neighbours. This glossary does not cover every script or every behaviour, so here are four to start with. Select a linked term to go to its glossary page.

| What happens | Example | Glossary term |
| ------------ | ------- | ------------- |
| Letters take a joined form | The Arabic letters kāf, tāʾ, bāʾ (ك ت ب) are drawn as كتب<sup>4</sup> | [Joining](../../language-terms/writing-systems-and-scripts/joining.md) |
| Two letters become one shape | The Arabic letters lam and alef (ل and ا) are drawn as لا<sup>5</sup> | [Ligature](ligature.md) |
| Consonants merge | The Devanagari letters क and ष, with no vowel between them, are drawn as क्ष<sup>6</sup> | [Conjunct](../../language-terms/writing-systems-and-scripts/conjunct.md) |
| A mark is drawn before the letter it follows | In the Devanagari कि, the vowel mark is stored after क and drawn to its left<sup>7</sup> | [Reordering](reordering.md) |

Drawing text like this takes two things working together. The [font](font.md) has to contain the extra shapes, and instructions for when to use them. The software has to contain a [shaping engine](shaping-engine.md), the part that reads those instructions and applies the rules of the script.<sup>8</sup> Complex text layout is the name for that whole job. The step itself is called [text shaping](text-shaping.md).

The font keeps its instructions in two parts. One, called [GSUB](gsub.md), lists the shapes to swap for other shapes. The other, called [GPOS](gpos.md), lists where each shape goes.<sup>9</sup>

The word "complex" describes the work the software has to do. It says nothing about how hard a script is to read or to write. The comparison behind the word is with English written in the [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md), which one widely used code library, [ICU](icu.md), describes as the least complex script to display.<sup>10</sup>

"Not complex" does not mean "no work", either. Latin text is shaped too. Some pairs of letters are moved closer together, which is called [kerning](../../design-terms/typography/kerning.md), and accents have to be placed on their letters. Microsoft's guidance for Latin, Cyrillic and Greek fonts covers both.<sup>11</sup>

You will meet more than one name for this idea:

* **Complex Text Layout (CTL)** is the name used in LibreOffice, a free office suite, where it is a setting you switch on for certain languages.<sup>12</sup>
* **Complex text** and **complex scripts** are the words used in ICU's documentation for its older layout engine.<sup>13</sup>
* **Complex script** is the term in Microsoft's guidance for font makers. Microsoft calls every other script a standard script.<sup>14</sup>

The lists behind these names do not match exactly. LibreOffice counts writing from right to left as one reason to call a language CTL.<sup>15</sup> Microsoft's test is narrower: a script is complex if it needs reordering or contextual analysis, which means working out a shape from its neighbours. This glossary covers direction on its own pages, starting with [bidirectional text](../../language-terms/writing-systems-and-scripts/bidirectional-text.md).

<!-- NEEDS EXPERT REVIEW: the ICU page read for this entry says "complex text" and "complex scripts", not "complex text layout". Only LibreOffice was confirmed using the full phrase and the CTL abbreviation. Confirm whether ICU should be credited with the phrase itself. -->

### Common mistake

Checking the font and stopping there. A team confirms that a font "supports Arabic" or "supports Hindi", sees the characters appear, and moves on. But a font can only supply shapes and instructions. Part of the work is not in the font at all. Microsoft's guidance for Devanagari fonts says a font should not try to reorder, because the shaping engine does that.<sup>16</sup> So a good font can still be drawn wrongly by a tool that does not shape text. Check the tool as well as the font.

### In practice

* **Test each tool with a real word.** Put a real word in the script into every tool your text passes through: the design tool, the browser, and anything that produces a PDF or an image. Compare it with the table above. Do the letters join? Is the mark on the correct side? If you do not read the script, ask someone who does, because broken text can look fine to a person who cannot read it.
* **Keep letter spacing at zero for scripts that join.** Extra space between letters pulls joined letters apart. MDN, a reference site for web developers, says languages that use the Arabic script expect connected letters to stay visually connected.<sup>17</sup> If your design system has [letter spacing](../../design-terms/typography/letter-spacing.md) tokens, do not apply them to these scripts.
* **Choose a font for its instructions, not only its characters.** A font can contain a script's characters and still lack the instructions for joining them, merging them and placing their marks. See [font coverage](font-coverage.md), then test with real words before you commit to the font.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Bidirectional text](../../language-terms/writing-systems-and-scripts/bidirectional-text.md) · [Character](../text-in-software/character.md) · [Conjunct](../../language-terms/writing-systems-and-scripts/conjunct.md) · [Devanagari script](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [GPOS](gpos.md) · [GSUB](gsub.md) · [ICU](icu.md) · [Joining](../../language-terms/writing-systems-and-scripts/joining.md) · [Kerning](../../design-terms/typography/kerning.md) · [Language](../../language-terms/linguistics/language.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Letter spacing](../../design-terms/typography/letter-spacing.md) · [Ligature](ligature.md) · [Mark](../../language-terms/writing-systems-and-scripts/mark.md) · [Matra](../../language-terms/writing-systems-and-scripts/matra.md) · [Reordering](reordering.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Shaping engine](shaping-engine.md) · [Stacking script](../../language-terms/writing-systems-and-scripts/stacking-script.md) · [Text shaping](text-shaping.md) · [Thai script](../../language-terms/writing-systems-and-scripts/thai-script.md) · [Text shaping & layout](../text-shaping-and-layout/)

### Further reading

* Foundations: [Shaping concepts (HarfBuzz)](https://harfbuzz.github.io/shaping-concepts.html)

### Sources

1. "Standard Script - Any non-complex script; any script that does not require re-ordering or contextual analysis in the shaping process" - Developing OpenType Fonts for Standard Scripts (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/standard](https://learn.microsoft.com/en-us/typography/script-development/standard)
2. "Examples of complex scripts are the Indic scripts (for example, Devanagari, Tamil, Telugu, and Gujarati), Thai, and Arabic" - Layout Engine, ICU Documentation [https://unicode-org.github.io/icu/userguide/layoutengine/](https://unicode-org.github.io/icu/userguide/layoutengine/)
3. "Using the Latin script, characters can be displayed from left to right in the order that they are stored in memory" - Layout Engine, ICU Documentation [https://unicode-org.github.io/icu/userguide/layoutengine/](https://unicode-org.github.io/icu/userguide/layoutengine/)
4. "To decide, you need to analyze the whole string and determine the appropriate glyph for each character based on its position" - Why do I need a shaping engine?, HarfBuzz Manual [https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)
5. "When supported by the style of the font, lam-alef ligatures are considered obligatory" - The Unicode Standard, Version 18.0, Chapter 9: Middle East-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-9/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-9/)
6. "a fully ligated conjunct K.SSA, in which the components are no longer distinct" - The Unicode Standard, Version 18.0, Chapter 12: South and Central Asia-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/)
7. "the software that renders the Indic scripts must be able to reorder elements in mapping from the logical (character) store to the presentational (glyph) rendering" - The Unicode Standard, Version 18.0, Chapter 12: South and Central Asia-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/)
8. "for other scripts (often unceremoniously called complex scripts), any combination of several shaping operations may be required, and the rules for how and when they are applied vary from script to script. HarfBuzz and other shaping engines implement these rules" - Shaping concepts, HarfBuzz Manual [https://harfbuzz.github.io/shaping-concepts.html](https://harfbuzz.github.io/shaping-concepts.html)
9. "These shaping models depend on the font incorporating certain features as lookups in its GSUB and GPOS tables" - What is HarfBuzz?, HarfBuzz Manual [https://harfbuzz.github.io/what-is-harfbuzz.html](https://harfbuzz.github.io/what-is-harfbuzz.html)
10. "The Latin script, which is the most commonly used script among software developers, is also the least complex script to display especially when it is used to write English" - Layout Engine, ICU Documentation [https://unicode-org.github.io/icu/userguide/layoutengine/](https://unicode-org.github.io/icu/userguide/layoutengine/)
11. "Apply feature 'kern' to provide pair kerning between base glyphs requiring adjustment for better typographical quality" and "Apply feature 'mark' to position diacritic glyphs to the base glyph" - Developing OpenType Fonts for Standard Scripts (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/standard](https://learn.microsoft.com/en-us/typography/script-development/standard)
12. "Currently, LibreOffice supports Hindi, Thai, Hebrew, and Arabic as CTL languages" and "Enable CTL support using" - General Glossary: Complex Text Layout (CTL), LibreOffice Help [https://help.libreoffice.org/latest/en-US/text/shared/00/00000005.html](https://help.libreoffice.org/latest/en-US/text/shared/00/00000005.html)
13. "We refer to these scripts as “complex scripts” and to text written in these scripts as “complex text.”" - Layout Engine, ICU Documentation [https://unicode-org.github.io/icu/userguide/layoutengine/](https://unicode-org.github.io/icu/userguide/layoutengine/)
14. "In this document, "standard" refers to any non-complex script, that is, any script that does not require re-ordering or contextual analysis" - Developing OpenType Fonts for Standard Scripts (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/standard](https://learn.microsoft.com/en-us/typography/script-development/standard)
15. "Languages with complex text layout may have some or all of the following features", one of which is "The text direction is from right to left" - General Glossary: Complex Text Layout (CTL), LibreOffice Help [https://help.libreoffice.org/latest/en-US/text/shared/00/00000005.html](https://help.libreoffice.org/latest/en-US/text/shared/00/00000005.html)
16. "OpenType fonts should not have substitutions that attempt to perform the re-ordering" - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
17. "languages that use the Arabic script expect connected letters to remain visually connected, as in the following example. Applying letter spacing may lead to the text looking broken" - letter-spacing (MDN) [https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing)
