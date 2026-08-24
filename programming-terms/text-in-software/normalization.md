---
term: Normalization
slug: normalization
aliases:
  - Unicode normalization
  - NFC
  - NFD
level: advanced
depth: deep
summary: Normalization rewrites text into one consistent form, so that two pieces of text that look the same to a reader also match when software compares them.
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

Normalization rewrites text into one consistent form, so that two pieces of text that look the same to a reader also match when software compares them.

## Why it matters

The same visible text can be stored in more than one way. `é` can be a single character with the accent already built in, or the plain letter `e` followed by a separate accent character. A reader cannot tell the two apart. Software comparing them piece by piece can, and reports that they do not match.

Normalization is the repair: rewrite both into whichever form you have chosen, and only then compare. [Unicode](unicode.md) defines four such forms in UAX #15. NFC composes sequences into [precomposed characters](precomposed-character.md) where possible, while NFD decomposes them into a base plus [combining marks](combining-mark.md); the compatibility forms NFKC and NFKD additionally fold formatting variants together, such as a [ligature](../text-for-digital-products-and-the-web/ligature.md) back into its separate letters, or a [full-width](full-width.md) form into an ordinary one. Normalization also fixes the order of combining marks, so a base carrying two marks matches whichever mark was typed first. Without it, text that looks identical can fail to match.

## Example

Comparing a file name typed as precomposed `é` with one typed as `e` plus a combining accent only matches after normalizing both to the same form (NFC or NFD).

## Common mistake

Comparing, searching, or deduplicating user text without normalizing first. Two pieces of text that look identical can be stored differently (precomposed versus decomposed), so equality checks, lookups, uniqueness constraints, and "have I seen this before" logic silently miss matches. The bug is invisible if you only test in unaccented English, and surfaces the first time somebody enters an accented or non-Latin name.

## In practice

* **Normalize at the boundary:** pick a form (NFC is the common choice for storage, since it is compact and matches most keyboard input) and normalize text as it enters your system, so everything downstream compares consistently. In JavaScript that is `String.prototype.normalize()`. See [String.prototype.normalize() (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/normalize).
* **Compatibility forms (NFKC/NFKD) are stronger and lossy:** they fold variants like [full-width](full-width.md) forms and ligatures together, which is useful for search and matching but wrong for storage where you must preserve the exact input. Choose deliberately per use.
* **Consistency across the stack:** the front end, back end, and database should agree on one normalization form, or a value stored one way will not match the same value queried another way.

## Related terms

[Combining mark](combining-mark.md) · [Full-width](full-width.md) · [Grapheme cluster](grapheme-cluster.md) · [Ligature](../text-for-digital-products-and-the-web/ligature.md) · [Precomposed character](precomposed-character.md) · [Unicode](unicode.md)

## Further reading

* Code & specs: [String.prototype.normalize() (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/normalize)
* Foundations: [UAX #15: Unicode Normalization Forms](https://unicode.org/reports/tr15/)
