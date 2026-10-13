---
term: Text shaping
slug: text-shaping
aliases:
  - shaping
level: intermediate
depth: deep
summary: Text shaping is the step in which software works out which of a font's shapes to draw for a piece of text, and where each shape goes.
related:
  - shaping-engine
  - complex-text-layout
  - gsub
  - gpos
  - opentype
status: voice-passed
version_added: 0.1
updated: 2026-10-13
contributors:
  - sam-gordashko
further_reading:
  - title: Shaping Across Element Boundaries, CSS Text Module Level 3 (W3C)
    url: https://www.w3.org/TR/css-text-3/#boundary-shaping
    type: code
  - title: What is HarfBuzz? (HarfBuzz)
    url: https://harfbuzz.github.io/what-is-harfbuzz.html
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
  - shaping-layout
---

# Text shaping

## Definition

Text shaping is the step in which software works out which of a font's shapes to draw for a piece of text, and where each shape goes.<sup>1</sup>

Text in every script goes through this step before it is drawn.<sup>2</sup> Text shaping is the name of the job. The software that does the job is called a [shaping engine](shaping-engine.md).

### Why it matters in design systems

Text on a screen looks like a row of finished letters. It is not stored that way. Text is stored as [characters](../text-in-software/character.md), and each character is saved as a number. The shapes are kept somewhere else, in a [font](font.md), which is a file of drawn shapes. Each shape is called a [glyph](glyph.md).<sup>3</sup>

Shaping connects the two. It starts with the stored characters and a font. It ends with a list of glyphs and a position for each one.<sup>4</sup>

How much work that takes depends on the [script](../../language-terms/writing-systems-and-scripts/script.md), which is the set of symbols and rules a language is written with. For some scripts, shaping is little more than setting one glyph after another. For others there is a lot to work out.<sup>5</sup>

This glossary does not cover every script, so here are four to start with. Select a linked term to go to its glossary page.

| What is stored | What the reader should see | What shaping did |
| -------------- | -------------------------- | ---------------- |
| The Arabic letters kāf ك, tāʾ ت and bāʾ ب | كتب | Chose a form of each letter that connects to the letters beside it. This is called [joining](../../language-terms/writing-systems-and-scripts/joining.md).<sup>6</sup> |
| The Thai consonants ส, ว, ส and ด, with one vowel mark stored after ว and another after ด | สวัสดี | Placed each vowel mark above its consonant. A [mark](../../language-terms/writing-systems-and-scripts/mark.md) is a symbol that attaches to another symbol.<sup>7</sup> |
| Five Tibetan characters: the consonants ra, ga and ya, a vowel mark, then the consonant ད | རྒྱུད | Built one stack from the first three consonants, with ra on top, ga in the middle and ya below, and set the vowel mark under it. This is called [stacking](../../language-terms/writing-systems-and-scripts/stacking-script.md).<sup>8</sup> |
| The Devanagari consonant क, then the vowel mark for "i" | कि | Drew the vowel mark to the left of the consonant, although it is stored after it. This is called [reordering](reordering.md).<sup>9</sup> |

In all four rows the stored characters were already correct. Shaping changed three things: which glyphs were chosen, where they sit, and in the last row the order they are drawn in.

The instructions for this come from two places. Some are kept in the font, because they depend on that font's own shapes. A font holds a list of glyphs to swap for other glyphs, and a list of where to place them. Most fonts today are in a format called [OpenType](../../design-terms/typography/opentype.md).<sup>10</sup> In an OpenType font the list of swaps is called [GSUB](gsub.md), and the list of places is called [GPOS](gpos.md).<sup>11</sup> When a swap turns several glyphs into one merged glyph, the result is a [ligature](ligature.md).

The other instructions are kept in the software. Reordering is one of them. The shaping engine does it by rules of its own, and it is not stored in the font.<sup>12</sup>

Three names in this part of the glossary are easy to mix up:

* **Text shaping** is the job.
* **A shaping engine** is the software that does the job. There is more than one. HarfBuzz is a shaping engine, and so is CoreText on macOS.<sup>13</sup>
* **[Complex text layout](complex-text-layout.md)** is a name for the same job in the scripts where it has the most to do, such as the four in the table.<sup>14</sup> It is not a separate step.

Shaping is also not the only thing that happens to text on its way to the screen. Mixing right-to-left and left-to-right writing in one line, which is called [bidirectional text](../../language-terms/writing-systems-and-scripts/bidirectional-text.md), is a different job. So is deciding where a line ends. A shaping engine such as HarfBuzz leaves both to other software.<sup>15</sup>

For your work, this means correct text needs three things at once: the right characters, a font with the glyphs and instructions the script needs, and software that shapes. A design system can name the font. It cannot supply the shaping, because that belongs to each tool the text passes through. So treat a script as supported only in the tools where a person who reads it has seen it shaped correctly.

### Common mistake

