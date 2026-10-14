---
term: Noto fonts
slug: noto-fonts
aliases:
  - Google Noto
  - Noto
level: intermediate
depth: core
summary: >-
  The Noto fonts are a collection of free fonts, directed by Google, that aims
  to provide a font for every script in Unicode.
related:
  - tofu
  - font
  - font-coverage
  - fallback-font
  - font-subsetting
  - unicode
status: voice-passed
version_added: 0.1
updated: 2026-10-13T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: SIL Open Font License
    url: https://openfontlicense.org/
    type: code
  - title: Noto Fonts (project site)
    url: https://notofonts.github.io/
    type: authority
license: CC-BY-4.0
tags:
  - reference-sources
---

# Noto fonts

## Definition

The Noto fonts are a collection of free fonts, directed by Google, that aims to provide a font for every script in Unicode.<sup>1</sup>

The Noto fonts are a collection of [fonts](font.md), the files that hold the shapes software uses to show text.<sup>2</sup>

A [script](../../language-terms/writing-systems-and-scripts/script.md) is a set of symbols used to write one or more languages, such as Arabic, Devanagari or Ethiopic. [Unicode](../text-in-software/unicode.md) is the standard that aims to give every character in every script its own number. Each font holds shapes for some of those characters.

### Why it matters in design systems

You have probably seen a row of empty boxes where words should be. It appears when text arrives in a script the font has no shapes for, and no font has shapes for every script. The boxes are nicknamed [tofu](tofu.md), and the Noto project says its name is short for "no tofu".<sup>3</sup>

So Noto is a natural place to look when a product has to display a script that its brand font does not cover.

The table gives the facts most often needed when choosing it. The counts are the project's own.

| Question                | Answer                                                                                                                                                                                           |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| What is in it?          | Fonts in several weights and widths, in styles with and without the small finishing strokes called serifs, and in other styles.<sup>4</sup>                                                      |
| How much does it cover? | More than 1,000 languages and over 150 writing systems.<sup>5</sup>                                                                                                                              |
| Who makes it?           | Google sets the direction and makes the final design decisions.<sup>6</sup>                                                                                                                      |
| What is the licence?    | The SIL Open Font License, version 1.1.<sup>7</sup> It lets you use, change and share the fonts, and include them inside a product you sell. The fonts may not be sold on their own.<sup>8</sup> |
| Is it one font file?    | No. There are more shapes in Noto than one font file can hold, so it is split into many families, such as Noto Sans Ethiopic for Ethiopic and Noto Sans Devanagari for Devanagari.<sup>9</sup>   |

That last row shapes how Noto is used. You do not add "Noto" to a product. You add the families for the scripts you support, and you list them in order after your main font, as [fallback fonts](fallback-font.md): for example `font-family: "Noto Sans", "Noto Sans Ethiopic", "Noto Sans Devanagari", sans-serif`. With that list, the Amharic word ሰላም ("selam", "peace") and the Hindi word हिन्दी ("Hindi") are each shown with the Noto family made for their script, and not with whatever font the device happens to have.

Noto has limits, and three of them matter when you choose it.

**Covering a script is not the same as being the typeface its readers prefer.** A [typeface](typeface.md) is the design of a set of shapes, and many scripts have long traditions with several styles of their own. Noto is designed to look consistent across scripts.<sup>10</sup> Readers of each language review the designs,<sup>11</sup> and Google makes the final decisions. A community may read more comfortably in a typeface made by its own designers, or may expect a style Noto does not offer. Ask people who read the script before you settle on it.

**The goal is not finished.** The project intends to support every script in Unicode, and that takes time.<sup>12</sup> Unicode keeps growing, and version 18.0 alone added three scripts,<sup>13</sup> so a newly added script may not have a Noto family yet. Check that the family for your script exists and holds the characters your languages need. This is its [font coverage](font-coverage.md).

**Having every character is not the same as showing the text correctly.** Many scripts need their shapes connected, stacked or moved, and that depends on instructions inside the font<sup>14</sup> and on the software following them.<sup>15</sup> The project keeps a public list of reported problems in its fonts.<sup>16</sup> Test a real word in each script you ship, and have someone who reads it check the result.

Because the collection is large, load only the families you need. If a family is cut down further to make its file smaller, which is called [font subsetting](font-subsetting.md), check that the cut did not remove characters your readers will type.

***

### Related terms and mentions

