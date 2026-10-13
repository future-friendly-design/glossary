---
term: Font weight
slug: font-weight
aliases:
  - weight
level: foundational
depth: core
summary: Font weight is a measure of how thick the strokes of a typeface are, from very thin to very heavy.
tool_names:
  figma: Font weight or style
  css: font-weight
related:
  - faux-bold
  - variable-font
  - typeface
status: voice-passed
version_added: 0.1
updated: 2026-10-13
contributors:
  - sam-gordashko
further_reading:
  - title: font-weight (MDN)
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight
    type: code
  - title: Explore text properties (Figma Learn)
    url: https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties
    type: design-tool
license: CC-BY-4.0
tags:
  - typography
---

# Font weight

## Definition

Font weight is a measure of how thick the strokes of a typeface are, from very thin to very heavy.<sup>1</sup>

Regular and bold are two weights. A [typeface](typeface.md) may come in nine of them, or two, or only one.

### Why it matters in design systems

Bold text looks darker than the text around it, and that difference is weight. Design systems use it all the time, because a change of weight is the simplest way to show that one piece of text matters more than another.

In software, weight is written as a number. The usual scale runs from 100 to 900 in steps of 100, and each step is at least as dark as the one before it.<sup>2</sup> Regular sits at 400, where a family may call it Regular, Book or Roman, and bold sits at 700.<sup>3</sup> These are the names that usually go with the numbers:<sup>4</sup>

| Number | Common name |
| ------ | ----------- |
| 100 | Thin |
| 200 | Extra Light, or Ultra Light |
| 300 | Light |
| 400 | Normal, or Regular |
| 500 | Medium |
| 600 | Semi Bold, or Demi Bold |
| 700 | Bold |
| 800 | Extra Bold, or Ultra Bold |
| 900 | Black, or Heavy |

The names are habits, not rules, and the match between a name and a number is only rough. The scale is also relative: inside one family a bigger number never looks lighter,<sup>5</sup> but nothing promises that 500 in one family is as dark as 500 in another.

A weight is not a setting that software can apply to any text. It belongs to a [font](../../programming-terms/text-for-digital-products-and-the-web/font.md), the file that holds the shapes software draws text with, and each font file records the weight of the shapes it holds.<sup>6</sup> A weight is available only when a file with that weight has been loaded.

When a design asks for a weight that has no file, software does not stop. It uses a nearby weight.<sup>7</sup> In a browser the rule has a direction. A request above 500 looks at heavier files first, so semibold (600) in a family that has only regular and bold comes out bold.<sup>8</sup> A request for 500 tries 400 first, so medium comes out regular.<sup>9</sup> And when a family has no bold at all, a browser will often make one by thickening the regular shapes, which is called [faux bold](../../programming-terms/text-for-digital-products-and-the-web/faux-bold.md).<sup>10</sup>

This is where products in more than one [script](../../language-terms/writing-systems-and-scripts/script.md) run into trouble. Software chooses a font for each character,<sup>11</sup> so text in each script is usually drawn from a different font, and each of those fonts comes in its own set of weights. Families with only a few weights are common.<sup>12</sup> A weight scale designed around a family with nine weights can land, in the next script over, on a font that has two.

<!-- NEEDS EXPERT REVIEW: the brief asserts that many typefaces for non-Latin scripts ship in fewer weights than Latin families. No primary source read for this pass states that as a comparison between scripts; the body only claims that few-weight families are common (CSS Fonts 3) and that each font in a stack has its own weights. Strengthen only with a source. -->

Here are four weight [tokens](../design-token.md) meeting two fonts in the same product, in a browser:

| Token | Number asked for | Font with 400, 500, 600 and 700 | Font with 400 and 700 only |
| ----- | ---------------- | ------------------------------- | -------------------------- |
| regular | 400 | 400 | 400 |
| medium | 500 | 500 | 400, the same as regular |
| semibold | 600 | 600 | 700, the same as bold |
| bold | 700 | 700 | 700 |

Four levels of emphasis in one script have become two in the other, and nobody chose that.

A [variable font](variable-font.md) works differently, because one file holds a range of weights and any number inside the range can be used, not only the hundreds.<sup>13</sup>

For a design system this means three habits. Store weight tokens as numbers, because the names change from family to family. Your font list is the ordered list of fonts your product names. For every font on it, in every script, write down which weights really exist. Then decide on purpose what medium and semibold should become where they do not exist. If a faked bold is not acceptable, say so in code: CSS, the code that styles web pages, has a property called `font-synthesis` that tells a browser whether it may make one.<sup>14</sup>

### Also called

Figma: Font weight or style · CSS: `font-weight`

***

### Related terms and mentions

[Character](../../programming-terms/text-in-software/character.md) · [Design token](../design-token.md) · [Fallback font](../../programming-terms/text-for-digital-products-and-the-web/fallback-font.md) · [Faux bold](../../programming-terms/text-for-digital-products-and-the-web/faux-bold.md) · [Font](../../programming-terms/text-for-digital-products-and-the-web/font.md) · [Glyph](../../programming-terms/text-for-digital-products-and-the-web/glyph.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Typeface](typeface.md) · [Variable font](variable-font.md) · [Fonts](../fonts/)

