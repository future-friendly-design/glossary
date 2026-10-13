---
term: Shaping engine
slug: shaping-engine
aliases:
  - shaper
  - HarfBuzz
level: intermediate
depth: core
summary: A shaping engine is the software that works out which shapes a font should draw for a piece of text, and where each shape goes.
related:
  - text-shaping
  - gsub
  - gpos
  - opentype
  - complex-text-layout
status: voice-passed
version_added: 0.1
updated: 2026-10-13
contributors:
  - sam-gordashko
further_reading:
  - title: Why do I need a shaping engine? (HarfBuzz)
    url: https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html
    type: authority
license: CC-BY-4.0
tags:
  - shaping-layout
---

# Shaping engine

## Definition

A shaping engine is the software that works out which shapes a font should draw for a piece of text, and where each shape goes.<sup>1</sup>

That job is called [text shaping](text-shaping.md). You do not install a shaping engine or open it. It is already inside the operating system, the browser and the design tool you use, and it runs every time text is drawn.<sup>2</sup>

### Why it matters in design systems

When you type a word, the letters appear on screen at once. It looks as if nothing happens in between. Something does.

Text is stored as [characters](../text-in-software/character.md), and each character is saved as a number. A [font](font.md) is a file of drawn shapes, and each shape is called a [glyph](glyph.md).<sup>3</sup> Something has to get from the stored numbers to the right shapes, and then decide where each shape sits. That something is the shaping engine.

For a lot of English text the job looks easy: one character, one shape, each placed to the right of the last. For many [scripts](../../language-terms/writing-systems-and-scripts/script.md), the sets of symbols and rules that languages are written with, it takes real work. Here is the same job in three scripts:

| What is stored | What the reader should see | What the shaping engine did |
| -------------- | -------------------------- | --------------------------- |
| `c`, `a`, `t` | `cat` | Chose one shape for each character and placed them left to right. |
| The Arabic letters kāf, tāʾ, bāʾ: ك ت ب | كتب | Chose the joined form of each letter. An Arabic letter changes shape with its place in the word.<sup>4</sup> |
| The Devanagari letter क, then the vowel mark for "i" | कि | Drew the vowel mark to the left of the letter, although it is stored after it.<sup>5</sup> |

A shaping engine needs two things to do this: the text and a font. The font carries more than shapes. It also carries instructions, such as "when these two shapes meet, draw this joined shape instead" and "place this mark this far above that letter".<sup>6</sup> The font holds the instructions. The shaping engine follows them.

The shaping engine also brings rules of its own, a set for each script.<sup>7</sup> Moving the Devanagari vowel mark in the table above is one of those rules. It is not stored in the font at all. Microsoft's guidance for font makers says a font should not try to do that reordering, because the shaping engine does it.<sup>8</sup>

This is why the right font is necessary but not enough. A font with every shape and every instruction still depends on software that follows them. If a tool sets shapes side by side without shaping them, Arabic comes out as separate letters and the Devanagari vowel mark lands on the wrong side, in a font that could have done better. So when text looks wrong and the font is right, the shaping engine is the next place to look.

With the idea in place, here are the names you will meet. Most fonts today are in a format called [OpenType](../../design-terms/typography/opentype.md).<sup>9</sup> An OpenType font keeps its instructions in two parts: [GSUB](gsub.md) lists the shapes to swap, and [GPOS](gpos.md) lists where to place them. The shaping engines have names too. Uniscribe is used on Windows, and CoreText is used on macOS.<sup>10</sup> HarfBuzz is a third, used by the Firefox and Chromium browsers and by LibreOffice, a free office suite.<sup>11</sup> HarfBuzz's own list of users also includes design tools such as Figma and Adobe InDesign.<sup>12</sup>

<!-- NEEDS EXPERT REVIEW: the HarfBuzz manual names Uniscribe for Windows. Newer Windows software is widely reported to use DirectWrite instead; no primary source for that was fetched, so only Uniscribe is named here. Confirm which name to give readers. -->

Different tools can use different shaping engines. That is the reason to check your text in every tool your team uses, and not only in the browser.

