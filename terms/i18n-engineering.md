---
term: Internationalization & engineering
slug: i18n-engineering
aliases: []
tags: []
level: foundational
entry_type: overview
summary: Internationalization and engineering covers the practices, data, and tooling that let one product work correctly across languages and regions, from the up-front design work to locale data, sorting, segmentation, and input.
related: [characters-encoding, shaping-layout]
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
Internationalization and engineering covers the practices, data, and tooling that let one product work correctly across languages and regions, from the up-front design work to locale data, sorting, segmentation, and input.

## Why it matters
Supporting the world's languages is not one feature you add at the end; it is a set of habits and dependencies woven through a product. Internationalization is the architecture that makes adaptation possible, localization is the adaptation itself, and in between sit the things that quietly go wrong if ignored: text that grows when translated, sorting that differs by language, words that have no spaces between them, and input methods that do not map one key to one character. This category gives design-systems and engineering readers the vocabulary to plan for all of that deliberately instead of discovering it in a bug report from another locale.

## Key terms
A guided tour of the internationalization and engineering terms in this glossary, grouped by what they help you do:

- **The i18n / l10n model:** [Internationalization](internationalization.md), [Localization](localization.md), [Locale](locale.md)
- **Locale-aware text behavior:** [Collation](collation.md), [Segmentation](segmentation.md)
- **Locale data and libraries:** [CLDR](cldr.md), [ICU](icu.md)
- **Designing for translation:** [Text expansion](text-expansion.md), [Pseudolocalization](pseudolocalization.md)
- **Input:** [Input method editor (IME)](input-method-editor.md), [Keyboard layout](keyboard-layout.md)

## Further reading
- Foundations: [W3C Internationalization (i18n)](https://www.w3.org/International/)
