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

The name is short for Glyph Positioning. A [glyph](glyph.md) is a shape that a [font](font.md) draws for a character. GPOS belongs to [OpenType](../../design-terms/typography/opentype.md), the font file format most fonts use today.<sup>2</sup>

### Why it matters in design systems

Every letter you see on screen has been put in an exact spot. Often the rule is simple: draw a shape, move along by its width, draw the next one.<sup>3</sup>

That simple rule is not enough for a lot of writing:

| What needs placing | Example | Without it |
| ------------------ | ------- | ---------- |
| Two letters whose shapes leave a gap between them | `A` next to `V` | The pair looks too far apart. Closing the gap is called [kerning](../../design-terms/typography/kerning.md).<sup>4</sup> |
| A mark that belongs above or below a letter | The Arabic vowel marks in ba, bi, bu: بَ بِ بُ | The mark sits too high, too low, or on top of the letter.<sup>5</sup> |
| A mark that sits on another mark | Vietnamese, where a tone mark sits on top of a vowel mark | The two marks overlap.<sup>6</sup> |

<!-- NEEDS EXPERT REVIEW: the Vietnamese row has no rendered example because the repo holds no vetted Vietnamese sample. Add one confirmed by a Vietnamese reader. -->

The measurements for this are kept in the font, because they depend on the font's own shapes. The right spot for a mark depends on the height and width of the letter it belongs to.<sup>7</sup> GPOS is where the font keeps those measurements.

The font does not place anything. A font is a file, and the placing is done by the software that draws text, called a [shaping engine](shaping-engine.md). It reads GPOS and follows it. It does this after any shapes have been swapped for others, so that it is placing the final shapes.<sup>8</sup>

GPOS has a partner. A second part of the font, called [GSUB](gsub.md), lists which shapes to swap for other shapes. GSUB says which shapes. GPOS says where they go.

Kerning is a refinement. It is there for better typographic quality, and text without it can still be read.<sup>9</sup> Placing marks is different. In writing that uses many marks, a mark in the wrong place can make a word hard to read or change what it says. Microsoft's description of GPOS says such writing needs controlled placement of marks "for legibility and linguistic accuracy".<sup>10</sup>

The [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) needs its marks placed too. Microsoft's guidance for Latin, Cyrillic and Greek fonts lists mark placement among the things a font should handle.<sup>11</sup>

What this means for your work: GPOS is not something you set in a design tool. What you can do is choose fonts with care and test them. A font can contain a script's marks and still lack the measurements for placing them.<sup>12</sup> Then the marks appear, but they float, collide or pile up. So test a font with real words that carry marks, in each tool your team uses, and ask someone who reads the script whether the marks sit where they should.

One note on vocabulary. This glossary counts placing shapes as part of [text shaping](text-shaping.md), the step that turns stored characters into drawn shapes. Microsoft's documents use "shaping" for swapping shapes only, and name positioning as a separate step.<sup>13</sup>

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Character](../text-in-software/character.md) · [Diacritic](../../language-terms/writing-systems-and-scripts/diacritic.md) · [Font](font.md) · [Glyph](glyph.md) · [GSUB](gsub.md) · [Harakat](../../language-terms/writing-systems-and-scripts/harakat.md) · [Joining](../../language-terms/writing-systems-and-scripts/joining.md) · [Kerning](../../design-terms/typography/kerning.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Legibility](../../design-terms/typography/legibility.md) · [Mark](../../language-terms/writing-systems-and-scripts/mark.md) · [OpenType](../../design-terms/typography/opentype.md) · [OpenType features](../../design-terms/typography/opentype-features.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Shaping engine](shaping-engine.md) · [Text shaping](text-shaping.md) · [Tone mark](../../language-terms/writing-systems-and-scripts/tone-mark.md) · [Text shaping & layout](../text-shaping-and-layout/)

### Further reading

* Code & specs: [GPOS: Glyph Positioning Table (Microsoft)](https://learn.microsoft.com/en-us/typography/opentype/spec/gpos)
* Foundations: [Why do I need a shaping engine? (HarfBuzz)](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)

### Sources

1. "The Glyph Positioning table (GPOS) provides precise control over glyph placement for sophisticated text layout and rendering in each script and language system that a font supports" - GPOS: Glyph Positioning Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gpos](https://learn.microsoft.com/en-us/typography/opentype/spec/gpos)
2. "There are several font formats that a program might encounter, each of which has a set of standard text-shaping rules. The dominant format is OpenType" - What is HarfBuzz?, HarfBuzz Manual [https://harfbuzz.github.io/what-is-harfbuzz.html](https://harfbuzz.github.io/what-is-harfbuzz.html)
3. "For some writing systems (or scripts) and languages, the process is simple, requiring the shaper to do little more than advance the horizontal position forward by the correct amount for each successive glyph" - Shaping concepts, HarfBuzz Manual [https://harfbuzz.github.io/shaping-concepts.html](https://harfbuzz.github.io/shaping-concepts.html)
4. "A pair adjustment positions two glyphs with respect to one another. Kerning is an example of pair adjustment" - GPOS: Glyph Positioning Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gpos](https://learn.microsoft.com/en-us/typography/opentype/spec/gpos)
5. "A mark-to-base attachment positions combining marks with respect to base glyphs, as when positioning vowels, diacritical marks, or tone marks in Arabic, Hebrew, and Vietnamese" - GPOS: Glyph Positioning Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gpos](https://learn.microsoft.com/en-us/typography/opentype/spec/gpos)
6. "A mark-to-mark attachment positions one mark relative to another, as when positioning tone marks with respect to vowel diacritical marks in Vietnamese" - GPOS: Glyph Positioning Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gpos](https://learn.microsoft.com/en-us/typography/opentype/spec/gpos)
7. "exactly where you should draw the breve depends on the height and width of the preceding zhe glyph. To find the right position, you need to consult the table inside the font (the GPOS table) that contains positioning information" - Why do I need a shaping engine?, HarfBuzz Manual [https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)
8. "Using positioning information in the GPOS table and baseline offset information in the BASE table, the client then positions the glyphs" - Advanced typographic tables: OpenType Layout, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/ttochap1](https://learn.microsoft.com/en-us/typography/opentype/spec/ttochap1)
9. "Apply feature 'kern' to provide pair kerning between base glyphs requiring adjustment for better typographical quality" - Developing OpenType Fonts for Standard Scripts (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/standard](https://learn.microsoft.com/en-us/typography/script-development/standard)
10. "These writing systems require controlled placement of all marks in relation to one another for legibility and linguistic accuracy" - GPOS: Glyph Positioning Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gpos](https://learn.microsoft.com/en-us/typography/opentype/spec/gpos)
11. "Apply feature 'mark' to position diacritic glyphs to the base glyph" - Developing OpenType Fonts for Standard Scripts (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/standard](https://learn.microsoft.com/en-us/typography/script-development/standard)
12. "These shaping models depend on the font incorporating certain features as lookups in its GSUB and GPOS tables" - What is HarfBuzz?, HarfBuzz Manual [https://harfbuzz.github.io/what-is-harfbuzz.html](https://harfbuzz.github.io/what-is-harfbuzz.html)
13. The Uniscribe shaping engine is described as working in stages, the first being "Shaping (substituting) glyphs with OTLS (OpenType Library Services)" and the second "Positioning glyphs with OTLS" - Developing OpenType Fonts for Standard Scripts (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/standard](https://learn.microsoft.com/en-us/typography/script-development/standard)