Two notes on the word itself. This glossary uses "shaping" for both halves of the job: choosing the shapes and placing them. Microsoft's documents use it more narrowly, for choosing the shapes only, and list placing them as a separate step.<sup>13</sup> And shaping is not everything that happens to text on its way to the screen. HarfBuzz, for example, works on one line at a time and leaves the decision of where a line breaks to other software.<sup>14</sup>

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Character](../text-in-software/character.md) · [Complex text layout](complex-text-layout.md) · [Devanagari script](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Font](font.md) · [Glyph](glyph.md) · [GPOS](gpos.md) · [GSUB](gsub.md) · [Joining](../../language-terms/writing-systems-and-scripts/joining.md) · [Mark](../../language-terms/writing-systems-and-scripts/mark.md) · [Matra](../../language-terms/writing-systems-and-scripts/matra.md) · [OpenType](../../design-terms/typography/opentype.md) · [Reordering](reordering.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../../language-terms/writing-systems-and-scripts/script-rules.md) · [Text shaping](text-shaping.md) · [Text shaping & layout](../text-shaping-and-layout/)

### Further reading

* Foundations: [Why do I need a shaping engine? (HarfBuzz)](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)

### Sources

1. "Before a Unicode sequence can be rendered, the codepoints in the sequence must be mapped to the corresponding glyphs provided in the font, and those glyphs must be positioned correctly relative to each other" - Why do I need a shaping engine?, HarfBuzz Manual [https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)
2. "Text shaping is an integral part of preparing text for display" - Why do I need a shaping engine?, HarfBuzz Manual [https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)
3. "OpenType fonts contain a set of glyphs (that is, shapes to represent the letters, numbers, punctuation marks, and all other symbols)" - Why do I need a shaping engine?, HarfBuzz Manual [https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)
4. "To decide, you need to analyze the whole string and determine the appropriate glyph for each character based on its position" - Why do I need a shaping engine?, HarfBuzz Manual [https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)
5. "the software that renders the Indic scripts must be able to reorder elements in mapping from the logical (character) store to the presentational (glyph) rendering" - The Unicode Standard, Version 18.0, Chapter 12: South and Central Asia-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/)
6. "These shaping models depend on the font incorporating certain features as lookups in its GSUB and GPOS tables" - What is HarfBuzz?, HarfBuzz Manual [https://harfbuzz.github.io/what-is-harfbuzz.html](https://harfbuzz.github.io/what-is-harfbuzz.html)
7. "For many of the scripts supported in Unicode, these steps involve script-specific layout rules, including complex joining, reordering, and positioning behavior. Implementing these rules is the job of the shaping engine" - Why do I need a shaping engine?, HarfBuzz Manual [https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)
8. "OpenType fonts should not have substitutions that attempt to perform the re-ordering" - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
9. "There are several font formats that a program might encounter, each of which has a set of standard text-shaping rules. The dominant format is OpenType" - What is HarfBuzz?, HarfBuzz Manual [https://harfbuzz.github.io/what-is-harfbuzz.html](https://harfbuzz.github.io/what-is-harfbuzz.html)
10. "You could use Uniscribe if you are writing Windows software; you could use CoreText on macOS; or you could use HarfBuzz" - Why do I need a shaping engine?, HarfBuzz Manual [https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)
11. "HarfBuzz is used directly by text-handling libraries like Pango, as well as by the layout engines in Firefox, LibreOffice, and Chromium" - Why do I need a shaping engine?, HarfBuzz Manual [https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)
12. "HarfBuzz is used in Android, Chrome, ChromeOS, Firefox, Flutter, GNOME, GTK+, KDE, Qt, LibreOffice, OpenJDK, XeTeX, Adobe Photoshop, Illustrator, InDesign, Microsoft Edge, Amazon Kindle, PlayStation, Godot Engine, Unreal Engine, Figma, Canva, QuarkXPress, Scribus, smart TVs, car displays, and many other places" - HarfBuzz README, Users [https://github.com/harfbuzz/harfbuzz/blob/main/README.md](https://github.com/harfbuzz/harfbuzz/blob/main/README.md)
13. The Uniscribe shaping engine is described as working in stages, the first being "Shaping (substituting) glyphs with OTLS (OpenType Library Services)" and the second "Positioning glyphs with OTLS" - Developing OpenType Fonts for Standard Scripts (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/standard](https://learn.microsoft.com/en-us/typography/script-development/standard)
14. "HarfBuzz won't help you with line breaking, hyphenation, or justification. As mentioned above, HarfBuzz lays out the string along a single line of, notionally, infinite length" - What HarfBuzz doesn't do, HarfBuzz Manual [https://harfbuzz.github.io/what-harfbuzz-doesnt-do.html](https://harfbuzz.github.io/what-harfbuzz-doesnt-do.html)
