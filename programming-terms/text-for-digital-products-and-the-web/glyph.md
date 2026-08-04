---
term: Glyph
slug: glyph
aliases: []
tags: [characters-encoding]
level: foundational
depth: core
summary: A glyph is the specific visual shape a font draws for a character.
related: [character, font, code-point, ligature]
status: voice-passed
version_added: 0.1
updated: 2026-08-04
contributors: [sam-gordashko]
further_reading:
  - title: "Glyph (Unicode Glossary)"
    url: https://www.unicode.org/glossary/#glyph
    type: authority
license: CC-BY-4.0
---

# Glyph

## Definition

A glyph is the specific visual shape a [font](font.md) draws for a [character](character.md).<sup>1</sup>

For example, the character `a` is one unit of text, but its glyph looks quite different in a serif typeface, one with small finishing strokes, than in a sans-serif, one without them.

### Why it matters in design systems

This is the line between what text is and what text looks like. The character is the abstract unit a system stores; the glyph is one font's drawing of it. Swap the font and every glyph on the page changes while the text itself stays identical, which is why a font change can never fix a spelling and a spelling change can never fix a rendering problem.

The mapping between the two is not one to one in either direction. Unicode is explicit that one or more glyphs may be selected to depict a single character, and that a rendering engine chooses them during layout.<sup>2</sup> Several characters can also collapse into one glyph, which is what a [ligature](ligature.md) is. In the Arabic script a single letter is drawn with a different glyph depending on which letters sit beside it, the behaviour covered under [joining](../../language-terms/writing-systems-and-scripts/joining.md), so one character may correspond to four or more glyphs in the same font.

For a design system, that has a practical consequence worth internalizing: counting characters tells you nothing about what will be drawn. Whether text renders correctly depends on whether the font contains the needed glyphs, which is [font coverage](font-coverage.md), and on whether the software selects and positions them properly, which is [text shaping](text-shaping.md). A font missing a glyph is the usual cause of the empty box known as [tofu](../../design-terms/typography/tofu.md). Both conditions have to hold, and neither is visible in the text itself, so both have to be tested by rendering real content in the real tools rather than inspected in a string.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Character](character.md) · [Code point](code-point.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Joining](../../language-terms/writing-systems-and-scripts/joining.md) · [Ligature](ligature.md) · [Text shaping](text-shaping.md) · [Tofu](../../design-terms/typography/tofu.md) · [Typeface](../../design-terms/typography/typeface.md) · [Unicode](unicode.md) · [Fonts](../../design-terms/fonts/)

### Further reading

* Foundations: [Glyph (Unicode Glossary)](https://www.unicode.org/glossary/#glyph)

### Sources

1. "An abstract form that represents one or more glyph images" - Unicode Glossary: Glyph, sense 1 [https://www.unicode.org/glossary/#glyph](https://www.unicode.org/glossary/#glyph)
2. "In displaying Unicode character data, one or more glyphs may be selected to depict a particular character. These glyphs are selected by a rendering engine during composition and layout processing" - Unicode Glossary: Glyph [https://www.unicode.org/glossary/#glyph](https://www.unicode.org/glossary/#glyph)
