---
term: Font coverage
slug: font-coverage
aliases:
  - character coverage
  - language support
  - glyph coverage
level: intermediate
depth: deep
summary: Font coverage is the set of characters that a font file has glyphs for.
related:
  - fallback-font
  - font-subsetting
  - full-width
status: voice-passed
version_added: 0.1
updated: 2026-10-14
contributors:
  - sam-gordashko
further_reading:
  - title: CSS Fonts Module Level 3 (W3C)
    url: https://www.w3.org/TR/css-fonts-3/
    type: code
  - title: 'The Unicode Standard 18.0, chapter 5: Implementation Guidelines'
    url: https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-5/
    type: authority
license: CC-BY-4.0
tags:
  - typography
---

# Font coverage

## Definition

Font coverage is the set of characters that a font file has glyphs for.<sup>1</sup>

Font coverage is one of the things that describes a [font](font.md), the file that holds the shapes software uses to show text.<sup>2</sup>

When someone says a font "covers" or "supports" a [script](../../language-terms/writing-systems-and-scripts/script.md), this is the first thing they mean. The font has a [glyph](glyph.md) for every [character](../text-in-software/character.md) the script uses.

### Why it matters in design systems

You paste a person's name into a design and part of it turns into empty boxes. Or the name does appear, but in a style that is plainly not the one you chose. Both have the same cause. The text asked for characters your font holds no shape for, so the software either borrowed a shape from some other font, called a [fallback font](fallback-font.md), or found nothing at all and showed a placeholder box, called [tofu](tofu.md).<sup>3</sup>

Every font runs out somewhere, and that is a matter of arithmetic, not of effort. [Unicode](../text-in-software/unicode.md), the standard that aims to give every character in every writing system its own number, lists 172,808 characters in version 18.0.<sup>4</sup> A font in the [OpenType](opentype.md) format records how many shapes it holds in a slot of a fixed size.<sup>5</sup> The largest number that slot can hold is 65,535.<sup>6</sup> So one font cannot give every character a shape of its own. It has room for well under half of them. A product that has to show every script needs several fonts working together, and choosing which fonts is a design decision.

Holding the shapes is also only the first of three levels of coverage, and a font can pass one level and fail the next.

| Level           | The question to ask                                                                              | What you see when the answer is no                                                                                                    |
| --------------- | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------- |
| 1. Shapes       | Does the font hold a shape for every character in the text?                                      | Empty boxes, or some characters shown in a different font.<sup>7</sup>                                                                |
| 2. Instructions | Does the font also hold the instructions this script needs for combining and placing its shapes? | Every character appears, but the word is wrong. Symbols that should connect stand apart, or marks sit in the wrong place.<sup>8</sup> |
| 3. Software     | Does the software that picks and places the shapes read those instructions and follow them?      | The same wrong word. The font cannot fix this, because applying the instructions is the software's job.<sup>9</sup>                   |

Level 2 is the one people miss, because nothing looks missing. Many scripts do not simply set one shape after the next. In [Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md), the letters kāf ك, tāʾ ت and bāʾ ب each have a shape for standing alone, but in the word كتب they connect. In [Devanagari](../../language-terms/writing-systems-and-scripts/devanagari.md), the word हिन्दी ("Hindi") merges the consonants न and द into one combined shape, न्द. These behaviours are required for the text to be correct, and the instructions for them have to be in the font.<sup>10</sup> A font that holds every one of those characters but none of the instructions will show them side by side, unconnected and unmerged. All the characters show up, and the word is still wrong to anyone who can read it.

The instructions are kept in two lists inside the font. [GSUB](gsub.md) says which glyphs to swap for others, and [GPOS](gpos.md) says where to place them.<sup>11</sup> The work of following them is called [text shaping](../text-shaping-and-layout/text-shaping.md), the software that does it is a [shaping engine](../text-shaping-and-layout/shaping-engine.md), and writing that needs a lot of this work is said to need [complex text layout](../text-shaping-and-layout/complex-text-layout.md).

Coverage is counted in characters, so a label such as "supports Latin" does not tell you much either. Vietnamese is written in [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md), and the phrase Tiếng Việt ("Vietnamese") uses the vowels ế and ệ, which each carry two marks at once. Unicode lists the characters Vietnamese needs in four separate groups of Latin characters,<sup>12</sup> and a font drawn with English in mind may hold only the first. So check coverage against the languages you support, one by one, and not against the name of a script.

### Common mistake

Checking the font against your own text and stopping there. The labels, buttons and headings in a product are written by the team, so they are easy to check. The text that breaks coverage is written by other people: names, addresses, messages and search terms, in whatever script those people write. Nobody can list it in advance. A font that covers every word in the design file can still turn a customer's name into boxes on the first day, and the person who sees the boxes is the person whose name it is.

### In practice

