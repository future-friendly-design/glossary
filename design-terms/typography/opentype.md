---
term: OpenType
slug: opentype
aliases:
  - OTF
  - OpenType font format
level: foundational
depth: core
summary: OpenType is a font file format, and it is the most widely used one.
related:
  - opentype-features
  - gsub
  - gpos
  - glyph
  - font
status: voice-passed
version_added: 0.1
updated: 2026-10-13T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: OpenType specification overview (Microsoft)
    url: https://learn.microsoft.com/en-us/typography/opentype/spec/overview
    type: code
  - title: Use OpenType features (Figma Learn)
    url: >-
      https://help.figma.com/hc/en-us/articles/4913951097367-Use-OpenType-features
    type: design-tool
license: CC-BY-4.0
tags:
  - shaping-layout
---

# OpenType

## Definition

OpenType is a font file format, and it is the most widely used one.<sup>1</sup>

A file format is an agreed way of arranging what is inside a file, so that any software can open the file and find what it needs. A [font](../../programming-terms/text-for-digital-products-and-the-web/font.md) file holds drawn shapes, called [glyphs](../../programming-terms/text-for-digital-products-and-the-web/glyph.md), and instructions for choosing those shapes and placing them in a line.<sup>2</sup> OpenType is the agreement about where each of those things sits in the file.

### Why it matters in design systems

Download a font and look at the file name. It usually ends in `.otf` or `.ttf`, and a file with either ending can be an OpenType font.<sup>3</sup> The word also turns up in design tools, where a panel of type settings is often labelled "OpenType". So the name is familiar long before anyone explains what it promises, and it is easy to assume it promises more than it does.

Here is what the format gives a font maker room for:

| An OpenType font file can hold           | What that is for                                                                                                                                                                     |
| ---------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Drawn shapes                             | The outlines of the glyphs, the shapes that appear on screen.<sup>4</sup>                                                                                                            |
| A list that matches characters to shapes | Text is stored as [characters](../../programming-terms/text-in-software/character.md), each saved as a number. The list says which shape to start with for each one.<sup>5</sup>     |
| Instructions for swapping shapes         | Two letters drawn as one combined shape, or an Arabic letter changing form inside a word. This part of the file is called [GSUB](../../programming-terms/fonts/gsub.md).<sup>6</sup> |
| Instructions for placing shapes          | Setting a mark above a letter, or closing the gap between two letters. This part is called [GPOS](../../programming-terms/fonts/gpos.md).<sup>7</sup>                                |
| Several weights or widths in one file    | A font built this way is called a [variable font](variable-font.md).<sup>8</sup>                                                                                                     |

Every row says "can hold". That is the part people miss. The format has room for every character in [Unicode](../../programming-terms/text-in-software/unicode.md), the standard list of the world's characters, but no font fills that room.<sup>9</sup> A font holds the shapes somebody drew for it, which may come from one [script](../../language-terms/writing-systems-and-scripts/script.md) or from many.<sup>10</sup> A script is a set of symbols used to write one or more languages, such as Latin, Arabic or Devanagari. So "it is an OpenType font" tells you how the file is arranged. It does not tell you which scripts the font has shapes for.

It helps to keep four levels apart, because a problem at one level is not fixed at another:

* **The format** is OpenType. It decides what a font file is able to hold.
* **The font** is one file in that format. It holds the shapes and instructions its maker put in, and nothing else. The instructions are sorted into named groups called [OpenType features](opentype-features.md).
* **The software** that draws text reads the font and follows its instructions.<sup>11</sup> A font is a file, and a file does nothing by itself. This software is called a [shaping engine](../../programming-terms/text-shaping-and-layout/shaping-engine.md).
* **The script** sets the rules for what correct text looks like. The software supplies some of those rules itself, and the OpenType specification says plainly that the full rules for each script are outside what it covers.<sup>12</sup>

Two things that are often credited to OpenType sit at the software level. When Devanagari draws a vowel mark before the letter it is typed after, the software moves it, and fonts are told not to try.<sup>13</sup> And the order of right-to-left text, including what happens when Arabic or Hebrew is mixed with English on one line, is worked out by the software from rules that Unicode publishes.<sup>14</sup> Neither is an OpenType feature, and no font setting switches them on.

