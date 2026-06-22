---
term: Punctuation mark
slug: punctuation-mark
aliases: []
tags: [characters-encoding]
level: foundational
depth: core
summary: "A punctuation mark is a symbol such as a comma, period, or question mark that structures written text rather than representing a sound."
related: [mark, orthography, script]
status: draft
version_added: 0.1
updated: 2026-06-21
contributors: [sam-gordashko]
further_reading:
  - title: "Unicode Standard Annex #44: General Category Values"
    url: https://www.unicode.org/reports/tr44/#General_Category_Values
    type: code
license: CC-BY-4.0
---

# Punctuation mark

## Definition
A punctuation mark is a symbol such as a comma, period, or question mark that structures written text rather than representing a sound.

## Why it matters
Punctuation is the fourth sense of "[mark](mark.md)" the glossary has to keep separate from the others: it is unrelated to combining marks or diacritics, even though it shares the word. It earns a node because punctuation is genuinely language and script specific, which is easy to forget when English defaults are baked into a product. Which symbols are used, how quotation marks look, whether a question mark is reversed or a sentence-ender is a different glyph: these are part of a language's [orthography](orthography.md), not universal constants. In Unicode, punctuation is its own family of General Categories (the P groups), distinct from letters and from combining marks.

## Example
Spanish opens a question with an inverted "¿" and closes it with "?"; Greek uses a different mark for the question; and several scripts use their own quotation conventions, so "punctuation" is not one fixed set.

## Related terms
[Mark](mark.md) · [Orthography](orthography.md) · [Script](script.md)

## Further reading
- Code & specs: [Unicode Standard Annex #44: General Category Values](https://www.unicode.org/reports/tr44/#General_Category_Values)

<!-- NEEDS EXPERT REVIEW: the language-specific punctuation examples (Spanish inverted marks, Greek question mark, per-language quotation styles) are standard but should be confirmed by the SILCON cohort. This entry covers the fourth ("punctuation") sense of mark; a fuller punctuation cluster can follow later. -->
