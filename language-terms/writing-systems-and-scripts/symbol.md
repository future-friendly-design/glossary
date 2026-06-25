---
term: Symbol
slug: symbol
aliases: []
level: foundational
depth: deep
summary: A symbol is an individual visual element that makes up a script.
related:
  - character
  - glyph
  - grapheme
  - mark
  - script
  - script-rules
status: voice-passed
version_added: 0.1
updated: 2026-06-23T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: 'Unicode Standard Annex #44: General Category Values'
    url: https://www.unicode.org/reports/tr44/#General_Category_Values
    type: code
license: CC-BY-4.0
tags:
  - characters-encoding
---

# Symbol

## Definition

A symbol is an individual visual element that makes up a [script](script.md). A [mark](mark.md) is a kind of symbol that modifies or accompanies another symbol, changing how it is pronounced, what it means, or how it functions. The [script rules](script-rules.md) define how symbols can be combined and determine the layout and direction for any language that uses the script in its [writing system](writing-system.md).

The term symbol is used to describe the visual elements of any script in general, because each script has its own name for them.

| Script type                               | What its symbols are called | Example |
| ----------------------------------------- | --------------------------- | :-----: |
| [Alphabet](../../terms/alphabet.md)       | letters                     |   A, b  |
| [Abjad](../../terms/abjad.md)             | consonant letters           |   ا, ب  |
| [Syllabary](../../terms/syllabary.md)     | syllable symbols            |   あ, い  |
| [Logographic](../../terms/logographic.md) | characters                  |   山, 川  |

It's important to understand how the concept of a symbol, regardless of its script specific name, maps to writing, reading, [typography](../../terms/typography.md) and computer programming terms.&#x20;

When a written language is read, the smallest symbol or combination of symbols that distinguishes one meaning from another is a [grapheme](grapheme.md). For example, `e` is one symbol and one grapheme. `é` is two symbols, a letter plus an accent mark, but still one grapheme.

Thinking about typography, the specific shape a [font](../../terms/font.md) draws for a symbol is its [glyph](../../terms/glyph.md), and the same symbol can have many glyphs within the same font. The `e` and `é` you see on this page are glyphs.&#x20;

In computing, each symbol also maps to a [character](../../terms/character.md), the abstract unit of text software stores and counts: `e` is one character, while `é` is one character when stored precomposed or two when stored as a letter plus a combining accent mark.

### Why it matters in design systems

A single symbol is three things at once, depending on who is handling it: a grapheme to the reader, a glyph to the font in your design tool, and a character to your code. A design system has to satisfy all three, and they fail independently, so choosing a font that includes the right symbols still isn't the whole answer when you support a language.

Zooming out, the script entry is the matching move: it asks whether you showed up with the right characters, layout, and direction for the whole writing system. The symbol is the opposite zoom. You go all the way in to the smallest visual unit and check the same symbols across every context the text actually appears in. Context is the variable this level adds. Because the symbol is the atom where the writing system becomes marks a person reads, every layer above it has to resolve right here: the script decides which [typefaces](../../terms/typeface.md) are even eligible, the ones whose [font coverage](../../terms/font-coverage.md) includes it (miss that and the symbol drops to a fallback or to tofu, the box that stands in for an absent glyph); the use context decides whether the glyphs that are there stay legible; and, more often than designers expect, the brand decides which font you actually get.

That last one is the catch. Text is functional and it is identity: because the glyph shapes carry the brand, the typeface is usually chosen by brand or marketing to look right on the surfaces it was made for, not by the design system to work everywhere. You rarely pick a font from scratch; you inherit a brand guideline and have to make it hold up across every context and script the product needs. A typeface built to make a brand unmistakable on a billboard can contain every symbol you need and still be the wrong tool in a 14px form field. Whether a reader can still tell one symbol from another there is [legibility](../../terms/legibility.md), and it is the symbol's job; arranging legible symbols into comfortable lines and paragraphs is [readability](../../terms/readability.md), the zoomed-out sibling that lives in spacing and layout.

And the glyph is only one of the three views. Stored as a character, the same symbol can take more than one form ("é" is one code point or two), so text that looks right can still break search, counting, and input. Read as a grapheme, what a person counts as "one character" is not what your code counts, so field limits and truncation surprise people. So the real question is never just "does the font include the symbols," it is "do these symbols, drawn in this font at this size and stored this way, hold up." Coverage is necessary, not sufficient.

