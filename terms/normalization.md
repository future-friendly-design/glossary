---
term: Normalization
slug: normalization
aliases:
  - Unicode normalization
  - NFC
  - NFD
level: advanced
depth: deep
summary: >-
  Normalization rewrites text into a consistent form so that strings that look
  the same compare as equal.
related:
  - precomposed-character
  - combining-mark
  - grapheme-cluster
  - unicode
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: String.prototype.normalize() (MDN)
    url: >-
      https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/normalize
    type: code
  - title: 'UAX #15: Unicode Normalization Forms'
    url: https://unicode.org/reports/tr15/
    type: authority
license: CC-BY-4.0
tags:
  - characters-encoding
---

# Normalization

## Definition

Normalization rewrites text into a consistent form so that strings that look the same compare as equal.

## Why it matters

Unicode defines four normalization forms in UAX #15. NFC composes sequences into [precomposed-character](precomposed-character.md)s where possible, while NFD decomposes them into a base plus [combining-mark](../programming-terms/text-for-digital-products-and-the-web/combining-mark.md)s; the compatibility forms NFKC and NFKD additionally fold formatting variants (like a ligature back into its letters, or a full-width form into a normal one). Normalization also fixes the order of combining marks. Without it, text that looks identical can fail to match.

## Example

Comparing a file name typed as precomposed "é" with one typed as "e" plus a combining accent only matches after normalizing both to the same form (NFC or NFD).

## Common mistake

Comparing, searching, or deduplicating user text without normalizing first. Two visually identical strings can differ at the byte level (precomposed versus decomposed), so equality checks, lookups, uniqueness constraints, and "have I seen this before" logic silently miss matches. The bug is invisible in ASCII testing and only surfaces with accented or non-Latin input.

## In practice

* **Normalize at the boundary:** pick a form (NFC is the common choice for storage, since it is compact and matches most keyboard input) and normalize text as it enters your system, so everything downstream compares consistently. In JavaScript that is `String.prototype.normalize()`. See [String.prototype.normalize() (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/normalize).
* **Compatibility forms (NFKC/NFKD) are stronger and lossy:** they fold variants like [full-width](full-width.md) forms and ligatures together, which is useful for search and matching but wrong for storage where you must preserve the exact input. Choose deliberately per use.
* **Consistency across the stack:** the front end, back end, and database should agree on one normalization form, or a value stored one way will not match the same value queried another way.

## Related terms

[Precomposed character](precomposed-character.md) · [Combining mark](../programming-terms/text-for-digital-products-and-the-web/combining-mark.md) · [Grapheme cluster](grapheme-cluster.md) · [Unicode](unicode.md) · [Full-width](full-width.md)

## Further reading

* Code & specs: [String.prototype.normalize() (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/normalize)
* Foundations: [UAX #15: Unicode Normalization Forms](https://unicode.org/reports/tr15/)
