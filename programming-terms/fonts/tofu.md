---
term: Tofu
slug: tofu
aliases:
  - .notdef glyph
  - missing glyph box
level: foundational
depth: core
summary: >-
  Tofu is the nickname for the empty box that appears in place of a character
  when no font available to the software holds a shape for it.
related:
  - glyph
  - font
  - font-coverage
status: voice-passed
version_added: 0.1
updated: 2026-10-13T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: 'OpenType recommendations: Glyph 0, the .notdef glyph (Microsoft)'
    url: >-
      https://learn.microsoft.com/en-us/typography/opentype/spec/recom#glyph-0-the-notdef-glyph
    type: code
  - title: 'The Unicode Standard 18.0, chapter 5: Implementation Guidelines'
    url: https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-5/
    type: authority
license: CC-BY-4.0
tags:
  - characters-encoding
---

# Tofu

## Definition

Tofu is the nickname for the empty box that appears in place of a character when no font available to the software holds a shape for it.<sup>1</sup>

Tofu is what you see when every [font](font.md) available, the files that hold the shapes software uses to show text, falls short.<sup>2</sup>

For example, the Amharic greeting ሰላም ("selam", "peace") is written with three characters of [Ethiopic script](../../language-terms/writing-systems-and-scripts/ethiopic-script.md). On a device with no font for Ethiopic, the same word looks like this: □□□.

### Why it matters in design systems

A row of small empty rectangles where words should be is easy to dismiss as a glitch. For the person reading, it is their name, their message or their language that has been replaced by boxes, and they cannot read any of it.

Each box stands for one real character. A font is a file of shapes, called [glyphs](glyph.md), and it only has shapes for the characters its makers drew. The software received the character correctly and then could not find a font with a shape for it.<sup>3</sup> So the text itself is not damaged. Nothing needs to be typed again, and the same text will read correctly anywhere a suitable font is present.

The box is put there on purpose. A font keeps one special shape to show when a character is missing, which font makers call `.notdef`,<sup>4</sup> and the recommended drawing for it is an empty rectangle, or a rectangle with a question mark or an X inside.<sup>5</sup> Some software shows the character's number in its place.<sup>6</sup> A visible box is far better than the alternative: if nothing were shown, a reader would see what looks like a space and never learn that something is missing.<sup>7</sup>

Tofu is the last step of a longer search. Before showing a box, a web browser tries the font you chose, then any other fonts you listed, called [fallback fonts](fallback-font.md), then the fonts on the device.<sup>8</sup> A box means all of them failed. This is why tofu is a matter of [font coverage](font-coverage.md), the set of characters a font has shapes for, and why the same page can show boxes on one device and readable text on another.

Tofu is often confused with a different failure that looks just as broken.

| What you see  | Example                  | What went wrong                                                                                                                                                          | What fixes it                                       |
| ------------- | ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------- |
| Empty boxes   | □□□                      | No available font has a shape for these characters. This is tofu.                                                                                                        | A font that covers the script.                      |
| Wrong letters | `Ã©` where `é` should be | The stored numbers were turned back into characters using the wrong list. This is a [character encoding](../text-in-software/character-encoding.md) failure.<sup>9</sup> | Reading the text with the encoding it was saved in. |

The word also gave a font collection its name. The [Noto fonts](noto-fonts.md) project says its name is short for "no tofu".<sup>10</sup>

When you see tofu in a product, treat it as a missing font and act on that. Find out which script the boxes belong to. Add a font for that script to the product's list of fonts on purpose, so the result does not depend on what each device has. And if the product used to show that text correctly, ask whether the font file was cut down to make it smaller, which is called [font subsetting](font-subsetting.md), because a cut can remove the very shapes that are now missing.

***

### Related terms and mentions

