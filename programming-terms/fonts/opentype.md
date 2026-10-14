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
updated: 2026-10-14
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

OpenType is the format a [font](font.md) is stored in.<sup>2</sup> A font is the file that holds the shapes software uses to show text.

A file format is an agreed way of arranging what is inside a file, so that any software can open the file and find what it needs. A font file holds the shape for each character, called a [glyph](glyph.md), plus instructions for picking those glyphs and placing them in a line.<sup>3</sup> OpenType is the agreement about where each of those things sits in the file.

### Why it matters in design systems

Download a font and look at the file name. It usually ends in `.otf` or `.ttf`, and a file with either ending can be an OpenType font.<sup>4</sup> The word also turns up in design tools, where a panel of type settings is often labelled "OpenType". So the name is familiar long before anyone explains what it promises, and it is easy to assume it promises more than it does.

| An OpenType font file can hold           | What that is for                                                                                                                                            |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Glyphs                                   | The outlines of the glyphs.<sup>5</sup>                                                                                                                     |
| A list that matches characters to glyphs | Text is stored as [characters](../text-in-software/character.md), each saved as a number. The list says which glyph to start with for each one.<sup>6</sup> |
| Instructions for swapping glyphs         | Two letters shown as one combined glyph, or an [Arabic](../../language-terms/writing-systems-and-scripts/arabic-script.md) letter changing form inside a word. This part of the file is called [GSUB](gsub.md).<sup>7</sup>      |
| Instructions for placing glyphs          | Setting a [mark](../../language-terms/writing-systems-and-scripts/mark.md) above a [symbol](../../language-terms/writing-systems-and-scripts/symbol.md), or closing the gap between two letters. This part is called [GPOS](gpos.md).<sup>8</sup>                                     |
| Several weights or widths in one file    | A font built this way is called a [variable font](variable-font.md).<sup>9</sup>                                                                            |

Every row says "can hold". That is the part people miss. The format has room for every character in [Unicode](../text-in-software/unicode.md), the standard list of the world's characters.<sup>10</sup> A font holds only the glyphs somebody drew for it, which may come from one [script](../../language-terms/writing-systems-and-scripts/script.md) or from many.<sup>11</sup> A script is a set of symbols used to write one or more languages, such as [Latin](../../language-terms/writing-systems-and-scripts/latin-script.md), Arabic or [Devanagari](../../language-terms/writing-systems-and-scripts/devanagari.md). So "it is an OpenType font" tells you how the file is arranged. It does not tell you which scripts the font has glyphs for.

It helps to keep four levels apart, because a problem at one level is not fixed at another:

* **The format** is OpenType. It decides what a font file is able to hold.
* **The font** is one file in that format. It holds the glyphs and instructions its maker put in, and nothing else. The instructions are sorted into named groups called [OpenType features](opentype-features.md).
* **The software** that picks and places the glyphs reads the font and follows its instructions.<sup>12</sup> A font is a file, and a file does nothing by itself. This software is called a [shaping engine](../text-shaping-and-layout/shaping-engine.md).
* **The script** sets the rules for what correct text looks like. The software supplies some of those rules itself, and the OpenType specification says plainly that the full rules for each script are outside what it covers.<sup>13</sup>

Two things that are often credited to OpenType sit at the software level. When a Devanagari [vowel mark](../../language-terms/writing-systems-and-scripts/matra.md) appears before the letter it is typed after, the software moves it, and fonts are told not to try.<sup>14</sup> And the order of [right-to-left](../../language-terms/writing-systems-and-scripts/right-to-left.md) text, including what happens when Arabic or [Hebrew](../../language-terms/writing-systems-and-scripts/hebrew-script.md) is mixed with English on one line, is worked out by the software from rules that Unicode publishes.<sup>15</sup> Neither is an OpenType feature, and no font setting switches them on.

