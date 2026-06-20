---
term: Characters, encoding & text model
slug: characters-encoding
aliases: []
tags: []
level: foundational
entry_type: overview
summary: "Characters, encoding, and the text model are how written language is represented in software: the abstract characters, the numbers Unicode assigns them, and the rules for turning those into bytes, marks, and forms."
related: [typography]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "W3C Internationalization (i18n)"
    url: https://www.w3.org/International/
    type: authority
license: CC-BY-4.0
---

## Definition
Characters, encoding, and the text model are how written language is represented in software: the abstract characters, the numbers Unicode assigns them, and the rules for turning those into bytes, marks, and forms.

## Why it matters
Every product handles text, and a surprising share of bugs trace back to this layer: garbled accents, miscounted string lengths, emoji sliced in half, searches that miss obvious matches, empty boxes where a script should be. Most of them come from blurring the layers, treating a character as a glyph, a code point as a byte, or a code unit as a user-visible character. Getting the model straight, plus the algorithms that operate on it (encoding, normalization, the bidirectional algorithm, segmentation), is what lets you build software that handles the world's languages without corrupting them. This category collects the vocabulary for reasoning about text precisely.

## Key terms
A guided tour of the characters and encoding terms in this glossary, grouped by what they help you reason about:

- **The text model:** [[character]], [[glyph]], [[code-point]], [[grapheme-cluster]]
- **The standard and its structure:** [[unicode]], [[plane-bmp]]
- **Encodings:** [[character-encoding]], [[utf-8]], [[utf-16]], [[surrogate-pair]]
- **Combining and normalizing:** [[combining-mark]], [[precomposed-character]], [[normalization]], [[diacritic]], [[tone-mark]]
- **Direction:** [[bidirectional-text]], [[text-direction]]
- **Rendering gaps:** [[tofu]]

## Further reading
- Foundations: [W3C Internationalization (i18n)](https://www.w3.org/International/)
