---
term: Characters, encoding & text model
slug: characters-encoding
aliases: []
level: foundational
entry_type: overview
summary: >-
  Characters, encoding, and the text model are how written language is
  represented in software: the abstract characters, the numbers Unicode assigns
  them, and the rules for turning those into bytes, marks, and forms.
related:
  - typography
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: W3C Internationalization (i18n)
    url: https://www.w3.org/International/
    type: authority
license: CC-BY-4.0
---

# Characters, encoding & text model

## Definition

Characters, encoding, and the text model are how written language is represented in software: the abstract characters, the numbers Unicode assigns them, and the rules for turning those into bytes, marks, and forms.

## Why it matters

Every product handles text, and a surprising share of bugs trace back to this layer: garbled accents, miscounted string lengths, emoji sliced in half, searches that miss obvious matches, empty boxes where a script should be. Most of them come from blurring the layers, treating a character as a glyph, a code point as a byte, or a code unit as a user-visible character. Getting the model straight, plus the algorithms that operate on it (encoding, normalization, the bidirectional algorithm, segmentation), is what lets you build software that handles the world's languages without corrupting them. This category collects the vocabulary for reasoning about text precisely.

## Key terms

A guided tour of the characters and encoding terms in this glossary, grouped by what they help you reason about:

* **The text model:** [Character](../programming-terms/text-for-digital-products-and-the-web/character.md), [Glyph](../programming-terms/text-for-digital-products-and-the-web/glyph.md), [Code point](../programming-terms/text-for-digital-products-and-the-web/code-point.md), [Grapheme cluster](../programming-terms/text-for-digital-products-and-the-web/grapheme-cluster.md)
* **The standard and its structure:** [Unicode](../programming-terms/text-for-digital-products-and-the-web/unicode.md), [Plane / Basic Multilingual Plane](../programming-terms/text-for-digital-products-and-the-web/plane-bmp.md)
* **Encodings:** [Character encoding](../programming-terms/text-for-digital-products-and-the-web/character-encoding.md), [UTF-8](../programming-terms/text-for-digital-products-and-the-web/utf-8.md), [UTF-16](../programming-terms/text-for-digital-products-and-the-web/utf-16.md), [Surrogate pair](../programming-terms/text-for-digital-products-and-the-web/surrogate-pair.md)
* **Combining and normalizing:** [Combining mark](../programming-terms/text-for-digital-products-and-the-web/combining-mark.md), [Precomposed character](../programming-terms/text-for-digital-products-and-the-web/precomposed-character.md), [Normalization](../programming-terms/text-for-digital-products-and-the-web/normalization.md), [Diacritic](../language-terms/writing-systems-and-scripts/diacritic.md), [Tone mark](../language-terms/writing-systems-and-scripts/tone-mark.md)
* **Direction:** [Bidirectional text](../language-terms/writing-systems-and-scripts/bidirectional-text.md), [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md)
* **Rendering gaps:** [Tofu](../design-terms/typography/tofu.md)

## Further reading

* Foundations: [W3C Internationalization (i18n)](https://www.w3.org/International/)
