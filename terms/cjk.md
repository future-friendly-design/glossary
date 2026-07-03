---
term: CJK
slug: cjk
aliases:
  - CJK characters
  - CJKV
level: intermediate
depth: core
summary: >-
  CJK is shorthand for the shared Chinese, Japanese, and Korean characters
  handled together in computing and typography.
related:
  - han-characters
  - logographic
  - hiragana
  - katakana
  - hangul
  - unicode-standard
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: 'Unicode FAQ: Chinese and Japanese'
    url: https://www.unicode.org/faq/han_cjk.html
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# CJK

## Definition

CJK is shorthand for the shared Chinese, Japanese, and Korean characters handled together in computing and typography.

## Why it matters

CJK abbreviates Chinese, Japanese, and Korean, the three written traditions that share a large stock of [Han characters](han-characters.md). Through a process called Han unification, Unicode encodes the common characters once as "CJK Unified Ideographs": the base block (U+4E00 to U+9FFF) holds 20,992 characters, with tens of thousands more across extension blocks. The label matters in practice because CJK text shares engineering concerns regardless of language: large glyph sets and font files, full-width and proportional forms, and vertical writing. It is sometimes extended to CJKV to include Vietnamese.

## Example

A single Unicode code point in the CJK Unified Ideographs block can be displayed with Chinese, Japanese, or Korean font styling, since Han unification encodes the shared character once rather than per language.

## Related terms

[Han characters](han-characters.md) · [Logographic](../language-terms/writing-systems-and-scripts/logographic.md) · [Hiragana](hiragana.md) · [Katakana](katakana.md) · [Hangul](hangul.md) · [Unicode Standard](unicode-standard.md)

## Further reading

* Foundations: [Unicode FAQ: Chinese and Japanese](https://www.unicode.org/faq/han_cjk.html)
