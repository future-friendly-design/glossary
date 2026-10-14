---
term: Complex text layout
slug: complex-text-layout
aliases:
  - CTL
  - complex script
  - complex script rendering
level: advanced
depth: deep
summary: >-
  Complex text layout is a name for text shaping in the scripts where shaping
  has the most to do.
related:
  - text-shaping
  - reordering
  - stacking-script
  - bidirectional-text
  - matra
status: voice-passed
version_added: 0.1
updated: 2026-10-13T00:00:00.000Z
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

Complex text layout is a name for text shaping in the scripts where shaping has the most to do.<sup>1</sup> In those scripts, the right shape or position of a character depends on the characters around it, or characters appear in a different order from the one they are stored in.<sup>2</sup>

It is not a separate step from [text shaping](text-shaping.md), the step in which software picks the right shapes from a font for a piece of text and decides where each one goes. It is the same job, named for the scripts that need the most of it.

It is often shortened to CTL. A [script](../../language-terms/writing-systems-and-scripts/script.md) is a set of symbols and rules used to write one or more languages, and the scripts that need this extra work are often called complex scripts. [Arabic](../../language-terms/writing-systems-and-scripts/arabic-script.md), [Devanagari](../../language-terms/writing-systems-and-scripts/devanagari.md) and [Thai](../../language-terms/writing-systems-and-scripts/thai-script.md) are three of them.<sup>3</sup>

### Why it matters in design systems

Type an English word and each letter appears as you press its key. The first letter sits at the left, the next one to its right, and no letter has to change because of the one beside it. The letters can appear in the same order they are stored.<sup>4</sup>

Many scripts do not work this way, because what appears on screen depends on the neighbours. This glossary does not cover every script or every behaviour, so here are four to start with. Select a linked term to go to its glossary page.

| What happens                                        | Example                                                                                  | Glossary term                                                            |
| --------------------------------------------------- | ---------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| Letters take a joined form                          | The Arabic letters kāf ك, tāʾ ت and bāʾ ب appear as كتب<sup>5</sup>                      | [Joining](../../language-terms/writing-systems-and-scripts/joining.md)   |
| Two letters become one shape                        | The Arabic letters lam (ل) and alef (ا) appear as لا<sup>6</sup>                         | [Ligature](../fonts/ligature.md)                                         |
| Consonants merge                                    | The Devanagari consonants क and ष, with no vowel between them, appear as क्ष<sup>7</sup> | [Conjunct](../../language-terms/writing-systems-and-scripts/conjunct.md) |
| A mark stored after its consonant appears before it | In the Devanagari कि, the vowel mark is stored after क and shown to its left<sup>8</sup> | [Reordering](reordering.md)                                              |

Displaying text like this takes two things working together. The [font](../text-for-digital-products-and-the-web/font.md) is a file of shapes, and each shape is called a [glyph](../text-for-digital-products-and-the-web/glyph.md). It has to contain the extra glyphs, and instructions for when to use them. The software has to contain a [shaping engine](shaping-engine.md), the part that reads those instructions and applies the rules of the script.<sup>9</sup> That step is called text shaping, and every script goes through it. Complex text layout is a name for it in the scripts where it has the most to do.

The word "complex" describes the work the software has to do, and says nothing about how hard a script is to read or to write. The comparison behind the word is with English written in the [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md), which one widely used code library, [ICU](../internationalization-and-localization/icu.md), describes as the least complex script to display.<sup>10</sup>

"Not complex" does not mean "no work", either. English text is shaped too. Some pairs of letters are moved closer together, which is called [kerning](../../design-terms/typography/kerning.md), and where a Latin letter carries an accent, the accent has to be placed on it.<sup>11</sup>

You will meet more than one name for this idea:

* **Complex Text Layout (CTL)** is the name used in LibreOffice, a free office suite, where it is a setting you switch on for certain languages.<sup>12</sup>
* **Complex text** and **complex scripts** are the words used in ICU's documentation for its layout engine, which has since been removed.<sup>13</sup>
* **Complex script** is the term in Microsoft's guidance for font makers, which calls every other script a standard script.<sup>14</sup>

The lists behind these names do not match exactly. LibreOffice counts writing from right to left as one reason to call a language CTL.<sup>15</sup> So in LibreOffice the name also covers direction, which is a separate job from shaping. Microsoft's test is narrower: a script is complex if it needs reordering or contextual analysis, which means working out a shape from its neighbours.<sup>16</sup>