### Example

English wraps speech in curly quotes, “like this”, while French uses guillemets, « like this », with a space sitting inside each one. Getting that right is a writing-system win, a matter of [orthography](orthography.md), and the script entry is where you catch it. But zoom all the way in: if a reader cannot tell the letters apart between those quotes on a 320px-wide screen, the small end of the range like an original iPhone SE, the typeface is still the wrong choice for that context. The quotes are correct and the line is still unreadable, because correctness and legibility are decided at different zoom levels.<sup>1</sup>

### Common mistake

Assuming "symbol" is a precise technical category. In [Unicode](../../terms/unicode.md), the standard that gives every character a unique number and sorts them into categories, it is one, and it is not "any element of a script." Unicode's "Symbol" is a top-level General Category (abbreviated S) covering math symbols like +, currency symbols like $, modifier symbols, and other symbols such as © and emoji. It specifically excludes the elements that make up writing systems, which Unicode encodes as letters (category L, whose "Other Letter" value covers caseless writing such as Han characters and syllabary symbols) or as marks (category M). So the elements of a script are letters or marks in Unicode terms, not "Symbols." Treat "symbol" the everyday word and "Symbol" the Unicode category as two different things.<sup>2</sup>

### In practice

* **Verify coverage first, then legibility:** confirm the font draws every symbol the content needs, including marks and less common letters, since a missing one falls back to another font or shows tofu. Coverage is only table stakes, though; the real test is whether the symbols it does draw stay legible where they actually ship.
* **Get the confusable set from a credible source and a fluent reader, then test it in the smallest context:** name the symbols whose confusion would cost the user, in credential fields, codes, IDs, and money. For Latin that is pairs like "1 l I i" and "0 O"; for any other script, pull Unicode's [confusables data](https://www.unicode.org/Public/security/latest/confusables.txt) and ask someone who reads the script, because you cannot see the near-twins in a script you do not read, and for a newly digitized one you may be the first to map them. Then set those symbols in the real typeface at the real size, a 320px screen or a 14px field, and look.<sup>3</sup>
* **Use the failures to defend a scoped change:** when a glyph does not hold up you have usually inherited the font from brand or marketing, so bring the failing screens, not opinions. The fix is rarely "drop the brand font," it is a defensible, context-scoped choice, a different face for credential fields, a stylistic alternate, or a fallback, recorded in the design system so the next team does not relitigate it.

***

### Related terms and mentions

[Abjad](../../terms/abjad.md) · [Alphabet](../../terms/alphabet.md) · [Character](../../terms/character.md) · [Font](../../terms/font.md) · [Font coverage](../../terms/font-coverage.md) · [Glyph](../../terms/glyph.md) · [Grapheme](grapheme.md) · [Han characters](../../terms/han-characters.md) · [Legibility](../../terms/legibility.md) · [Logographic](../../terms/logographic.md) · [Mark](mark.md) · [Orthography](orthography.md) · [Readability](../../terms/readability.md) · [Script](script.md) · [Script rules](script-rules.md) · [Syllabary](../../terms/syllabary.md) · [Typeface](../../terms/typeface.md) · [Typography](../../terms/typography.md) · [Unicode](../../terms/unicode.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [Unicode Standard Annex #44: General Category Values](https://www.unicode.org/reports/tr44/#General_Category_Values)

### Sources

1. French and English mark quotations with different characters: French uses guillemets « » where English uses straight or curly quotes - W3C: Quotation marks and how to mark them up [https://www.w3.org/Style/2013/quote-marks](https://www.w3.org/Style/2013/quote-marks)
2. Unicode's General Category "Symbol" (S) covers math, currency, modifier, and other symbols including emoji; the elements of writing systems are instead encoded as Letters (category L, whose Other\_Letter value covers Han characters and syllabary symbols) or Marks (category M) - Unicode Standard Annex #44: General Category Values [https://www.unicode.org/reports/tr44/#General\_Category\_Values](https://www.unicode.org/reports/tr44/#General_Category_Values)
3. Unicode maintains cross-script "confusables" data mapping characters that are visually confusable with one another, used to detect deceptive look-alikes - Unicode Technical Standard #39: Unicode Security Mechanisms [https://www.unicode.org/reports/tr39/](https://www.unicode.org/reports/tr39/)
</content>
