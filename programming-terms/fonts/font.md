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
updated: 2026-10-14
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

Each shape in a font is called a [glyph](glyph.md): it is the [typeface](typeface.md)'s design for a [character](../text-in-software/character.md) of text. The font file also holds instructions that a [shaping engine](../text-shaping-and-layout/shaping-engine.md) reads to choose and place those shapes, usually in a format called [OpenType](opentype.md). The set of characters a font has glyphs for is called its [font coverage](font-coverage.md). When the text needs a character the font has no glyph for, software uses a [fallback font](fallback-font.md) or shows an empty box called [tofu](tofu.md).&#x20;

Alongside the glyphs, the font file holds a list called the character map. [Unicode](../text-in-software/unicode.md) gives every character a number, and the character map says which glyph in the font goes with each number.<sup>2</sup> Software reads that list every time it shows a word.<sup>3</sup>&#x20;

### Why it matters in design systems

A font is not the same thing as a typeface. The typeface is the design of each glyph which provides the visual identity to written content in a design system. The font is the file that delivers the typeface to a screen or a printer.<sup>4</sup> A font licence is permission to use specific font files under specific conditions, so licences are written about fonts, not typefaces.<sup>5</sup>

It's important to remember that each language has different requirements for the symbols and marks its [writing system](../../language-terms/writing-systems-and-scripts/writing-system.md) needs, even when two languages share the same script! Vietnamese and English both use the Latin script, but Vietnamese also needs tone marks placed on top of other marks.<sup>6</sup>&#x20;

Fun fact: a single font file can hold at most 65,535 shapes,<sup>7</sup> and Unicode, the standard list of the world's characters, holds 172,808 of them as of version 18.0.<sup>8</sup>

So it's important to check that the font you are using supports all the languages required by your system, and you define fallback fonts as needed.&#x20;

Fonts are usually organized into families of files, where each file holds one [font weight](font-weight.md) (like regular or bold) or one style (like italic).<sup>9</sup> This is important to remember in design systems because each font file has to be loaded by the product and they are often licenced and priced independently.&#x20;

&#x20;A [variable font](variable-font.md) is the exception, a single file that holds a range of styles.&#x20;



### Common mistake

**Leaving out the bold or italic file.** When a design asks for a weight or style that the product never loaded, the browser fakes it: it thickens the regular shapes, which is called [faux bold](faux-bold.md),<sup>10</sup> or slants them, which is called [faux italic](faux-italic.md).<sup>11</sup> The fake looks rougher than the real font, and in some scripts it can make the text harder to read.<sup>12</sup> Load a file for every weight and style the design uses.

### In practice

* **Write down the files, not only the name.** A family name in a token or a brand guide does not say which files ship. List each font file your product loads: which weight, which style, which scripts. That list is what a licence covers, what a page downloads, and what a developer needs from you.
* **Choose a font for every script you ship.** List the scripts your languages are written in, pick a font for each one on purpose, and put them in order in the font list. If you do not choose, the device chooses for you. The [Noto fonts](noto-fonts.md) are one place to look for a script your main typeface was never drawn for.
* **Test real words with someone who reads the script.** Holding a shape for every character is necessary, and it is not enough. Many scripts also need instructions inside the font for combining, stacking or reordering shapes, and a font can hold the shapes and lack the instructions.<sup>13</sup> Following those instructions is called [text shaping](../text-shaping-and-layout/text-shaping.md), and only a reader of the script can tell you whether it came out right.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Character](../text-in-software/character.md) · [Design token](../../design-terms/design-token.md) · [Devanagari script](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Ethiopic script](../../language-terms/writing-systems-and-scripts/ethiopic-script.md) · [Fallback font](fallback-font.md) · [Faux bold](faux-bold.md) · [Faux italic](faux-italic.md) · [Font coverage](font-coverage.md) · [Font subsetting](font-subsetting.md) · [Font weight](font-weight.md) · [Glyph](glyph.md) · [Language](../../language-terms/linguistics/language.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Noto fonts](noto-fonts.md) · [OpenType](opentype.md) · [Reordering](../text-shaping-and-layout/reordering.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Shaping engine](../text-shaping-and-layout/shaping-engine.md) · [Text shaping](../text-shaping-and-layout/text-shaping.md) · [Tofu](tofu.md) · [Typeface](typeface.md) · [Unicode](../text-in-software/unicode.md) · [Variable font](variable-font.md) · [Writing system](../../language-terms/writing-systems-and-scripts/writing-system.md) · [Font terms](./)