### Further reading

* Code & specs: [font-weight (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight)
* Design tools: [Explore text properties (Figma Learn)](https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties)

### Sources

1. "specifies the weight of glyphs in the font, their degree of blackness or stroke thickness" - CSS Fonts Module Level 3, W3C Recommendation: 3.2. Font weight: the font-weight property [https://www.w3.org/TR/css-fonts-3/#font-weight-prop](https://www.w3.org/TR/css-fonts-3/#font-weight-prop)
2. "These values form an ordered sequence, where each number indicates a weight that is at least as dark as its predecessor" - CSS Fonts Module Level 3, W3C Recommendation: 3.2. Font weight: the font-weight property [https://www.w3.org/TR/css-fonts-3/#font-weight-prop](https://www.w3.org/TR/css-fonts-3/#font-weight-prop)
3. "400 roughly corresponds with a face that would be labeled as Regular, Book, Roman and 700 roughly matches a face that would be labeled as Bold" - CSS Fonts Module Level 3, W3C Recommendation: 3.2. Font weight: the font-weight property [https://www.w3.org/TR/css-fonts-3/#font-weight-prop](https://www.w3.org/TR/css-fonts-3/#font-weight-prop)
4. "These roughly correspond to the commonly used weight names below: 100 - Thin 200 - Extra Light (Ultra Light) 300 - Light 400 - Normal 500 - Medium 600 - Semi Bold (Demi Bold) 700 - Bold 800 - Extra Bold (Ultra Bold) 900 - Black (Heavy)" - CSS Fonts Module Level 3, W3C Recommendation: 3.2. Font weight: the font-weight property [https://www.w3.org/TR/css-fonts-3/#font-weight-prop](https://www.w3.org/TR/css-fonts-3/#font-weight-prop)
5. "The scale is relative, so a face with a larger weight value must never appear lighter" - CSS Fonts Module Level 3, W3C Recommendation: 3.2. Font weight: the font-weight property [https://www.w3.org/TR/css-fonts-3/#font-weight-prop](https://www.w3.org/TR/css-fonts-3/#font-weight-prop)
6. "Indicates the visual weight (degree of blackness or thickness of strokes) of the characters in the font" - OS/2: OS/2 and Windows Metrics Table, usWeightClass, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/os2#usweightclass](https://learn.microsoft.com/en-us/typography/opentype/spec/os2#usweightclass)
7. "When a weight is specified for which no face exists, a face with a nearby weight is used" - CSS Fonts Module Level 3, W3C Recommendation: 3.2. Font weight: the font-weight property [https://www.w3.org/TR/css-fonts-3/#font-weight-prop](https://www.w3.org/TR/css-fonts-3/#font-weight-prop)
8. "If the desired weight is greater than 500, weights above the desired weight are checked in ascending order followed by weights below the desired weight in descending order until a match is found" - CSS Fonts Module Level 3, W3C Recommendation: 5.2. Matching font styles [https://www.w3.org/TR/css-fonts-3/#font-style-matching](https://www.w3.org/TR/css-fonts-3/#font-style-matching)
9. "If the desired weight is 500, 400 is checked first and then the rule for desired weights less than 400 is used" - CSS Fonts Module Level 3, W3C Recommendation: 5.2. Matching font styles [https://www.w3.org/TR/css-fonts-3/#font-style-matching](https://www.w3.org/TR/css-fonts-3/#font-style-matching)
10. "bold faces are often synthesized by user agents for faces that lack actual bold faces" - CSS Fonts Module Level 3, W3C Recommendation: 3.2. Font weight: the font-weight property [https://www.w3.org/TR/css-fonts-3/#font-weight-prop](https://www.w3.org/TR/css-fonts-3/#font-weight-prop)
11. "For each character in the run a font family is chosen and a particular font face is selected containing a glyph for that character" - CSS Fonts Module Level 3, W3C Recommendation: 5. Font Matching Algorithm [https://www.w3.org/TR/css-fonts-3/#font-matching-algorithm](https://www.w3.org/TR/css-fonts-3/#font-matching-algorithm)
12. "Quite often there are only a few weights available for a particular font family" - CSS Fonts Module Level 3, W3C Recommendation: 3.2. Font weight: the font-weight property [https://www.w3.org/TR/css-fonts-3/#font-weight-prop](https://www.w3.org/TR/css-fonts-3/#font-weight-prop)
13. "a user agent using a font which supports a range of weights should behave the same as if a font is present at each individual weight in the range" - CSS Fonts Module Level 4, W3C Working Draft: 2.2. Font weight: the font-weight property [https://www.w3.org/TR/css-fonts-4/#font-weight-prop](https://www.w3.org/TR/css-fonts-4/#font-weight-prop)
14. "This property controls whether user agents are allowed to synthesize bold or oblique font faces when a font family lacks bold or italic faces" - CSS Fonts Module Level 3, W3C Recommendation: 3.8. Controlling synthetic faces: the font-synthesis property [https://www.w3.org/TR/css-fonts-3/#font-synthesis-prop](https://www.w3.org/TR/css-fonts-3/#font-synthesis-prop)
