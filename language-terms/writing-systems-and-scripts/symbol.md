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

A symbol is an individual visual element that makes up a script. A mark is a kind of symbol that modifies or accompanies another symbol, changing how it is pronounced, what it means, or how it functions. The script rules define how symbols can be combined and determine the layout and direction for any language that uses the script in its writing system.

The term symbol is used to describe the visual elements of any script in general, because each script has its own name for them.

| Script type                               | What its symbols are called | Example |
| ----------------------------------------- | --------------------------- | :-----: |
| [Alphabet](../../terms/alphabet.md)       | letters                     |   A, b  |
| [Abjad](../../terms/abjad.md)             | consonant letters           |   ا, ب  |
| [Syllabary](../../terms/syllabary.md)     | syllable symbols            |   あ, い  |
| [Logographic](../../terms/logographic.md) | characters                  |   山, 川  |

It's important to understand how the concept of a symbol, regardless of its script specific name, maps to writing, reading, typography and computer programming terms.&#x20;

When a written language is read, the smallest symbol or combination of symbols that distinguishes one meaning from another is a grapheme. For example, `e` is one symbol and one grapheme. `é` is two symbols, a letter plus an accent mark, but still one grapheme.

Thinking about typography, the specific shape a font draws for a symbol is its glyph, and the same symbol can have many glyphs within the same font. The `e` and `é` you see on this page are glyphs.&#x20;

In computing, each symbol also maps to a character, the abstract unit of text software stores and counts: `e` is one character, while `é` is one character when stored precomposed or two when stored as a letter plus a combining accent mark.



### Why it matters in design systems

Picking a typeface feels like a brand decision you make once, but it cascades all the way down to the symbol. The [script](script.md) a language uses decides which [typefaces](../../terms/typeface.md) are even eligible: the ones with coverage for that script. The symbol is the next zoom in. Every symbol your content actually uses has to exist as a glyph in the font you picked ([font coverage](../../terms/font-coverage.md)), and it has to be drawn clearly enough for where it appears. A symbol with no glyph falls back to another font or renders as tofu. A symbol that is present but ambiguous, a lowercase "l" that reads as a "1", is technically covered and still wrong in the spot that matters. So coverage is necessary, not sufficient: the same typeface can be the right call for a headline and the wrong one for a dense form, because which symbols carry risk, and the size they are read at, change with the use case.

#### Example

The symbols of a script are whatever that script calls them: a letter such as "A" in the Latin alphabet, the syllable "あ" in [Hiragana](../../terms/hiragana.md), or the [Han character](../../terms/han-characters.md) "山". Add a vowel mark or an accent to one of those and you have a mark, the modifying kind of symbol, not a separate base element. In Unicode all of these writing-system symbols are encoded as letters (category L), not as "Symbols" in Unicode's own sense.<sup>1</sup>

### Common mistake

Assuming "symbol" is a precise technical category. In Unicode it is one, and it is not "any element of a script." Unicode's "Symbol" is a top-level General Category (abbreviated S) covering math symbols like +, currency symbols like $, modifier symbols, and other symbols such as © and emoji. It specifically excludes the elements that make up writing systems, which Unicode encodes as letters (category L, whose "Other Letter" value covers caseless writing such as Han characters and syllabary symbols) or as marks (category M). So the elements of a script are letters or marks in Unicode terms, not "Symbols." Treat "symbol" the everyday word and "Symbol" the Unicode category as two different things.<sup>1</sup>

### In practice

* **Match the typeface to the use case, symbol by symbol:** the same font can be perfect for a hero headline and a liability in a login form. Where text is read small (mobile UI, dense tables, captions), judge a font by how its actual symbols hold up at that size, not by how the specimen looks large.
* **Find the confusable symbols for the script you are in, do not assume Latin's:** in Latin, "1 l I i" and "0 O" are the pairs to keep distinct in passwords, codes, and IDs, but every script has its own near-twins, and in a script you do not read you cannot catch them by eye. Make it a question for the people who can: which symbols, alone or combined, are easy to mistake for each other here, and where would a misread cost the user? Unicode's confusables data is a cross-script starting point, and for a newly digitized script you may be among the first to map this, so test with fluent readers rather than guessing.<sup>2</sup>
* **Verify coverage before you commit, not at handoff:** confirm the chosen font actually draws every symbol the content needs, including [marks](mark.md) and less common letters, not just A to Z, or the text silently falls back to another font or shows tofu.

***



### Related terms and mentions

[Abjad](../../terms/abjad.md) · [Alphabet](../../terms/alphabet.md) · [Character](../../terms/character.md) · [Font coverage](../../terms/font-coverage.md) · [Glyph](../../terms/glyph.md) · [Grapheme](grapheme.md) · [Han characters](../../terms/han-characters.md) · [Hiragana](../../terms/hiragana.md) · [Logographic](../../terms/logographic.md) · [Mark](mark.md) · [Script](script.md) · [Script rules](script-rules.md) · [Syllabary](../../terms/syllabary.md) · [Typeface](../../terms/typeface.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [Unicode Standard Annex #44: General Category Values](https://www.unicode.org/reports/tr44/#General_Category_Values)

### Sources

1. Unicode's General Category "Symbol" (S) covers math, currency, modifier, and other symbols including emoji; the elements of writing systems are instead encoded as Letters (category L, whose Other\_Letter value covers Han characters and syllabary symbols) or Marks (category M) - Unicode Standard Annex #44: General Category Values [https://www.unicode.org/reports/tr44/#General\_Category\_Values](https://www.unicode.org/reports/tr44/#General_Category_Values)
2. Unicode maintains cross-script "confusables" data mapping characters that are visually confusable with one another, used to detect deceptive look-alikes - Unicode Technical Standard #39: Unicode Security Mechanisms [https://www.unicode.org/reports/tr39/](https://www.unicode.org/reports/tr39/)
