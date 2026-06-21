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

# Characters, encoding & text model

## Definition
Characters, encoding, and the text model are how written language is represented in software: the abstract characters, the numbers Unicode assigns them, and the rules for turning those into bytes, marks, and forms.

## Why it matters
Every product handles text, and a surprising share of bugs trace back to this layer: garbled accents, miscounted string lengths, emoji sliced in half, searches that miss obvious matches, empty boxes where a script should be. Most of them come from blurring the layers, treating a character as a glyph, a code point as a byte, or a code unit as a user-visible character. Getting the model straight, plus the algorithms that operate on it (encoding, normalization, the bidirectional algorithm, segmentation), is what lets you build software that handles the world's languages without corrupting them. This category collects the vocabulary for reasoning about text precisely.

## Key terms
A guided tour of the characters and encoding terms in this glossary, grouped by what they help you reason about:

- **The text model:** [Character](character.md), [Glyph](glyph.md), [Code point](code-point.md), [Grapheme cluster](grapheme-cluster.md)
- **The standard and its structure:** [Unicode](unicode.md), [Plane / Basic Multilingual Plane](plane-bmp.md)
- **Encodings:** [Character encoding](character-encoding.md), [UTF-8](utf-8.md), [UTF-16](utf-16.md), [Surrogate pair](surrogate-pair.md)
- **Combining and normalizing:** [Combining mark](combining-mark.md), [Precomposed character](precomposed-character.md), [Normalization](normalization.md), [Diacritic](diacritic.md), [Tone mark](tone-mark.md)
- **Direction:** [Bidirectional text](bidirectional-text.md), [Text direction](text-direction.md)
- **Rendering gaps:** [Tofu](tofu.md)

## Further reading
- Foundations: [W3C Internationalization (i18n)](https://www.w3.org/International/)