### Common mistake

Treating right-to-left as the test. A team builds "RTL support", sees Arabic start from the right edge, and counts the script as done. But direction and shaping are two separate jobs, and a shaping engine such as HarfBuzz does not sort out direction at all.<sup>17</sup> So Arabic can run the correct way and still come out as separate letters. It fails the other way round too: Devanagari is written from left to right, like English, and needs every part of this work.<sup>18</sup> Check the direction and the shaping as two separate things. This glossary covers direction on its own pages: [text direction](../../language-terms/writing-systems-and-scripts/text-direction.md), [right-to-left](../../language-terms/writing-systems-and-scripts/right-to-left.md) and [bidirectional text](../../language-terms/writing-systems-and-scripts/bidirectional-text.md).

### In practice

* **Test one real word for each behaviour.** The table above is a test plan. Pick a word that joins, a word with a required ligature, a word with a conjunct and a word with a reordered mark, and put them into every tool your text passes through: the design tool, the browser, and anything that produces a PDF or an image. If you do not read the script, ask someone who does, because broken text can look fine to a person who cannot read it.
* **Keep letter spacing at zero for scripts that join.** Extra space between letters can pull joined letters apart, depending on the tool, and readers of the Arabic script expect connected letters to stay connected.<sup>19</sup> If your design system has [letter spacing](../../design-terms/typography/letter-spacing.md) [tokens](../../design-terms/design-token.md), do not apply them to these scripts.
* **Look for a second font setting in office tools.** LibreOffice keeps one font setting for text in the Latin script and a separate one for complex text layout.<sup>20</sup> Set your brand fonts in both when you build templates.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Bidirectional text](../../language-terms/writing-systems-and-scripts/bidirectional-text.md) · [Character](../text-in-software/character.md) · [Conjunct](../../language-terms/writing-systems-and-scripts/conjunct.md) · [Design token](../../design-terms/design-token.md) · [Devanagari script](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Font](../text-for-digital-products-and-the-web/font.md) · [Font coverage](../text-for-digital-products-and-the-web/font-coverage.md) · [Glyph](../text-for-digital-products-and-the-web/glyph.md) · [GPOS](../fonts/gpos.md) · [GSUB](../fonts/gsub.md) · [ICU](../internationalization-and-localization/icu.md) · [Joining](../../language-terms/writing-systems-and-scripts/joining.md) · [Kerning](../../design-terms/typography/kerning.md) · [Language](../../language-terms/linguistics/language.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Letter spacing](../../design-terms/typography/letter-spacing.md) · [Ligature](../fonts/ligature.md) · [Mark](../../language-terms/writing-systems-and-scripts/mark.md) · [Matra](../../language-terms/writing-systems-and-scripts/matra.md) · [Reordering](reordering.md) · [Right-to-left](../../language-terms/writing-systems-and-scripts/right-to-left.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../../language-terms/writing-systems-and-scripts/script-rules.md) · [Shaping engine](shaping-engine.md) · [Stacking script](../../language-terms/writing-systems-and-scripts/stacking-script.md) · [Text direction](../../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](text-shaping.md) · [Thai script](../../language-terms/writing-systems-and-scripts/thai-script.md) · [Virama](../../language-terms/writing-systems-and-scripts/virama.md) · [Text shaping & layout terms](./)

### Further reading

