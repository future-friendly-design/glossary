---
term: GPOS
slug: gpos
aliases:
  - Glyph Positioning table
level: advanced
depth: core
summary: GPOS is the part of a font file that tells software where to place each shape in relation to the shapes around it.
related:
  - gsub
  - opentype
  - opentype-features
  - text-shaping
status: voice-passed
version_added: 0.1
updated: 2026-10-13
contributors:
  - sam-gordashko
further_reading:
  - title: "GPOS: Glyph Positioning Table (Microsoft)"
    url: https://learn.microsoft.com/en-us/typography/opentype/spec/gpos
    type: code
  - title: Why do I need a shaping engine? (HarfBuzz)
    url: https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html
    type: authority
license: CC-BY-4.0
tags:
  - shaping-layout
---

# GPOS

## Definition

GPOS is the part of a font file that tells software where to place each shape in relation to the shapes around it.<sup>1</sup>

GPOS is one of the tools of [text shaping](text-shaping.md), the step in which software works out which of a font's shapes to draw for a piece of text, and where each shape goes: software called a [shaping engine](shaping-engine.md) reads it from the font.<sup>2</sup>

The name is short for Glyph Positioning. A [glyph](glyph.md) is one of the drawn shapes stored in a [font](font.md). GPOS belongs to [OpenType](../../design-terms/typography/opentype.md), the most widely used font format.<sup>3</sup>

### Why it matters in design systems

Every symbol you see on screen has been put in an exact spot. Often the rule is simple: draw a glyph, move along by its width, draw the next one.<sup>4</sup>

That simple rule is not enough for a lot of writing:

| What needs placing | Example | Without it |
| ------------------ | ------- | ---------- |
| Two letters whose shapes leave a gap between them | `A` next to `V` | The pair looks too far apart. Closing the gap is called [kerning](../../design-terms/typography/kerning.md).<sup>5</sup> |
| A mark that belongs above or below a symbol | The Arabic vowel marks in `بَ` (ba), `بِ` (bi), `بُ` (bu) | The mark sits too high, too low, or on top of the symbol.<sup>6</sup> |
| A mark that sits on another mark | The Vietnamese ế in Tiếng Việt, where a [tone mark](../../language-terms/writing-systems-and-scripts/tone-mark.md), which shows the tone of the voice, sits on top of a mark that changes the vowel | In a font that builds ế from separate parts, the two marks overlap.<sup>7</sup> |

The measurements for this are kept in the font, because they depend on the font's own glyphs: the right spot for a mark depends on the height and width of the symbol it belongs to.<sup>8</sup> GPOS is where the font keeps those measurements. Kerning is the one exception. It can also be kept in an older part of the font file, called `kern`, so an older font with no GPOS can still kern, but it has nowhere to keep the measurements for marks.<sup>9</sup>

The font does not place anything. A font is a file, and the placing is done by the software that draws text, called a shaping engine, which reads GPOS and follows it. It does this after any glyphs have been swapped for others, so that it is placing the final glyphs.<sup>10</sup> Those swaps are listed in a second part of the font, called [GSUB](gsub.md). GSUB says which glyphs. GPOS says where they go.

Kerning is a refinement that gives better typographic quality.<sup>11</sup> Placing marks is different. In writing that uses many marks, a mark in the wrong place can make a word hard to read or change what it says, so that kind of writing needs its marks placed with control, both to be legible and to be correct in the language.<sup>12</sup>

The [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) needs its marks placed too. A font for Latin, Cyrillic or Greek is expected to place each accent on its base letter.<sup>13</sup>

GPOS is not something you set in a design tool. What you can do is choose fonts with care and test them, because all of the placing information has to come from the font itself.<sup>14</sup> A font can have glyphs for a script's marks and still lack the measurements for placing them, and then the marks appear, but they float, collide or pile up. So test a font with real words that carry marks, in each tool your team uses, and ask someone who reads the script whether the marks sit where they should.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Character](../text-in-software/character.md) · [Complex text layout](complex-text-layout.md) · [Diacritic](../../language-terms/writing-systems-and-scripts/diacritic.md) · [Font](font.md) · [Glyph](glyph.md) · [GSUB](gsub.md) · [Harakat](../../language-terms/writing-systems-and-scripts/harakat.md) · [Kerning](../../design-terms/typography/kerning.md) · [Language](../../language-terms/linguistics/language.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Legibility](../../design-terms/typography/legibility.md) · [Mark](../../language-terms/writing-systems-and-scripts/mark.md) · [OpenType](../../design-terms/typography/opentype.md) · [OpenType features](../../design-terms/typography/opentype-features.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Shaping engine](shaping-engine.md) · [Symbol](../../language-terms/writing-systems-and-scripts/symbol.md) · [Text shaping](text-shaping.md) · [Tone mark](../../language-terms/writing-systems-and-scripts/tone-mark.md) · [Text shaping & layout terms](../text-shaping-and-layout/)