For your work, this changes the question to ask about a font. "Is it OpenType?" is almost always yes, and the answer settles nothing. Ask instead which scripts the font has glyphs for, whether it has the instructions those scripts need, and whether each tool your team uses follows them. The quickest check for all three is to type a real word in that script into each tool and show it to someone who reads it.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Bidirectional text](../../language-terms/writing-systems-and-scripts/bidirectional-text.md) · [Character](../text-in-software/character.md) · [Devanagari script](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [GPOS](gpos.md) · [GSUB](gsub.md) · [Hebrew script](../../language-terms/writing-systems-and-scripts/hebrew-script.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Ligature](ligature.md) · [Mark](../../language-terms/writing-systems-and-scripts/mark.md) · [Matra](../../language-terms/writing-systems-and-scripts/matra.md) · [OpenType features](opentype-features.md) · [Reordering](../text-shaping-and-layout/reordering.md) · [Right-to-left](../../language-terms/writing-systems-and-scripts/right-to-left.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Shaping engine](../text-shaping-and-layout/shaping-engine.md) · [Symbol](../../language-terms/writing-systems-and-scripts/symbol.md) · [Text shaping](../text-shaping-and-layout/text-shaping.md) · [Unicode](../text-in-software/unicode.md) · [Variable font](variable-font.md) · [Font terms](./)

### Further reading

* Code & specs: [OpenType specification overview (Microsoft)](https://learn.microsoft.com/en-us/typography/opentype/spec/overview)
* Design tools: [Use OpenType features (Figma Learn)](https://help.figma.com/hc/en-us/articles/4913951097367-Use-OpenType-features)

### Sources

1. "There are several font formats that a program might encounter, each of which has a set of standard text-shaping rules. The dominant format is OpenType" - What is HarfBuzz?, HarfBuzz Manual [https://harfbuzz.github.io/what-is-harfbuzz.html](https://harfbuzz.github.io/what-is-harfbuzz.html)
2. "The OpenType font format is a widely-supported format for font data with a rich set of capabilities for digital typography" - OpenType specification overview (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/overview](https://learn.microsoft.com/en-us/typography/opentype/spec/overview)
3. "Portions of the data are used by applications to calculate the layout of text using the font; that is, the selection of glyphs and their placement within a line. Other data provide descriptions of glyphs" - The OpenType Font File, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/otff](https://learn.microsoft.com/en-us/typography/opentype/spec/otff)
4. "OpenType font files may have the extension .OTF, .TTF, .OTC or .TTC. (The extension may be upper or lower case.)" - The OpenType Font File, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/otff](https://learn.microsoft.com/en-us/typography/opentype/spec/otff)
5. "Glyph outline data can use the CFF or CFF version 2 (“CFF2”) formats, as well as the TrueType glyph format" - OpenType specification overview (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/overview](https://learn.microsoft.com/en-us/typography/opentype/spec/overview)
6. "To retrieve glyphs, the client uses information in the 'cmap' table of the font, which maps the client’s character codes to glyph indices" - Advanced typographic tables: OpenType Layout, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/ttochap1](https://learn.microsoft.com/en-us/typography/opentype/spec/ttochap1)
7. "The Glyph Substitution (GSUB) table provides data for substitution of glyphs for appropriate rendering of scripts, such as cursively-connecting forms in Arabic script, or for advanced typographic effects, such as ligatures" - GSUB: Glyph Substitution Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gsub](https://learn.microsoft.com/en-us/typography/opentype/spec/gsub)
8. "The Glyph Positioning table (GPOS) provides precise control over glyph placement for sophisticated text layout and rendering in each script and language system that a font supports" - GPOS: Glyph Positioning Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gpos](https://learn.microsoft.com/en-us/typography/opentype/spec/gpos)
9. "OpenType Font Variations allow a font designer to incorporate multiple font faces within a font family into a single font resource" - OpenType Font Variations Overview, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview](https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview)
10. "All Unicode® characters can be supported, including supplementary-plane characters, as well as Unicode variation sequences" - OpenType specification overview (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/overview](https://learn.microsoft.com/en-us/typography/opentype/spec/overview)
11. "A font may support characters from a single script, or from many scripts" - Advanced typographic tables: OpenType Layout, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/ttochap1](https://learn.microsoft.com/en-us/typography/opentype/spec/ttochap1)
12. "In all cases, the text-processing client is responsible for applying, combining, and arbitrating among features and rendering the result" - Feature Tags, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/featuretags](https://learn.microsoft.com/en-us/typography/opentype/spec/featuretags)
13. "complete specification of shaping algorithms for different scripts is beyond the scope of this specification" - OpenType specification overview (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/overview](https://learn.microsoft.com/en-us/typography/opentype/spec/overview)
14. "OpenType fonts should not have substitutions that attempt to perform the re-ordering" - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
15. "This annex describes specifications for the positioning of characters in text containing characters flowing from right to left, such as Arabic or Hebrew" - Unicode Standard Annex #9: Unicode Bidirectional Algorithm, Revision 52 (Unicode 18.0.0) [https://www.unicode.org/reports/tr9/tr9-52.html](https://www.unicode.org/reports/tr9/tr9-52.html)
