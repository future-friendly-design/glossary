---
term: Grapheme cluster
slug: grapheme-cluster
aliases:
  - user-perceived character
level: intermediate
depth: deep
summary: >-
  A grapheme cluster is what a reader thinks of as one character, even if it is
  made of several code points.
related:
  - character
  - code-point
  - combining-mark
  - normalization
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Intl.Segmenter (MDN)
    url: >-
      https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Segmenter
    type: code
  - title: 'UAX #29: Unicode Text Segmentation'
    url: https://unicode.org/reports/tr29/
    type: authority
license: CC-BY-4.0
tags:
  - characters-encoding
---

# Grapheme cluster

## Definition

A grapheme cluster is what a reader thinks of as one character, even if it is made of several code points.

## Why it matters

Unicode uses this term to sidestep the ambiguity of "character," which in code usually means a single [code-point](code-point.md). A base letter plus its [combining-mark](../programming-terms/text-for-digital-products-and-the-web/combining-mark.md)s, or a multi-code-point emoji, counts as one grapheme cluster. The boundary rules are defined in UAX #29, and respecting them is what makes cursor movement, text selection, and "character" counting behave the way users actually expect.

## Example

"e" plus a combining acute accent displays as "é": one grapheme cluster, but two code points.

## Common mistake

Counting "characters" by code points (or worse, by UTF-16 code units) and calling that the string length. A flag emoji or an accented letter can be several code points, so naive length checks, truncation, and cursor steps end up splitting a single glyph in half or miscounting. The "length" of a string is rarely the count a user has in mind.

## In practice

* **Segment by grapheme cluster, not code unit:** in JavaScript, `Intl.Segmenter` with `granularity: "grapheme"` iterates user-perceived characters, and most languages have a UAX #29 segmentation library. See [Intl.Segmenter (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Segmenter).
* **Truncation and limits:** when you cap a field at "N characters" or append an ellipsis, cut on grapheme boundaries so you never slice a combined character or emoji apart.
* **Counting and validation:** decide what "one character" means in your spec (usually a grapheme cluster) so the front end, back end, and database all measure the same way instead of each using a different unit.

## Related terms

[Character](character.md) · [Code point](code-point.md) · [Combining mark](../programming-terms/text-for-digital-products-and-the-web/combining-mark.md) · [Normalization](normalization.md)

## Further reading

* Code & specs: [Intl.Segmenter (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Segmenter)
* Foundations: [UAX #29: Unicode Text Segmentation](https://unicode.org/reports/tr29/)