Working out how much room text needs by counting its characters. A character limit on a form field, or a rule that cuts a label off after 20 characters, assumes that each character becomes one glyph of about the same width. Shaping does not work that way. Two characters can become one glyph, and one character can need different glyphs in different places.<sup>16</sup> The Thai word in the table shows the effect: it is stored as six characters and fills the width of four, because its two vowel marks sit above their consonants. Size a component from real words, shaped in the real font, in each language you support.

### In practice

* **Say which language the text is in.** Shaping uses the script and the language of the text, as well as the characters and the font.<sup>17</sup> Languages that share a script can expect different shapes for the same letter. Some Cyrillic letters, for example, are drawn one way in Russian and another way in Bulgarian.<sup>18</sup> On the web, the browser reads the language marked on the content and uses it when it chooses and places glyphs.<sup>19</sup> So mark the language of every piece of text with a [language tag](language-tag.md), a short code that names the language, including a single name or quotation in another language.
* **Keep a word in one piece.** A shaping engine such as HarfBuzz works on one stretch of text at a time. A change of font, font size, script, language or direction inside the text starts a new stretch, and each stretch is shaped by itself.<sup>20</sup> The rules for web pages add that shaping must be broken where spacing or a border has been put between two symbols.<sup>21</sup> So if you highlight part of a word, or give its first letter a style of its own, symbols that should connect across that point can come apart. Try the design on a word in a script that joins before you approve it.
* **Be careful with effects that handle letters one at a time.** An animation that brings letters in one by one, or a heading set along a curve from separate letters, hands the software each letter alone. But the right form of an Arabic letter can only be chosen by looking at the letters around it.<sup>22</sup> Without its neighbours, each letter is drawn in the form it has when it stands alone, and the word falls apart. In these scripts, apply the effect to whole words.

<!-- NEEDS EXPERT REVIEW: the last bullet infers that a letter handed to the software alone is drawn in its standalone form. The cited source says the form is chosen from the whole string; it does not describe letter-by-letter effects. Confirm in a real animation or text-on-a-path tool with an Arabic word. -->

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Bidirectional text](../../language-terms/writing-systems-and-scripts/bidirectional-text.md) · [Character](../text-in-software/character.md) · [Complex text layout](complex-text-layout.md) · [Cyrillic script](../../language-terms/writing-systems-and-scripts/cyrillic.md) · [Devanagari script](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Font](font.md) · [Glyph](glyph.md) · [GPOS](gpos.md) · [GSUB](gsub.md) · [Joining](../../language-terms/writing-systems-and-scripts/joining.md) · [Language](../../language-terms/linguistics/language.md) · [Language tag](language-tag.md) · [Left-to-right](../../language-terms/writing-systems-and-scripts/left-to-right.md) · [Ligature](ligature.md) · [Mark](../../language-terms/writing-systems-and-scripts/mark.md) · [OpenType](../../design-terms/typography/opentype.md) · [Reordering](reordering.md) · [Right-to-left](../../language-terms/writing-systems-and-scripts/right-to-left.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../../language-terms/writing-systems-and-scripts/script-rules.md) · [Shaping engine](shaping-engine.md) · [Stacking script](../../language-terms/writing-systems-and-scripts/stacking-script.md) · [Symbol](../../language-terms/writing-systems-and-scripts/symbol.md) · [Thai script](../../language-terms/writing-systems-and-scripts/thai-script.md) · [Tibetan script](../../language-terms/writing-systems-and-scripts/tibetan-script.md) · [Unicode](../text-in-software/unicode.md) · [Vertical text](../../terms/vertical-text.md) · [Text shaping & layout](../text-shaping-and-layout/)

### Further reading