### Further reading

* Code & specs: [GPOS: Glyph Positioning Table (Microsoft)](https://learn.microsoft.com/en-us/typography/opentype/spec/gpos)
* Foundations: [Why do I need a shaping engine? (HarfBuzz)](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)

### Sources

1. "The Glyph Positioning table (GPOS) provides precise control over glyph placement for sophisticated text layout and rendering in each script and language system that a font supports" - GPOS: Glyph Positioning Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gpos](https://learn.microsoft.com/en-us/typography/opentype/spec/gpos)
2. "Apply OpenType GPOS features to position glyphs or marks" - Developing OpenType Fonts for Devanagari Script (Microsoft), Shaping Engine [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
3. "There are several font formats that a program might encounter, each of which has a set of standard text-shaping rules. The dominant format is OpenType" - What is HarfBuzz?, HarfBuzz Manual [https://harfbuzz.github.io/what-is-harfbuzz.html](https://harfbuzz.github.io/what-is-harfbuzz.html)
4. "For some writing systems (or scripts) and languages, the process is simple, requiring the shaper to do little more than advance the horizontal position forward by the correct amount for each successive glyph" - Shaping concepts, HarfBuzz Manual [https://harfbuzz.github.io/shaping-concepts.html](https://harfbuzz.github.io/shaping-concepts.html)
5. "A pair adjustment positions two glyphs with respect to one another. Kerning is an example of pair adjustment" - GPOS: Glyph Positioning Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gpos](https://learn.microsoft.com/en-us/typography/opentype/spec/gpos)
6. "A mark-to-base attachment positions combining marks with respect to base glyphs, as when positioning vowels, diacritical marks, or tone marks in Arabic, Hebrew, and Vietnamese" - GPOS: Glyph Positioning Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gpos](https://learn.microsoft.com/en-us/typography/opentype/spec/gpos)
7. "A mark-to-mark attachment positions one mark relative to another, as when positioning tone marks with respect to vowel diacritical marks in Vietnamese" - GPOS: Glyph Positioning Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gpos](https://learn.microsoft.com/en-us/typography/opentype/spec/gpos)
8. "exactly where you should draw the breve depends on the height and width of the preceding zhe glyph. To find the right position, you need to consult the table inside the font (the GPOS table) that contains positioning information" - Why do I need a shaping engine?, HarfBuzz Manual [https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)
9. "The only positioning adjustment defined in other font tables is pair kerning, supported by the legacy 'kern' table" - GPOS: Glyph Positioning Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gpos](https://learn.microsoft.com/en-us/typography/opentype/spec/gpos)
10. "Using positioning information in the GPOS table and baseline offset information in the BASE table, the client then positions the glyphs" - Advanced typographic tables: OpenType Layout, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/ttochap1](https://learn.microsoft.com/en-us/typography/opentype/spec/ttochap1)
11. "Apply feature 'kern' to provide pair kerning between base glyphs requiring adjustment for better typographical quality" - Developing OpenType Fonts for Standard Scripts (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/standard](https://learn.microsoft.com/en-us/typography/script-development/standard)
12. "These writing systems require controlled placement of all marks in relation to one another for legibility and linguistic accuracy" - GPOS: Glyph Positioning Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gpos](https://learn.microsoft.com/en-us/typography/opentype/spec/gpos)
13. "Apply feature 'mark' to position diacritic glyphs to the base glyph" - Developing OpenType Fonts for Standard Scripts (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/standard](https://learn.microsoft.com/en-us/typography/script-development/standard)
14. "All the information controlling the substitution and relative positioning of glyphs during glyph processing is contained within the font itself" - Windows glyph processing for OpenType fonts, part 1 (Microsoft) [https://learn.microsoft.com/en-us/typography/develop/processing-part1](https://learn.microsoft.com/en-us/typography/develop/processing-part1)
