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

### Why it matters in design systems

In a design system the symbol of a script is rarely where you make a decision, it matters because it's a shared reference point for language support across liguistics, typography and computer programming. While these disciplines are all related to a design system, they are unique, and often use the same terms to mean different things, which can get pretty confusing!&#x20;

The goal is to understand how the concept of a symbol, regardless of its script specific name, maps to related terms across linguistics, typography, and computer programming, so you can make user friendly design decisions specific to the language you are working on.&#x20;

From a linguistics perspective, the [symbol](symbol.md) sits inside a larger structure: a [script](script.md) is the set of symbols a language is written with, and that script is one part of the language's [writing system](writing-system.md).

When a written language is read, the smallest symbol, or combination of symbols, that distinguishes one meaning from another is a [grapheme](../linguistics/grapheme.md). For example, `e` is one symbol and one grapheme; `é` is two symbols, a letter plus an accent mark, but still one grapheme.

When a written language is to be printed or shown on a screen, typography refers to the specific shape a [font](../../terms/font.md) draws for a symbol as a [glyph](../../terms/glyph.md),. For example, the  `e` and `é` you see on this page are glyphs. The same symbol in the same font can have more than one glyph. For example `e`, _`e`_, **`e`**, _**`e`**_, are the same symbol represented as four different glyphs. &#x20;

In computer programming, there is a universal coding standard called Unicode. What this glossary calls a symbol, Unicode refers to as a [character](../../terms/character.md). Each character is given a unique ID number called a code point. They reserve the term  `symbol` for math symbols like `+`, currency symbols like `$`, modifier symbols, and other symbols such as `©` and emoji `🔠`.

In design systems, the designers and developers working on software, websites, and other user interfaces use `character` as the the abstract unit used to measure single piece of text. For example, if a form had a limit of how much text could be entered into the input, both `e` and `é` would be measured as one character of the allowed text.&#x20;

_In case you missed it, `character` is also the name for the symbols within a logographic script._

### Common mistake

A common mistake is assuming that all languages that have the same script in their writing system use the same symbols for the same purpose. It's important to look at the [orthography](orthography.md) of each language along side the symbols. \
\
For example, English and French both use the Latin script. However, the English orthography requires speech wrapped in the curly quote symbol, `“like this”`, while French requires guillemets with a space sitting inside each one, `« like this »`. &#x20;



Another common mistake is assuming that all symbols mean the same thing across disciplines. &#x20;

For example, a designer names the hero image asset for a website project `hero image (16:9)` in their design tool. They export the image file and push it to a shared code repository for their developers to use and email a copy of the file to the client. Both the developer and the client are having issues with the file. Why?&#x20;

The designer using an Apple computer didn't realize the client was using a Windows operating system on their computer which forbids the use of some symbols `:` in file names so the image wouldn't open.&#x20;

The developer working in code experiences a breaking changing change because the `(` `:` and `)` symbols are reserved in their programming language for a specific purpose.&#x20;



### In practice

* **Verify coverage first, then legibility:** confirm the font draws every symbol the content needs, including marks and less common letters, since a missing one falls back to another font or shows tofu. Coverage is only table stakes, though; the real test is whether the symbols it does draw stay legible where they actually ship.
* **Get the confusable set from a credible source and a fluent reader, then test it in the smallest context:** name the symbols whose confusion would cost the user, in credential fields, codes, IDs, and money. For Latin that is pairs like "1 l I i" and "0 O"; for any other script, pull Unicode's [confusables data](https://www.unicode.org/Public/security/latest/confusables.txt) and ask someone who reads the script, because you cannot see the near-twins in a script you do not read, and for a newly digitized one you may be the first to map them. Then set those symbols in the real typeface at the real size, a 320px screen or a 14px field, and look.<sup>3</sup>
* **Use the failures to defend a scoped change:** when a glyph does not hold up you have usually inherited the font from brand or marketing, so bring the failing screens, not opinions. The fix is rarely "drop the brand font," it is a defensible, context-scoped choice, a different face for credential fields, a stylistic alternate, or a fallback, recorded in the design system so the next team does not relitigate it.

***

### Related terms and mentions

[Abjad](../../terms/abjad.md) · [Alphabet](../../terms/alphabet.md) · [Character](../../terms/character.md) · [Font](../../terms/font.md) · [Font coverage](../../terms/font-coverage.md) · [Glyph](../../terms/glyph.md) · [Grapheme](../linguistics/grapheme.md) · [Han characters](../../terms/han-characters.md) · [Legibility](../linguistics/legibility.md) · [Logographic](../../terms/logographic.md) · [Mark](mark.md) · [Orthography](orthography.md) · [Readability](../linguistics/readability.md) · [Script](script.md) · [Script rules](script-rules.md) · [Syllabary](../../terms/syllabary.md) · [Typeface](../../terms/typeface.md) · [Typography](../../terms/typography.md) · [Unicode](../../terms/unicode.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [Unicode Standard Annex #44: General Category Values](https://www.unicode.org/reports/tr44/#General_Category_Values)

### Sources

1. French and English mark quotations with different characters: French uses guillemets « » where English uses straight or curly quotes - W3C: Quotation marks and how to mark them up [https://www.w3.org/Style/2013/quote-marks](https://www.w3.org/Style/2013/quote-marks)
2. Unicode's General Category "Symbol" (S) covers math, currency, modifier, and other symbols including emoji; the elements of writing systems are instead encoded as Letters (category L, whose Other\_Letter value covers Han characters and syllabary symbols) or Marks (category M) - Unicode Standard Annex #44: General Category Values [https://www.unicode.org/reports/tr44/#General\_Category\_Values](https://www.unicode.org/reports/tr44/#General_Category_Values)
3. Unicode maintains cross-script "confusables" data mapping characters that are visually confusable with one another, used to detect deceptive look-alikes - Unicode Technical Standard #39: Unicode Security Mechanisms [https://www.unicode.org/reports/tr39/](https://www.unicode.org/reports/tr39/)