[Character](../text-in-software/character.md) · [Devanagari script](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Ethiopic script](../../language-terms/writing-systems-and-scripts/ethiopic-script.md) · [Fallback font](fallback-font.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Font subsetting](font-subsetting.md) · [Glyph](glyph.md) · [Language](../../language-terms/linguistics/language.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [SIL fonts](sil.md) · [Tofu](tofu.md) · [Typeface](typeface.md) · [Unicode](../text-in-software/unicode.md) · [Reference sources](../../terms/reference-sources.md) · [Font terms](./)

### Further reading

* Code & specs: [SIL Open Font License](https://openfontlicense.org/)
* Foundations: [Noto Fonts (project site)](https://notofonts.github.io/)

### Sources

1. "We do intend to support all scripts encoded by Unicode" - Noto fonts FAQ (the Noto project, archived repository) [https://github.com/notofonts/noto-fonts/blob/main/FAQ.md](https://github.com/notofonts/noto-fonts/blob/main/FAQ.md)
2. "Noto is a collection of high-quality fonts for all modern and ancient languages" - Homepage, Noto fonts documentation (the Noto project) [https://notofonts.github.io/noto-docs/website/homepage/](https://notofonts.github.io/noto-docs/website/homepage/)
3. "The name is also short for “no tofu,” as the project aims to eliminate the tofu-like blank rectangles that appear when no font is available for your text" - Homepage, Noto fonts documentation (the Noto project) [https://notofonts.github.io/noto-docs/website/homepage/](https://notofonts.github.io/noto-docs/website/homepage/)
4. "Noto is a collection of high-quality fonts with multiple weights and widths in sans, serif, mono, and other styles" - Noto dashboard, Noto Fonts project site [https://notofonts.github.io/](https://notofonts.github.io/)
5. "in more than 1,000 languages and over 150 writing systems" - Noto dashboard, Noto Fonts project site [https://notofonts.github.io/](https://notofonts.github.io/)
6. "Google provides the direction, planning, and final aesthetic decisions" - Noto fonts FAQ (the Noto project, archived repository) [https://github.com/notofonts/noto-fonts/blob/main/FAQ.md](https://github.com/notofonts/noto-fonts/blob/main/FAQ.md)
7. "This Font Software is licensed under the SIL Open Font License, Version 1.1" - fonts/LICENSE, notofonts.github.io repository [https://github.com/notofonts/notofonts.github.io/blob/main/fonts/LICENSE](https://github.com/notofonts/notofonts.github.io/blob/main/fonts/LICENSE)
8. "The OFL allows the licensed fonts to be used, studied, modified and redistributed freely as long as they are not sold by themselves. The fonts, including any derivative works, can be bundled, embedded, redistributed and/or sold with any software" - SIL Open Font License, official text, Preamble [https://openfontlicense.org/open-font-license-official-text/](https://openfontlicense.org/open-font-license-official-text/)
9. "A single file is not possible, because there are many more glyphs in Noto than can fit into a single font" - Noto fonts FAQ (the Noto project, archived repository) [https://github.com/notofonts/noto-fonts/blob/main/FAQ.md](https://github.com/notofonts/noto-fonts/blob/main/FAQ.md)
10. "Noto provides pan-language harmony, yet maintains authenticity" - Noto fonts FAQ (the Noto project, archived repository) [https://github.com/notofonts/noto-fonts/blob/main/FAQ.md](https://github.com/notofonts/noto-fonts/blob/main/FAQ.md)
11. "We then work with reviewers who are native readers of the languages" - Noto fonts FAQ (the Noto project, archived repository) [https://github.com/notofonts/noto-fonts/blob/main/FAQ.md](https://github.com/notofonts/noto-fonts/blob/main/FAQ.md)
12. "That takes time and the ordering is based on a complex changing mix of factors" - Noto fonts FAQ (the Noto project, archived repository) [https://github.com/notofonts/noto-fonts/blob/main/FAQ.md](https://github.com/notofonts/noto-fonts/blob/main/FAQ.md)
13. "The new additions include three new scripts" - Unicode 18.0.0, The Unicode Consortium [https://www.unicode.org/versions/Unicode18.0.0/](https://www.unicode.org/versions/Unicode18.0.0/)
14. "many other features are used to activate capabilities that are required for correct display of text; for example, required ligatures for Arabic script, or positioning of mark glyphs" - OpenType specification overview (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/overview](https://learn.microsoft.com/en-us/typography/opentype/spec/overview)
15. "In all cases, the text-processing client is responsible for applying, combining, and arbitrating among features and rendering the result" - Registered features, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/featuretags](https://learn.microsoft.com/en-us/typography/opentype/spec/featuretags)
16. "See the reported issues in Noto fonts and report new issues" - Noto dashboard, Noto Fonts project site [https://notofonts.github.io/](https://notofonts.github.io/)