* Foundations: [Shaping concepts (HarfBuzz)](https://harfbuzz.github.io/shaping-concepts.html)

### Sources

1. "for other scripts (often unceremoniously called complex scripts), any combination of several shaping operations may be required, and the rules for how and when they are applied vary from script to script" - Shaping concepts, HarfBuzz Manual [https://harfbuzz.github.io/shaping-concepts.html](https://harfbuzz.github.io/shaping-concepts.html)
2. "In this document, "standard" refers to any non-complex script, that is, any script that does not require re-ordering or contextual analysis" - Developing OpenType Fonts for Standard Scripts (Microsoft), Introduction [https://learn.microsoft.com/en-us/typography/script-development/standard](https://learn.microsoft.com/en-us/typography/script-development/standard)
3. "Examples of complex scripts are the Indic scripts (for example, Devanagari, Tamil, Telugu, and Gujarati), Thai, and Arabic" - Layout Engine, ICU Documentation [https://unicode-org.github.io/icu/userguide/layoutengine/](https://unicode-org.github.io/icu/userguide/layoutengine/)
4. "Using the Latin script, characters can be displayed from left to right in the order that they are stored in memory" - Layout Engine, ICU Documentation [https://unicode-org.github.io/icu/userguide/layoutengine/](https://unicode-org.github.io/icu/userguide/layoutengine/)
5. "To decide, you need to analyze the whole string and determine the appropriate glyph for each character based on its position" - Why do I need a shaping engine?, HarfBuzz Manual [https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)
6. "When supported by the style of the font, lam-alef ligatures are considered obligatory" - The Unicode Standard, Version 18.0, Chapter 9: Middle East-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-9/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-9/)
7. "a fully ligated conjunct K.SSA, in which the components are no longer distinct" - The Unicode Standard, Version 18.0, Chapter 12: South and Central Asia-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/)
8. "the software that renders the Indic scripts must be able to reorder elements in mapping from the logical (character) store to the presentational (glyph) rendering" - The Unicode Standard, Version 18.0, Chapter 12: South and Central Asia-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/)
9. "HarfBuzz and other shaping engines implement these rules" - Shaping concepts, HarfBuzz Manual [https://harfbuzz.github.io/shaping-concepts.html](https://harfbuzz.github.io/shaping-concepts.html)
10. "The Latin script, which is the most commonly used script among software developers, is also the least complex script to display especially when it is used to write English" - Layout Engine, ICU Documentation [https://unicode-org.github.io/icu/userguide/layoutengine/](https://unicode-org.github.io/icu/userguide/layoutengine/)
11. "Apply feature 'kern' to provide pair kerning between base glyphs requiring adjustment for better typographical quality" and "Apply feature 'mark' to position diacritic glyphs to the base glyph" - Developing OpenType Fonts for Standard Scripts (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/standard](https://learn.microsoft.com/en-us/typography/script-development/standard)
12. "Currently, LibreOffice supports Hindi, Thai, Hebrew, and Arabic as CTL languages" and "Enable CTL support using" - General Glossary: Complex Text Layout (CTL), LibreOffice Help [https://help.libreoffice.org/latest/en-US/text/shared/00/00000005.html](https://help.libreoffice.org/latest/en-US/text/shared/00/00000005.html)
13. "We refer to these scripts as “complex scripts” and to text written in these scripts as “complex text.”" and "The ICU Line LayoutEngine has been removed in ICU 58" - Layout Engine, ICU Documentation [https://unicode-org.github.io/icu/userguide/layoutengine/](https://unicode-org.github.io/icu/userguide/layoutengine/)
14. "In this document, "standard" refers to any non-complex script, that is, any script that does not require re-ordering or contextual analysis" - Developing OpenType Fonts for Standard Scripts (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/standard](https://learn.microsoft.com/en-us/typography/script-development/standard)
15. "Languages with complex text layout may have some or all of the following features", one of which is "The text direction is from right to left" - General Glossary: Complex Text Layout (CTL), LibreOffice Help [https://help.libreoffice.org/latest/en-US/text/shared/00/00000005.html](https://help.libreoffice.org/latest/en-US/text/shared/00/00000005.html)
16. "Standard Script - Any non-complex script; any script that does not require re-ordering or contextual analysis in the shaping process" - Developing OpenType Fonts for Standard Scripts (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/standard](https://learn.microsoft.com/en-us/typography/script-development/standard)
17. "HarfBuzz won't help you with bidirectionality" - What HarfBuzz doesn't do, HarfBuzz Manual [https://harfbuzz.github.io/what-harfbuzz-doesnt-do.html](https://harfbuzz.github.io/what-harfbuzz-doesnt-do.html)
18. Of the scripts of South Asia: "With minor historical exceptions, they are written from left to right" - The Unicode Standard, Version 18.0, Chapter 12: South and Central Asia-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/)
19. "languages that use the Arabic script expect connected letters to remain visually connected, as in the following example. Applying letter spacing may lead to the text looking broken" - letter-spacing (MDN) [https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing)
20. "you can change the formatting for the following font types", which include "Western text font - Latin character sets" and "Complex text layout font - right-to-left text direction" - Font, LibreOffice Help [https://help.libreoffice.org/latest/en-US/text/shared/01/05020100.html](https://help.libreoffice.org/latest/en-US/text/shared/01/05020100.html)
