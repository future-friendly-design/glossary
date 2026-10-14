---
term: Glyph
slug: glyph
aliases: []
level: foundational
depth: core
summary: A glyph is the specific visual shape a font holds for a character.
related:
  - character
  - font
  - code-point
  - ligature
status: voice-passed
version_added: 0.1
updated: 2026-10-14
contributors:
  - sam-gordashko
further_reading:
  - title: Glyph (Unicode Glossary)
    url: https://www.unicode.org/glossary/#glyph
    type: authority
license: CC-BY-4.0
tags:
  - characters-encoding
---

# Glyph

## Definition

A glyph is the specific visual shape a [font](font.md) holds for a [character](../text-in-software/character.md).<sup>1</sup>

A glyph is one of the parts of a font, the file that holds the shapes software uses to show text.<sup>2</sup>

For example, the character `a` is one unit of text, but its glyph looks quite different in a serif [typeface](typeface.md), one with small finishing strokes, than in a sans-serif, one without them.

### Why it matters in design systems

This is the line between what text is and what text looks like. The character is the abstract unit a system stores; the glyph is the shape one font holds for it. Swap the font and every glyph on the page changes while the text itself stays identical, which is why a font change can never fix a spelling and a spelling change can never fix a rendering problem.

The mapping between the two is not one to one in either direction. [Unicode](../text-in-software/unicode.md), the standard that aims to give every character a number, says that a single glyph may correspond to one character or to several, and that a single character may produce multiple glyphs.<sup>3</sup> The software picks them while it lays out the text.<sup>4</sup> The part that does the picking is called a [shaping engine](../text-shaping-and-layout/shaping-engine.md). Several characters collapsing into one glyph is what a [ligature](ligature.md) is. In the [Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) a single letter is shown with a different glyph depending on which letters sit beside it, the behaviour covered under [joining](../../language-terms/writing-systems-and-scripts/joining.md), so one character may correspond to four glyphs in the same font.<sup>5</sup>

That has a practical consequence for a design system. Counting characters tells you nothing about what will be shown. Whether text shows correctly depends on whether the font has the glyphs it needs, which is its [font coverage](font-coverage.md), and on whether the software picks and places them properly, which is [text shaping](../text-shaping-and-layout/text-shaping.md). When no available font has a glyph for a character, software shows an empty box called [tofu](tofu.md). Both conditions have to hold, and neither is visible in the text itself, so both have to be tested by rendering real content in the real tools rather than inspected in a string.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Character](../text-in-software/character.md) · [Code point](../text-in-software/code-point.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Joining](../../language-terms/writing-systems-and-scripts/joining.md) · [Ligature](ligature.md) · [Shaping engine](../text-shaping-and-layout/shaping-engine.md) · [Text shaping](../text-shaping-and-layout/text-shaping.md) · [Tofu](tofu.md) · [Typeface](typeface.md) · [Unicode](../text-in-software/unicode.md) · [Font terms](./)

### Further reading

* Foundations: [Glyph (Unicode Glossary)](https://www.unicode.org/glossary/#glyph)

### Sources

1. "Glyphs represent the shapes that characters can have when they are rendered or displayed" - The Unicode Standard, Core Specification, Chapter 2 [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-2/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-2/)
2. "At the simplest level it contains information that maps character codes to shapes (called glyphs) that represent these characters" - CSS Fonts Module Level 3, W3C Recommendation: 1. Introduction [https://www.w3.org/TR/css-fonts-3/#introduction](https://www.w3.org/TR/css-fonts-3/#introduction)
3. "Various relationships may exist between character and glyph: a single glyph may correspond to a single character or to a number of characters, or multiple glyphs may result from a single character" - The Unicode Standard, Core Specification, Chapter 2 [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-2/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-2/)
4. "In displaying Unicode character data, one or more glyphs may be selected to depict a particular character. These glyphs are selected by a rendering engine during composition and layout processing" - Unicode Glossary: Glyph [https://www.unicode.org/glossary/#glyph](https://www.unicode.org/glossary/#glyph)
5. "Arabic letters are displayed with different glyphs, depending on their position in a word; the glyphs in Figure 2-2 show independent, final, initial, and medial forms" - The Unicode Standard, Core Specification, Chapter 2 [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-2/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-2/)
