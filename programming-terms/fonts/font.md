---
term: Font
slug: font
aliases:
  - font file
level: foundational
depth: deep
summary: A font is a file that holds the shapes software uses to show text.
related:
  - typeface
  - glyph
  - font-coverage
  - fallback-font
  - font-weight
  - variable-font
status: voice-passed
version_added: 0.1
updated: 2026-10-13T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: '@font-face (MDN)'
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face
    type: code
  - title: Explore text properties (Figma Learn)
    url: >-
      https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties
    type: design-tool
  - title: Glossary (Monotype)
    url: https://support.monotype.com/en/articles/8949273-glossary
    type: authority
license: CC-BY-4.0
tags:
  - typography
---

# Font

## Definition

A font is a file that holds the shapes software uses to show text.<sup>1</sup>

Each [character](../text-in-software/character.md) of text has a unique shape defined by its [typeface](typeface.md), known as a [glyph](glyph.md). The font file also holds instructions used by the [shaping engine](../text-shaping-and-layout/shaping-engine.md) in programming processes for choosing and placing those shapes, usually in a format called [OpenType](opentype.md). Which specific glyphs a font covers is it known as [font coverage](font-coverage.md). When the text content needs to display a glyph not included in the font coverage, the system uses a [fallback font](fallback-font.md) or shows an empty box called [tofu](tofu.md).&#x20;

Alongside the shapes/glphs, the font file holds a list that says which glph belongs to which character of text, and software reads that list every time it shows a word.<sup>2</sup>&#x20;

### Why it matters in design systems

A font is not the same thing as a typeface. The typeface is the design of each glyph which provides the visual identity to written content in a design system. The font is the file is part of the system that delivers the typeface to a screen or a printer.<sup>3</sup>

It's important to remember that each languages has different requirements for the symbols and marks needed to support its writing system, even if they share the same script!&#x20;

Fun fact: a single font file can hold at most 65,535 shapes,<sup>8</sup> and [Unicode](../text-in-software/unicode.md), the standard list of the world's characters, holds 172,808 of them as of version 18.0.<sup>9</sup> \
\
So it's important to check that the font you are using supports all the languages required by your system, and you define fallback fonts as needed.&#x20;

Fonts are usually organized into clusters of files, where each set of glphs has a unique shape defined by a font weight (like bold or regular), or style (like italic). This is important to remember in design systems because each font file has to be loaded by the system and they are often licenced and priced independently.&#x20;

&#x20;A [variable font](variable-font.md) is the exception, a single file that holds a range of styles.&#x20;



### Common mistakes

When a design asks for a style that has no file, such as a bold font weight that was not included in the system, a browser will often thicken the regular shapes instead, and the result is called [faux bold](faux-bold.md).<sup>11</sup>

In conversation, "font" and "typeface" are often used as if they meant the same thing.<sup>12</sup> The difference starts to matter when a decision is about files and not about looks. A font licence is permission to use specific font files under specific conditions or use cases.<sup>13</sup>&#x20;



### In practice

* **Write down the files, not only the name.** A family name in a token or a brand guide does not say which files ship. List each font file your product loads: which [weight](font-weight.md), which style, which scripts. That list is what a licence covers, what a page downloads, and what a developer needs from you.
* **Choose a font for every script you ship.** List the scripts your languages are written in, pick a font for each one on purpose, and put them in order in the font list. If you do not choose, the device chooses for you. The [Noto fonts](noto-fonts.md) are one place to look for a script your main typeface was never drawn for.
* **Test real words with someone who reads the script.** Holding a shape for every character is necessary, and it is not enough. Many scripts also need instructions inside the font for combining, stacking or reordering shapes, and a font can hold the shapes and lack the instructions.<sup>16</sup> Following those instructions is called text shaping, and only a reader of the script can tell you whether it came out right.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Character](../text-in-software/character.md) · [Design token](../../design-terms/design-token.md) · [Devanagari script](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Ethiopic script](../../language-terms/writing-systems-and-scripts/ethiopic-script.md) · [Fallback font](fallback-font.md) · [Faux bold](faux-bold.md) · [Faux italic](faux-italic.md) · [Font coverage](font-coverage.md) · [Font subsetting](font-subsetting.md) · [Font weight](font-weight.md) · [Glyph](glyph.md) · [Language](../../language-terms/linguistics/language.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Noto fonts](noto-fonts.md) · [OpenType](opentype.md) · [Reordering](../text-shaping-and-layout/reordering.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Text shaping](../text-shaping-and-layout/text-shaping.md) · [Tofu](tofu.md) · [Typeface](typeface.md) · [Unicode](../text-in-software/unicode.md) · [Variable font](variable-font.md) · [Font terms](./)

### Further reading

