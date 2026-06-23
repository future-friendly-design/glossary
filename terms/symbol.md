---
term: Symbol
slug: symbol
aliases: [sign]
tags: [characters-encoding]
level: foundational
depth: deep
summary: A symbol is an individual sign that makes up a script or writing system.
related: [character, glyph, grapheme, mark, script, script-rules]
status: draft
version_added: 0.1
updated: 2026-06-23
contributors: [sam-gordashko]
further_reading:
  - title: "Unicode Standard Annex #44: General Category Values"
    url: https://www.unicode.org/reports/tr44/#General_Category_Values
    type: code
license: CC-BY-4.0
---

# Symbol

## Definition
A symbol is an individual sign that makes up a script or writing system.

## Why it matters
Symbol is the word most people reach for when naming the pieces of a script, and it is useful precisely because it does not assume a script type. The basic signs are called letters in an [alphabet](alphabet.md), consonant signs in an [abjad](abjad.md), syllable signs in a [syllabary](syllabary.md), and characters in a [logographic](logographic.md) script, and "symbol" is the one word that covers them all. It is the sign-level layer of a script's anatomy, alongside the marks added to those signs ([mark](mark.md)) and the [script rules](script-rules.md) that govern how they combine and lay out. Because it is the casual umbrella, it helps to know the more precise terms it blurs together: a [character](character.md) is the abstract unit of text, a [glyph](glyph.md) is the shape a font draws for it, and a [grapheme](grapheme.md) is the smallest unit a reader treats as one sign.

## Example
The signs of a script are its symbols, whatever that script calls them: a letter in the [Latin alphabet](alphabet.md), a syllable sign in [Hiragana](hiragana.md), or a [Han character](han-characters.md). A vowel sign or accent added to one of those signs is a [mark](mark.md), not a separate symbol.

## Common mistake
Assuming "symbol" is a precise technical category. In Unicode it is one, and it does not mean "any sign in a script." Unicode's "Symbol" is a specific top-level General Category (abbreviated S) covering math symbols like +, currency symbols like $, modifier symbols, and other symbols such as © and emoji. It specifically excludes the signs that make up writing systems, which Unicode encodes as letters (category L, a group that also covers non-alphabetic signs like Han characters and syllabary signs) or marks (category M). So the signs of a script are characters, not "Symbols" in the Unicode sense. Treat "symbol" the everyday word and "Symbol" the Unicode category as two different things.

## In practice
- **Pick the precise term when it matters:** [character](character.md) for the abstract unit (counting, encoding), [glyph](glyph.md) for the drawn shape (fonts, fallback), [grapheme](grapheme.md) for what a reader counts as one sign. Keep "symbol" for the casual umbrella.
- **Watch the Unicode category in code:** a regex class like `\p{S}` matches symbols (math, currency, emoji) but not letters or marks, so "match every sign in the text" needs `\p{L}`, `\p{M}`, and `\p{S}` together, not `\p{S}` alone.

## Related terms
[Character](character.md) · [Glyph](glyph.md) · [Grapheme](grapheme.md) · [Mark](mark.md) · [Script](script.md) · [Script rules](script-rules.md)

## Further reading
- Code & specs: [Unicode Standard Annex #44: General Category Values](https://www.unicode.org/reports/tr44/#General_Category_Values)