### Further reading

* Code & specs: [@font-face (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face)
* Design tools: [Explore text properties (Figma Learn)](https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties)
* Foundations: [Glossary (Monotype)](https://support.monotype.com/en/articles/8949273-glossary)

### Sources

1. "A font provides a resource containing the visual representation of characters" - CSS Fonts Module Level 3, W3C Recommendation: 1. Introduction [https://www.w3.org/TR/css-fonts-3/#introduction](https://www.w3.org/TR/css-fonts-3/#introduction)
2. "This table defines the mapping of character codes to a default glyph index" - cmap: Character to Glyph Index Mapping Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/cmap](https://learn.microsoft.com/en-us/typography/opentype/spec/cmap)
3. "At the simplest level it contains information that maps character codes to shapes (called glyphs) that represent these characters" - CSS Fonts Module Level 3, W3C Recommendation: 1. Introduction [https://www.w3.org/TR/css-fonts-3/#introduction](https://www.w3.org/TR/css-fonts-3/#introduction)
4. "font refers to the physical embodiment (whether it’s a case of metal pieces or a computer file) while typeface refers to the design (the way it looks)" - Glossary: Font, Monotype [https://support.monotype.com/en/articles/8949273-glossary](https://support.monotype.com/en/articles/8949273-glossary)
5. "A font license (also known as EULA or end-user license agreement) is a legally binding document authorizing you to use font software under pre-defined conditions" - Glossary: Font license, Monotype [https://support.monotype.com/en/articles/8949273-glossary](https://support.monotype.com/en/articles/8949273-glossary)
6. "A mark-to-mark attachment positions one mark relative to another, as when positioning tone marks with respect to vowel diacritical marks in Vietnamese" - GPOS: Glyph Positioning Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gpos](https://learn.microsoft.com/en-us/typography/opentype/spec/gpos)
7. "uint16 numGlyphs The number of glyphs in the font" - maxp: Maximum Profile, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/maxp](https://learn.microsoft.com/en-us/typography/opentype/spec/maxp) (a uint16 is a 16-bit number, and the largest 16-bit number is 65,535)
8. "Unicode 18.0 adds 13,007 characters, for a total of 172,808 characters" - Unicode 18.0.0, The Unicode Consortium [https://www.unicode.org/versions/Unicode18.0.0/](https://www.unicode.org/versions/Unicode18.0.0/)
9. "A font resource without variation-related tables provides data for a single font face" - OpenType Font Variations Overview, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview](https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview)
10. "bold faces are often synthesized by user agents for faces that lack actual bold faces" - CSS Fonts Module Level 3, W3C Recommendation: 3.2. Font weight: the font-weight property [https://www.w3.org/TR/css-fonts-3/#font-weight-prop](https://www.w3.org/TR/css-fonts-3/#font-weight-prop)
11. "Synthetic font faces are a fallback strategy to provide an approximation to the requested font when a font family lacks a suitable face" - CSS Fonts Module Level 4, W3C Working Draft, 2.8 Controlling synthetic faces [https://www.w3.org/TR/css-fonts-4/#font-synthesis-intro](https://www.w3.org/TR/css-fonts-4/#font-synthesis-intro)
12. "Fonts used for Chinese, Japanese, Korean and other logographic scripts tend not to include these variants and synthesizing them might impede the legibility or change the meaning of the text" - font-synthesis, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/font-synthesis](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/font-synthesis)
13. "Some legacy fonts may include a given character in the character map but lack the shaping information" - CSS Fonts Module Level 3, W3C Recommendation: 5.2. Matching font styles [https://www.w3.org/TR/css-fonts-3/#font-style-matching](https://www.w3.org/TR/css-fonts-3/#font-style-matching)