* **Decide the scripts first, then choose the fonts.** List every script the product must display, including the text people type in. Name a font for each one on purpose, so the choice is not left to whatever the device happens to have. The [Noto fonts](noto-fonts.md) are a free collection built to fill these gaps.
* **Test with a real word and a real reader.** A grid of single characters only tests level 1. Type a real word in the script, and ask someone who reads it whether it looks right. That one check covers all three levels in the software you ran it in, so repeat it in each tool your text passes through.
* **Check each weight and style.** Bold and italic are usually separate font files, and they can cover less than the regular one. A family that mixes scripts will sometimes leave a script such as Arabic out of its italic.<sup>13</sup>
* **Check the file you ship, not the font you licensed.** Font files are often cut down to make them smaller, which is called [font subsetting](font-subsetting.md), and the cut can remove characters or instructions that the full font had.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Character](../text-in-software/character.md) · [Character encoding](../text-in-software/character-encoding.md) · [Complex text layout](../text-shaping-and-layout/complex-text-layout.md) · [Conjunct](../../language-terms/writing-systems-and-scripts/conjunct.md) · [Devanagari script](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Ethiopic script](../../language-terms/writing-systems-and-scripts/ethiopic-script.md) · [Fallback font](fallback-font.md) · [Font](font.md) · [Font subsetting](font-subsetting.md) · [Full-width](../text-in-software/full-width.md) · [Glyph](glyph.md) · [GPOS](gpos.md) · [GSUB](gsub.md) · [Joining](../../language-terms/writing-systems-and-scripts/joining.md) · [Language](../../language-terms/linguistics/language.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Mark](../../language-terms/writing-systems-and-scripts/mark.md) · [Noto fonts](noto-fonts.md) · [OpenType](opentype.md) · [Punctuation mark](../../language-terms/writing-systems-and-scripts/punctuation-mark.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Shaping engine](../text-shaping-and-layout/shaping-engine.md) · [Text shaping](../text-shaping-and-layout/text-shaping.md) · [Tofu](tofu.md) · [Unicode](../text-in-software/unicode.md) · [Writing system](../../language-terms/writing-systems-and-scripts/writing-system.md) · [Font terms](./)

### Further reading

* Code & specs: [CSS Fonts Module Level 3 (W3C)](https://www.w3.org/TR/css-fonts-3/)
* Foundations: [The Unicode Standard 18.0, chapter 5: Implementation Guidelines](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-5/)

### Sources

1. "The character map of a font defines the mapping of characters to glyphs for that font" - CSS Fonts Module Level 3, W3C Recommendation, section 2 [https://www.w3.org/TR/css-fonts-3/](https://www.w3.org/TR/css-fonts-3/)
2. "This allows for differences in available fonts across platforms and for differences in the range of characters supported by individual fonts" - CSS Fonts Module Level 3, W3C Recommendation, section 3.1 [https://www.w3.org/TR/css-fonts-3/#font-family-prop](https://www.w3.org/TR/css-fonts-3/#font-family-prop)
3. "If a document contains characters not supported by the character maps of the fonts contained in a font family list, a user agent may use a system font fallback procedure to locate an appropriate font that does. If no appropriate font can be found, some form of "missing glyph" character will be rendered by the user agent" - CSS Fonts Module Level 3, W3C Recommendation, section 2 [https://www.w3.org/TR/css-fonts-3/](https://www.w3.org/TR/css-fonts-3/)
4. "Unicode 18.0 adds 13,007 characters, for a total of 172,808 characters" - Unicode 18.0.0, The Unicode Consortium [https://www.unicode.org/versions/Unicode18.0.0/](https://www.unicode.org/versions/Unicode18.0.0/)
5. "uint16 numGlyphs The number of glyphs in the font" - maxp: Maximum Profile, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/maxp](https://learn.microsoft.com/en-us/typography/opentype/spec/maxp)
6. "uint16 16-bit unsigned integer" - OpenType Font File, Data types, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/otff](https://learn.microsoft.com/en-us/typography/opentype/spec/otff)
7. "character codes that do not correspond to any glyph in the font should be mapped to glyph index 0. The glyph at this location must be a special glyph representing a missing character, commonly known as .notdef" - cmap: Character to Glyph Index Mapping Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/cmap](https://learn.microsoft.com/en-us/typography/opentype/spec/cmap)
8. "Some legacy fonts may include a given character in the character map but lack the shaping information (e.g. OpenType layout tables or Graphite tables) necessary for correctly rendering text runs containing that character" - CSS Fonts Module Level 3, W3C Recommendation, section 5.2 [https://www.w3.org/TR/css-fonts-3/](https://www.w3.org/TR/css-fonts-3/)
9. "In all cases, the text-processing client is responsible for applying, combining, and arbitrating among features and rendering the result" - Registered features, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/featuretags](https://learn.microsoft.com/en-us/typography/opentype/spec/featuretags)
10. "many other features are used to activate capabilities that are required for correct display of text; for example, required ligatures for Arabic script, or positioning of mark glyphs" - OpenType specification overview (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/overview](https://learn.microsoft.com/en-us/typography/opentype/spec/overview)
11. "These shaping models depend on the font incorporating certain features as lookups in its GSUB and GPOS tables" - What is HarfBuzz?, HarfBuzz Manual [https://harfbuzz.github.io/what-is-harfbuzz.html](https://harfbuzz.github.io/what-is-harfbuzz.html)
12. "The Vietnamese vowels and other letters are found in the Basic Latin, Latin-1 Supplement, and Latin Extended-A blocks. Additional precomposed vowels and tone marks are found in the Latin Extended Additional block" - The Unicode Standard, Version 18.0, section 7.1 Latin [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-7/)
13. "Fonts that support a mixture of scripts will sometimes omit specific scripts such as Arabic from the set of glyphs supported in the italic face" - CSS Fonts Module Level 3, W3C Recommendation, section 3.4 [https://www.w3.org/TR/css-fonts-3/](https://www.w3.org/TR/css-fonts-3/)
