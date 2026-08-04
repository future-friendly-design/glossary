---
term: Grapheme cluster
slug: grapheme-cluster
aliases: [user-perceived character]
tags: [characters-encoding]
level: intermediate
depth: deep
summary: A grapheme cluster is what a reader thinks of as one character, even if it is made of several code points.
related: [character, code-point, combining-mark, normalization]
status: voice-passed
version_added: 0.1
updated: 2026-08-04
contributors: [sam-gordashko]
further_reading:
  - title: "Intl.Segmenter (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Segmenter
    type: code
  - title: "UAX #29: Unicode Text Segmentation"
    url: https://unicode.org/reports/tr29/
    type: authority
license: CC-BY-4.0
---

# Grapheme cluster

## Definition

A grapheme cluster is what a reader thinks of as one [character](character.md), even if it is made of several [code points](code-point.md).

For example, `e` followed by a combining acute accent displays as `é`: one grapheme cluster, two code points.

### Why it matters in design systems

Unicode introduced this term to escape the ambiguity of the word "character", which in code almost always means a single code point. The standard's own reasoning is worth quoting: a basic unit of a writing system is often made up of several code points, so to avoid ambiguity it is useful to speak of a user-perceived character instead.<sup>1</sup> Grapheme clusters are how that idea is made computable, described as a best-effort approximation that can be determined programmatically and unambiguously.<sup>2</sup>

The boundary rules live in Unicode Standard Annex #29. There are two versions of them, and the annex asks anyone citing the definition to say which one they mean.<sup>3</sup> This glossary means the **extended** grapheme cluster, which is the default and the one Unicode recommends, because it handles spacing marks and therefore gets the right answer for scripts such as Devanagari and Tamil where the legacy version splits a written unit apart.<sup>4</sup>

That distinction is the reason this term earns a page in a design glossary rather than an engineering one. Any product with a name field, a character limit, a truncation, or a text cursor is making a decision about what counts as one character, and getting it wrong is not a subtle bug. It looks like a person's name being cut in half, an emoji turning into rubble, or a limit that silently allows twice as much text in one language as another.

### Common mistake

Counting "characters" by code points, or worse by UTF-16 code units, and calling that the length. An accented symbol, a Devanagari syllable, and a flag emoji can each be several code points, so naive length checks, truncation, and cursor steps end up splitting a single written unit apart. Unicode's guidance is direct: where you need to show users a character count, it should match the number of grapheme clusters.<sup>5</sup> The length your programming language reports is rarely that number.

### In practice

* **Segment by grapheme cluster, not by code unit:** in JavaScript, `Intl.Segmenter` with `granularity: "grapheme"` iterates user-perceived characters, and it is the default granularity.<sup>6</sup> Most other languages have a UAX #29 segmentation library. See [Intl.Segmenter (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Segmenter).
* **Truncation and limits:** when you cap a field at "N characters" or append an ellipsis, cut on grapheme cluster boundaries so you never slice a combined symbol or an emoji in half. Test the limit with a script that stacks marks, not only with English.
* **Agree on the unit across the stack:** decide what "one character" means in your spec, then make the design, the front end, the back end, and the database measure the same way. A limit enforced in three places with three different units is three different limits.

***

### Related terms and mentions

[Character](character.md) · [Code point](code-point.md) · [Combining mark](combining-mark.md) · [Devanagari](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Grapheme](grapheme.md) · [Language](../../language-terms/linguistics/language.md) · [Normalization](normalization.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Segmentation](segmentation.md) · [Spacing combining mark](spacing-combining-mark.md) · [Symbol](../../language-terms/writing-systems-and-scripts/symbol.md) · [Tamil script](../../language-terms/writing-systems-and-scripts/tamil-script.md) · [Unicode](unicode.md) · [Unicode Standard](unicode-standard.md) · [UTF-16](utf-16.md) · [Writing system](../../language-terms/writing-systems-and-scripts/writing-system.md) · [Text in software](../text-in-software/)

### Further reading

* Code & specs: [Intl.Segmenter (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Segmenter)
* Foundations: [UAX #29: Unicode Text Segmentation](https://unicode.org/reports/tr29/)

### Sources

1. "There are many cases where such a basic unit is made up of multiple Unicode code points. To avoid ambiguity with the term character as defined for encoding purposes, it can be useful to speak of a user-perceived character" - Unicode Standard Annex #29: Unicode Text Segmentation [https://www.unicode.org/reports/tr29/](https://www.unicode.org/reports/tr29/)
2. "In implementations, the notion of user-perceived characters corresponds to the concept of grapheme clusters. They are a best-effort approximation that can be determined programmatically and unambiguously" - Unicode Standard Annex #29 [https://www.unicode.org/reports/tr29/](https://www.unicode.org/reports/tr29/)
3. "When citing the Unicode definition of grapheme clusters, it must be clear which of the two alternatives are being specified: extended versus legacy" - Unicode Standard Annex #29 [https://www.unicode.org/reports/tr29/](https://www.unicode.org/reports/tr29/)
4. "The extended grapheme clusters should be used in implementations in preference to legacy grapheme clusters, because they provide better results for Indic scripts such as Tamil or Devanagari in which editing by orthographic syllable is typically preferred" - Unicode Standard Annex #29 [https://www.unicode.org/reports/tr29/](https://www.unicode.org/reports/tr29/)
5. "In those relatively rare circumstances where programmers need to supply end users with user-perceived character counts, the counts should correspond to the number of segments delimited by grapheme cluster boundaries" - Unicode Standard Annex #29 [https://www.unicode.org/reports/tr29/](https://www.unicode.org/reports/tr29/)
6. "\"grapheme\" (default) Split the input into segments at grapheme cluster (user-perceived character) boundaries, as determined by the locale" - Intl.Segmenter() constructor, MDN [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Intl/Segmenter/Segmenter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Segmenter/Segmenter)