* Code & specs: [Shaping Across Element Boundaries, CSS Text Module Level 3 (W3C)](https://www.w3.org/TR/css-text-3/#boundary-shaping)
* Foundations: [What is HarfBuzz? (HarfBuzz)](https://harfbuzz.github.io/what-is-harfbuzz.html)

### Sources

1. "Text shaping is the process of transforming a sequence of Unicode codepoints that represent individual characters (letters, diacritics, tone marks, numbers, symbols, etc.) into the orthographically and linguistically correct two-dimensional layout of glyph shapes taken from a specified font" - Shaping concepts, HarfBuzz Manual [https://harfbuzz.github.io/shaping-concepts.html](https://harfbuzz.github.io/shaping-concepts.html)
2. "correctly shaping a text run in any script may still involve Unicode normalization, ligature substitutions, mark positioning, kerning, and applying other font features" - Script-specific shaping, HarfBuzz Manual [https://harfbuzz.github.io/script-specific-shaping.html](https://harfbuzz.github.io/script-specific-shaping.html)
3. "Glyphs represent the shapes that characters can have when they are rendered or displayed" and "A repertoire of glyphs makes up a font" - The Unicode Standard, Version 18.0, Chapter 2: General Structure [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-2/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-2/)
4. "HarfBuzz selects and positions the corresponding glyphs from the font" - What is HarfBuzz?, HarfBuzz Manual [https://harfbuzz.github.io/what-is-harfbuzz.html](https://harfbuzz.github.io/what-is-harfbuzz.html)
5. "For some writing systems (or scripts) and languages, the process is simple, requiring the shaper to do little more than advance the horizontal position forward by the correct amount for each successive glyph. But, for other scripts (often unceremoniously called complex scripts), any combination of several shaping operations may be required" - Shaping concepts, HarfBuzz Manual [https://harfbuzz.github.io/shaping-concepts.html](https://harfbuzz.github.io/shaping-concepts.html)
6. "Inside a font, there will be separate glyphs for the initial, medial, final, and isolated forms of each letter" - Why do I need a shaping engine?, HarfBuzz Manual [https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)
7. "the Thai combining marks above (U+0E31, U+0E34..U+0E37, U+0E47..U+0E4E) should be displayed outward from the base character they modify, in the order in which they appear in the text" - The Unicode Standard, Version 18.0, Chapter 16: Southeast Asia-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-16/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-16/)
8. "The base consonant can be written singly or it can have other consonants added above or below it to make a vertically "stacked" letter" - The Unicode Standard, Version 18.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-13/)
9. "Because Devanagari and other Indic scripts have some dependent vowels that must be depicted to the left side of their consonant letter, the software that renders the Indic scripts must be able to reorder elements in mapping from the logical (character) store to the presentational (glyph) rendering" - The Unicode Standard, Version 18.0, Chapter 12: South and Central Asia-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-12/)
10. "There are several font formats that a program might encounter, each of which has a set of standard text-shaping rules. The dominant format is OpenType" - What is HarfBuzz?, HarfBuzz Manual [https://harfbuzz.github.io/what-is-harfbuzz.html](https://harfbuzz.github.io/what-is-harfbuzz.html)
11. GSUB "Contains information about glyph substitutions" and GPOS "Contains information about X and Y positioning of glyphs" - Advanced typographic tables: OpenType Layout, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/ttochap1](https://learn.microsoft.com/en-us/typography/opentype/spec/ttochap1)
12. "OpenType fonts should not have substitutions that attempt to perform the re-ordering" - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
13. "You could use Uniscribe if you are writing Windows software; you could use CoreText on macOS; or you could use HarfBuzz" - Why do I need a shaping engine?, HarfBuzz Manual [https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)
14. "In many scripts, transforming the input sequence into the final layout often requires some combination of operations", such as "context-dependent substitutions, context-dependent mark positioning, glyph-to-glyph joining, glyph reordering, or glyph stacking" - Script-specific shaping, HarfBuzz Manual [https://harfbuzz.github.io/script-specific-shaping.html](https://harfbuzz.github.io/script-specific-shaping.html)
15. "HarfBuzz won't help you with bidirectionality" and "HarfBuzz won't help you with line breaking, hyphenation, or justification" - What HarfBuzz doesn't do, HarfBuzz Manual [https://harfbuzz.github.io/what-harfbuzz-doesnt-do.html](https://harfbuzz.github.io/what-harfbuzz-doesnt-do.html)
16. "glyphs and characters do not strictly correspond one-to-one. For example, a user might type two characters, which might be better represented with a single ligature glyph. Conversely, the same character might take different forms at the beginning, middle, or end of a word" - Advanced typographic tables: OpenType Layout, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/ttochap1](https://learn.microsoft.com/en-us/typography/opentype/spec/ttochap1)
17. "The shaping process is dependent on the input string, the active font, the script (or writing system) that the string is in, and the language that the string is in" - What is HarfBuzz?, HarfBuzz Manual [https://harfbuzz.github.io/what-is-harfbuzz.html](https://harfbuzz.github.io/what-is-harfbuzz.html)
18. "Many languages share a common script, but the shape of certain letters can vary across those languages. For example, certain Cyrillic letters have different shapes in Russian text than in Bulgarian" - CSS Fonts Module Level 3, section 6.2 (W3C) [https://www.w3.org/TR/css-fonts-3/#language-specific-support](https://www.w3.org/TR/css-fonts-3/#language-specific-support)
19. "user agents are required to infer the OpenType language system from the content language and use that when selecting and positioning glyphs using an OpenType font" - CSS Fonts Module Level 3, section 6.2 (W3C) [https://www.w3.org/TR/css-fonts-3/#language-specific-support](https://www.w3.org/TR/css-fonts-3/#language-specific-support)
20. "if you change the font, font size, script, language, or direction within your string, then you will need to shape each run independently and output them independently" - What HarfBuzz doesn't do, HarfBuzz Manual [https://harfbuzz.github.io/what-harfbuzz-doesnt-do.html](https://harfbuzz.github.io/what-harfbuzz-doesnt-do.html)
21. "Text shaping must be broken at inline box boundaries when any of the following are true", the first of which is "Any of margin/border/padding separating the two typographic character units in the inline axis is non-zero" - CSS Text Module Level 3, section 7.3 (W3C) [https://www.w3.org/TR/css-text-3/#boundary-shaping](https://www.w3.org/TR/css-text-3/#boundary-shaping)
22. "To decide, you need to analyze the whole string and determine the appropriate glyph for each character based on its position" - Why do I need a shaping engine?, HarfBuzz Manual [https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)