For your work, this changes the question to ask about a font. "Is it OpenType?" is almost always yes, and the answer settles nothing. Ask instead which scripts the font has shapes for, whether it has the instructions those scripts need, and whether each tool your team uses follows them. The quickest check for all three is to type a real word in that script into each tool and show it to someone who reads it.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Bidirectional text](../../language-terms/writing-systems-and-scripts/bidirectional-text.md) · [Character](../../programming-terms/text-in-software/character.md) · [Devanagari script](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Font](../../programming-terms/text-for-digital-products-and-the-web/font.md) · [Font coverage](../../programming-terms/text-for-digital-products-and-the-web/font-coverage.md) · [Glyph](../../programming-terms/text-for-digital-products-and-the-web/glyph.md) · [GPOS](../../programming-terms/fonts/gpos.md) · [GSUB](../../programming-terms/fonts/gsub.md) · [Hebrew script](../../language-terms/writing-systems-and-scripts/hebrew-script.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Ligature](../../programming-terms/fonts/ligature.md) · [Mark](../../language-terms/writing-systems-and-scripts/mark.md) · [Matra](../../language-terms/writing-systems-and-scripts/matra.md) · [OpenType features](opentype-features.md) · [Reordering](../../programming-terms/text-shaping-and-layout/reordering.md) · [Right-to-left](../../language-terms/writing-systems-and-scripts/right-to-left.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Shaping engine](../../programming-terms/text-shaping-and-layout/shaping-engine.md) · [Text shaping](../../programming-terms/text-shaping-and-layout/text-shaping.md) · [Unicode](../../programming-terms/text-in-software/unicode.md) · [Variable font](variable-font.md) · [Font terms](../../programming-terms/fonts/)

### Further reading

* Code & specs: [OpenType specification overview (Microsoft)](https://learn.microsoft.com/en-us/typography/opentype/spec/overview)
* Design tools: [Use OpenType features (Figma Learn)](https://help.figma.com/hc/en-us/articles/4913951097367-Use-OpenType-features)

### Sources

1. "There are several font formats that a program might encounter, each of which has a set of standard text-shaping rules. The dominant format is OpenType" - What is HarfBuzz?, HarfBuzz Manual [https://harfbuzz.github.io/what-is-harfbuzz.html](https://harfbuzz.github.io/what-is-harfbuzz.html)
2. "Portions of the data are used by applications to calculate the layout of text using the font; that is, the selection of glyphs and their placement within a line. Other data provide descriptions of glyphs" - The OpenType Font File, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/otff](https://learn.microsoft.com/en-us/typography/opentype/spec/otff)
3. "OpenType font files may have the extension .OTF, .TTF, .OTC or .TTC. (The extension may be upper or lower case.)" - The OpenType Font File, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/otff](https://learn.microsoft.com/en-us/typography/opentype/spec/otff)
4. "Glyph outline data can use the CFF or CFF version 2 (“CFF2”) formats, as well as the TrueType glyph format" - OpenType specification overview (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/overview](https://learn.microsoft.com/en-us/typography/opentype/spec/overview)
5. "To retrieve glyphs, the client uses information in the 'cmap' table of the font, which maps the client’s character codes to glyph indices" - Advanced typographic tables: OpenType Layout, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/ttochap1](https://learn.microsoft.com/en-us/typography/opentype/spec/ttochap1)
6. "The Glyph Substitution (GSUB) table provides data for substitution of glyphs for appropriate rendering of scripts, such as cursively-connecting forms in Arabic script, or for advanced typographic effects, such as ligatures" - GSUB: Glyph Substitution Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gsub](https://learn.microsoft.com/en-us/typography/opentype/spec/gsub)
7. "The Glyph Positioning table (GPOS) provides precise control over glyph placement for sophisticated text layout and rendering in each script and language system that a font supports" - GPOS: Glyph Positioning Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gpos](https://learn.microsoft.com/en-us/typography/opentype/spec/gpos)
8. "OpenType Font Variations allow a font designer to incorporate multiple font faces within a font family into a single font resource" - OpenType Font Variations Overview, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview](https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview)
9. "All Unicode® characters can be supported, including supplementary-plane characters, as well as Unicode variation sequences" - OpenType specification overview (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/overview](https://learn.microsoft.com/en-us/typography/opentype/spec/overview)
10. "A font may support characters from a single script, or from many scripts" - Advanced typographic tables: OpenType Layout, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/ttochap1](https://learn.microsoft.com/en-us/typography/opentype/spec/ttochap1)
11. "In all cases, the text-processing client is responsible for applying, combining, and arbitrating among features and rendering the result" - Feature Tags, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/featuretags](https://learn.microsoft.com/en-us/typography/opentype/spec/featuretags)
12. "complete specification of shaping algorithms for different scripts is beyond the scope of this specification" - OpenType specification overview (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/overview](https://learn.microsoft.com/en-us/typography/opentype/spec/overview)
13. "OpenType fonts should not have substitutions that attempt to perform the re-ordering" - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
14. "This annex describes specifications for the positioning of characters in text containing characters flowing from right to left, such as Arabic or Hebrew" - Unicode Standard Annex #9: Unicode Bidirectional Algorithm, Revision 52 (Unicode 18.0.0) [https://www.unicode.org/reports/tr9/tr9-52.html](https://www.unicode.org/reports/tr9/tr9-52.html)
