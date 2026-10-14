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

Each shape in a font is called a [glyph](glyph.md). The file also holds instructions for choosing and placing those shapes, usually in a format called [OpenType](opentype.md). What a font covers is its [font coverage](font-coverage.md), and when it falls short, software uses a [fallback font](fallback-font.md) or shows an empty box called [tofu](tofu.md). A font carries the design of a [typeface](typeface.md), and [text shaping](../text-shaping-and-layout/text-shaping.md) is the step that reads it.

Alongside the shapes, the file holds a list that says which shape belongs to which character, and software reads that list every time it shows a word.<sup>2</sup> A font is not the same thing as a typeface. The typeface is the design, the way the type looks, and the font is the file that delivers that design to a screen or a printer.<sup>3</sup>

### Why it matters in design systems

Choosing a font from a menu feels like choosing a look. What you are really choosing is a file, and a file only has what somebody put into it.

The first limit is the one that matters most in a product with more than one language. A font holds shapes for the characters its makers drew, and for no others. Drawing a [script](../../language-terms/writing-systems-and-scripts/script.md) well takes real knowledge of how that script is written and read, so extending a design to more scripts is difficult, skilled work,<sup>4</sup> and a font may hold shapes for one script only.<sup>5</sup> Here is what a font with only Latin shapes has to offer four short pieces of text:

| Text                                     | Script     | Does this font hold the shapes? |
| ---------------------------------------- | ---------- | ------------------------------- |
| Hello                                    | Latin      | Yes                             |
| selam: ሰላም ("peace", a greeting)         | Ethiopic   | No                              |
| marhaba: مرحبا ("hello")                 | Arabic     | No                              |
| Hindi: हिन्दी (the name of the language) | Devanagari | No                              |

Software works through text one character at a time. For each character it looks for a font that holds a shape, starting with the font the design asked for and moving down a list.<sup>6</sup> A font it finds further down that list is called a fallback font. If no font on the device holds a shape, the reader sees a placeholder, usually an empty box, which has the nickname tofu.<sup>7</sup> So the fonts a design system names decide which languages appear in the design you intended, which appear in something else, and which do not appear at all. The set of characters a font can be used for is called its font coverage.

No single font removes the problem. One font can hold at most 65,535 shapes,<sup>8</sup> and [Unicode](../text-in-software/unicode.md), the standard list of the world's characters, holds 172,808 of them as of version 18.0.<sup>9</sup> So one font cannot give every character a shape of its own. A product that has to show every script needs several fonts working together.

The second limit is style. An ordinary font file holds one style of a typeface: the regular, or the bold, or the italic, each in a file of its own.<sup>10</sup> Every one of those files has to be licensed, loaded and kept up to date. A [variable font](variable-font.md) is the exception, a single file that holds a range of styles. When a design asks for a style that has no file, such as a bold that was never loaded, a browser will often thicken the regular shapes instead, and the result is called [faux bold](faux-bold.md).<sup>11</sup>

In conversation, "font" and "typeface" are often used as if they meant the same thing.<sup>12</sup> The difference starts to matter when a decision is about files and not about looks. A licence is permission to use font software, so it is written about fonts.<sup>13</sup> A page downloads fonts. A [token](../../design-terms/design-token.md) that says "our brand type" names a typeface, and somebody still has to decide which font files that name stands for, in which weights and for which scripts. Code for the web uses different words again: CSS, the styling language of the web, calls the whole group a font family and one style inside it a font face.<sup>14</sup>

### Common mistake

Believing the screen. Text appears, so it looks as though the chosen font is working. But when the chosen font holds no shape for a character, software quietly takes the shape from another font, and because it does this character by character, a single line can end up shown in two or three fonts that were never designed to sit together. No error appears, because to the software nothing went wrong. The mismatch is easy to miss in a script you do not read and obvious to anyone who does. The question to ask is which font the text was shown in, not whether text appeared, and the inspection tools built into a web browser, called its developer tools, can answer it for any piece of text on a page.<sup>15</sup>

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