* Code & specs: [@font-face (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face)
* Design tools: [Explore text properties (Figma Learn)](https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties)
* Foundations: [Glossary (Monotype)](https://support.monotype.com/en/articles/8949273-glossary)

### Sources

1. "A font provides a resource containing the visual representation of characters" - CSS Fonts Module Level 3, W3C Recommendation: 1. Introduction [https://www.w3.org/TR/css-fonts-3/#introduction](https://www.w3.org/TR/css-fonts-3/#introduction)
2. "At the simplest level it contains information that maps character codes to shapes (called glyphs) that represent these characters" - CSS Fonts Module Level 3, W3C Recommendation: 1. Introduction [https://www.w3.org/TR/css-fonts-3/#introduction](https://www.w3.org/TR/css-fonts-3/#introduction)
3. "font refers to the physical embodiment (whether it’s a case of metal pieces or a computer file) while typeface refers to the design (the way it looks)" - Glossary: Font, Monotype [https://support.monotype.com/en/articles/8949273-glossary](https://support.monotype.com/en/articles/8949273-glossary)
4. "Creating fonts that support multiple scripts is a difficult task; designers need to understand the cultural traditions surrounding the use of type in different scripts and come up with letterforms that somehow share a common theme" - CSS Fonts Module Level 3, W3C Recommendation: 2. Typography Background [https://www.w3.org/TR/css-fonts-3/#typography-background](https://www.w3.org/TR/css-fonts-3/#typography-background)
5. "This can be used to combine fonts that only contain glyphs for a single script (e.g. Latin, Greek, Cyrillic)" - CSS Fonts Module Level 3, W3C Recommendation: 4.6. Using character ranges to define composite fonts [https://www.w3.org/TR/css-fonts-3/#composite-fonts](https://www.w3.org/TR/css-fonts-3/#composite-fonts)
6. "For each character in the run a font family is chosen and a particular font face is selected containing a glyph for that character" - CSS Fonts Module Level 3, W3C Recommendation: 5. Font Matching Algorithm [https://www.w3.org/TR/css-fonts-3/#font-matching-algorithm](https://www.w3.org/TR/css-fonts-3/#font-matching-algorithm)
7. "If no appropriate font can be found, some form of "missing glyph" character will be rendered by the user agent" - CSS Fonts Module Level 3, W3C Recommendation: 2. Typography Background [https://www.w3.org/TR/css-fonts-3/#typography-background](https://www.w3.org/TR/css-fonts-3/#typography-background)
8. "uint16 numGlyphs The number of glyphs in the font" - maxp: Maximum Profile, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/maxp](https://learn.microsoft.com/en-us/typography/opentype/spec/maxp) (a uint16 is a 16-bit number, and the largest 16-bit number is 65,535)
9. "Unicode 18.0 adds 13,007 characters, for a total of 172,808 characters" - Unicode 18.0.0, The Unicode Consortium [https://www.unicode.org/versions/Unicode18.0.0/](https://www.unicode.org/versions/Unicode18.0.0/)
10. "rather than having a separate font file for every width, weight, or style" - Variable fonts, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS\_fonts/Variable\_fonts\_guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide)
11. "bold faces are often synthesized by user agents for faces that lack actual bold faces" - CSS Fonts Module Level 3, W3C Recommendation: 3.2. Font weight: the font-weight property [https://www.w3.org/TR/css-fonts-3/#font-weight-prop](https://www.w3.org/TR/css-fonts-3/#font-weight-prop)
12. "Although font and typeface are often used interchangeably" - Glossary: Font, Monotype [https://support.monotype.com/en/articles/8949273-glossary](https://support.monotype.com/en/articles/8949273-glossary)
13. "A font license (also known as EULA or end-user license agreement) is a legally binding document authorizing you to use font software under pre-defined conditions" - Glossary: Font license, Monotype [https://support.monotype.com/en/articles/8949273-glossary](https://support.monotype.com/en/articles/8949273-glossary)
14. "For a given range of text, CSS font properties are used to select a font family and a specific font face within that family to be used when rendering that text" - CSS Fonts Module Level 3, W3C Recommendation: 1. Introduction [https://www.w3.org/TR/css-fonts-3/#introduction](https://www.w3.org/TR/css-fonts-3/#introduction)
15. "The top section of the Font Editor shows the fonts used by the currently inspected element, grouped by font family" - Edit fonts, Firefox Source Docs (Mozilla) [https://firefox-source-docs.mozilla.org/devtools-user/page\_inspector/how\_to/edit\_fonts/index.html](https://firefox-source-docs.mozilla.org/devtools-user/page_inspector/how_to/edit_fonts/index.html)
16. "Some legacy fonts may include a given character in the character map but lack the shaping information" - CSS Fonts Module Level 3, W3C Recommendation: 5.2. Matching font styles [https://www.w3.org/TR/css-fonts-3/#font-style-matching](https://www.w3.org/TR/css-fonts-3/#font-style-matching)
