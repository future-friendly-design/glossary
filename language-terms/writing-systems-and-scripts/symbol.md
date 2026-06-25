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

In a design system the symbol of a script is rarely where you make a decision, it matters because it's a shared reference point for language support across linguistics, typography, and computer programming. While these disciplines are all related to a design system, they are unique, and often use the same terms to mean different things, which can get pretty confusing!&#x20;

The goal is to understand how the concept of a symbol, regardless of its script-specific name, maps to related terms across linguistics, typography, and computer programming, so you can make user-friendly design decisions specific to the language you are working on.&#x20;

From a linguistics perspective, the [symbol](symbol.md) sits inside a larger structure: a [script](script.md) is the set of symbols a language is written with, and that script is one part of the language's [writing system](writing-system.md).

When a written language is read, the smallest symbol, or combination of symbols, that distinguishes one meaning from another is a [grapheme](../linguistics/grapheme.md). For example, `e` is one symbol and one grapheme; `é` is two symbols, a letter plus an accent mark, but still one grapheme.

When a written language is to be printed or shown on a screen, typography refers to the specific shape a [font](../../terms/font.md) draws for a symbol as a [glyph](../../terms/glyph.md). For example, the `e` and `é` you see on this page are glyphs. The same symbol in the same font can have more than one glyph. For example `e`, _`e`_, **`e`**, _**`e`**_, are the same symbol represented as four different glyphs. &#x20;

In computer programming, there is a universal coding standard called Unicode. What this glossary calls a symbol, Unicode refers to as a [character](../../terms/character.md). Each character is given a unique ID number called a code point. They reserve the term `symbol` for math symbols like `+`, currency symbols like `$`, modifier symbols, and other symbols such as `©` and emoji `🔠`.<sup>1</sup>

In design systems, the designers and developers working on software, websites, and other user interfaces use `character` as the abstract unit used to measure a single piece of text. For example, if a form had a limit of how much text could be entered into the input, both `e` and `é` would be measured as one character of the allowed text.&#x20;

_In case you missed it, `character` is also the name for the symbols within a logographic script._

### Common mistake

A common mistake is assuming that all languages that have the same script in their writing system use the same symbols for the same purpose. It's important to look at the [orthography](orthography.md) of each language alongside the symbols. \
\
For example, English and French both use the Latin script. However, the English orthography requires speech wrapped in the curly quote symbol, `“like this”`, while French requires guillemets with a space sitting inside each one, `« like this »`.<sup>2</sup>



Another common mistake is assuming that a symbol means the same thing in every discipline. A designer names a hero image export `hero image (16:9)` in their design tool, where the colon is just an aspect ratio. They push the file to a shared repository and email a copy to the client, and both break. Why?

On the client's Windows computer the file will not open, because Windows forbids the `:` in filenames (it is the drive-letter separator, as in `C:`).<sup>3</sup>

The developer hits the same kind of break, because in code the `:`, `(`, `)`, and the spaces already mean something specific, so the computer reads them as instructions instead of as part of the name.

The colon never changed. What it meant changed in every system it crossed: an aspect ratio to the designer, a forbidden character to Windows, reserved syntax in code.



### In practice

* **Check the orthography, not just the script, before reusing symbols across languages:** two languages can share a script and still differ in which symbols they use and how, like English's curly quotes versus French's guillemets. Do not hardcode one language's choices; pull them from locale data. Unicode's [CLDR](../../terms/cldr.md) publishes per-language conventions such as quotation marks as machine-readable data, and the internationalization libraries built on it apply the right symbol for the language automatically.<sup>4</sup>
* **When the rules are not lookup-able, capture them, because you may be the source:** for an under-resourced or newly digitized language, the conventions often are not in any library yet; they live with the people who read and write it. Get them from fluent readers, write them into your specs and tokens next to the symbols, and contribute them upstream so the next team can find them. CLDR's [Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and brand-new locales, which is how "I know the rule but it is not online" becomes part of the commons.<sup>5</sup>
* **Keep machine-facing names to a safe character set:** name tokens, files, components, and assets with plain ASCII (letters, digits, hyphens, underscores) and leave emojis, accents, quotes, and slashes for human-readable content, so a name that works in your design tool does not break when it becomes a filename or a code identifier.<sup>3</sup>

***

### Related terms and mentions

[Abjad](../../terms/abjad.md) · [Alphabet](../../terms/alphabet.md) · [Character](../../terms/character.md) · [CLDR](../../terms/cldr.md) · [Font](../../terms/font.md) · [Font coverage](../../terms/font-coverage.md) · [Glyph](../../terms/glyph.md) · [Grapheme](../linguistics/grapheme.md) · [Han characters](../../terms/han-characters.md) · [Legibility](../linguistics/legibility.md) · [Logographic](../../terms/logographic.md) · [Mark](mark.md) · [Orthography](orthography.md) · [Readability](../linguistics/readability.md) · [Script](script.md) · [Script rules](script-rules.md) · [Syllabary](../../terms/syllabary.md) · [Typeface](../../terms/typeface.md) · [Typography](../../terms/typography.md) · [Unicode](../../terms/unicode.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [Unicode Standard Annex #44: General Category Values](https://www.unicode.org/reports/tr44/#General_Category_Values)

### Sources

1. Unicode's General Category "Symbol" (S) covers math, currency, modifier, and other symbols including emoji; the elements of writing systems are instead encoded as Letters (category L, whose Other\_Letter value covers Han characters and syllabary symbols) or Marks (category M) - Unicode Standard Annex #44: General Category Values [https://www.unicode.org/reports/tr44/#General\_Category\_Values](https://www.unicode.org/reports/tr44/#General_Category_Values)
2. French and English mark quotations with different characters: French uses guillemets « » where English uses curly quotes - W3C: Quotation marks and how to mark them up [https://www.w3.org/Style/2013/quote-marks](https://www.w3.org/Style/2013/quote-marks)
3. Windows forbids the characters `< > : " / \ | ? *` in file and directory names and reserves device names such as CON and NUL - Microsoft: Naming Files, Paths, and Namespaces [https://learn.microsoft.com/en-us/windows/win32/fileio/naming-a-file](https://learn.microsoft.com/en-us/windows/win32/fileio/naming-a-file)
4. CLDR publishes locale-specific quotation marks as machine-readable delimiter data - Unicode Locale Data Markup Language (UTS #35) [https://www.unicode.org/reports/tr35/tr35-general.html#Delimiter_Elements](https://www.unicode.org/reports/tr35/tr35-general.html#Delimiter_Elements)
5. CLDR's Survey Tool lets the community review and submit locale data, including entirely new locales - Unicode CLDR Survey Tool [https://cldr.unicode.org/index/survey-tool](https://cldr.unicode.org/index/survey-tool)