[Character](../text-in-software/character.md) · [Character encoding](../text-in-software/character-encoding.md) · [Ethiopic script](../../language-terms/writing-systems-and-scripts/ethiopic-script.md) · [Fallback font](fallback-font.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Font subsetting](font-subsetting.md) · [Glyph](glyph.md) · [Language](../../language-terms/linguistics/language.md) · [Noto fonts](noto-fonts.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Font terms](./)

### Further reading

* Code & specs: [OpenType recommendations: Glyph 0, the .notdef glyph (Microsoft)](https://learn.microsoft.com/en-us/typography/opentype/spec/recom#glyph-0-the-notdef-glyph)
* Foundations: [The Unicode Standard 18.0, chapter 5: Implementation Guidelines](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-5/)

### Sources

1. "tofu being the nickname for the blank boxes that are shown when a computer or site lacks font support for a particular character" - More than 800 languages in a single typeface: creating Noto for Google, Monotype case study [https://www.monotype.com/resources/case-studies/more-than-800-languages-in-a-single-typeface-creating-noto-for-google](https://www.monotype.com/resources/case-studies/more-than-800-languages-in-a-single-typeface-creating-noto-for-google)
2. "If a particular character cannot be displayed using any font, the user agent should indicate by some means that a character is not being displayed" - CSS Fonts Module Level 3, W3C Recommendation, section 5.2 [https://www.w3.org/TR/css-fonts-3/#font-style-matching](https://www.w3.org/TR/css-fonts-3/#font-style-matching)
3. "An implementation may receive a code point to which a character is assigned in the Unicode Standard, but be unable to render it, because it lacks a font for the code point or is otherwise incapable of rendering it appropriately" - The Unicode Standard, Version 18.0, section 5.3 Unknown and Missing Characters [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-5/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-5/)
4. "character codes that do not correspond to any glyph in the font should be mapped to glyph index 0. The glyph at this location must be a special glyph representing a missing character, commonly known as .notdef" - cmap: Character to Glyph Index Mapping Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/cmap](https://learn.microsoft.com/en-us/typography/opentype/spec/cmap)
5. "It is recommended that the shape of the .notdef glyph be either an empty rectangle, a rectangle with a question mark inside of it, or a rectangle with an “X”" - OpenType font recommendations, Glyph 0: the .notdef glyph (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/recom#glyph-0-the-notdef-glyph](https://learn.microsoft.com/en-us/typography/opentype/spec/recom#glyph-0-the-notdef-glyph)
6. "any unrenderable character can only be indicated by some placeholder, such as displaying the hexadecimal value of the code point" - The Unicode Standard, Version 18.0, section 5.3 Unknown and Missing Characters [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-5/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-5/)
7. "This glyph should not be left without an outline as the user will only see what looks like a space if a glyph is missing and not be aware of the active font’s limitation" - OpenType font recommendations, Glyph 0: the .notdef glyph (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/recom#glyph-0-the-notdef-glyph](https://learn.microsoft.com/en-us/typography/opentype/spec/recom#glyph-0-the-notdef-glyph)
8. "If a document contains characters not supported by the character maps of the fonts contained in a font family list, a user agent may use a system font fallback procedure to locate an appropriate font that does. If no appropriate font can be found, some form of "missing glyph" character will be rendered by the user agent" - CSS Fonts Module Level 3, W3C Recommendation, section 2 [https://www.w3.org/TR/css-fonts-3/](https://www.w3.org/TR/css-fonts-3/)
9. "Garbled or incorrectly rendered or processed characters, generally caused by using the wrong character encoding to interpret the bytes in a string or file" - Internationalization Glossary, W3C Group Note: Mojibake [https://www.w3.org/TR/i18n-glossary/#dfn-mojibake](https://www.w3.org/TR/i18n-glossary/#dfn-mojibake)
10. "The name is also short for “no tofu,” as the project aims to eliminate the tofu-like blank rectangles that appear when no font is available for your text" - Homepage, Noto fonts documentation (the Noto project) [https://notofonts.github.io/noto-docs/website/homepage/](https://notofonts.github.io/noto-docs/website/homepage/)
