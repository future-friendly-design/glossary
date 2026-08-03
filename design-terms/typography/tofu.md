---
term: Tofu
slug: tofu
aliases:
  - .notdef glyph
  - missing glyph box
level: foundational
depth: core
summary: >-
  Tofu is the empty box shown when no available font has a glyph for a
  character.
related:
  - glyph
  - font
  - font-coverage
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Tofu (Google Fonts Knowledge)
    url: https://fonts.google.com/knowledge/glossary/tofu
    type: resource
license: CC-BY-4.0
tags:
  - characters-encoding
---

# Tofu

## Definition

Tofu is the empty box shown when no available font has a glyph for a character.

## Why it matters

When text contains a character that the current font and its [fallback-font](../../programming-terms/text-for-digital-products-and-the-web/fallback-font.md)s cannot draw, the renderer shows a placeholder, often a plain rectangle that designers nicknamed "tofu". The key thing it tells you: this is a missing [glyph](../../programming-terms/text-for-digital-products-and-the-web/glyph.md), not a broken character or a bad encoding, so the fix is font coverage, not re-saving the file. Google's Noto font family is even named "No Tofu" because it aims to cover as many scripts as possible to eliminate these boxes.

## Example

A page using a Latin-only font may show tofu boxes where Tibetan or emoji should appear.

## Related terms

[Fallback font](../../programming-terms/text-for-digital-products-and-the-web/fallback-font.md) · [Font](../../programming-terms/text-for-digital-products-and-the-web/font.md) · [Font coverage](../../programming-terms/text-for-digital-products-and-the-web/font-coverage.md) · [Glyph](../../programming-terms/text-for-digital-products-and-the-web/glyph.md)

## Further reading

* Resource library: [Tofu (Google Fonts Knowledge)](https://fonts.google.com/knowledge/glossary/tofu)
