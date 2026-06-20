---
term: Pseudolocalization
slug: pseudolocalization
aliases: [pseudo-localization, pseudo-loc]
tags: [i18n-engineering]
level: intermediate
depth: deep
summary: Pseudolocalization is a testing technique that fakes a translation to catch internationalization bugs before real translation begins.
related: [internationalization, localization, text-expansion]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Pseudolocalization (Microsoft Learn)"
    url: https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization
    type: authority
license: CC-BY-4.0
---

## Definition
Pseudolocalization is a testing technique that fakes a translation to catch internationalization bugs before real translation begins.

## Why it matters
Instead of translating into a real language, the tool replaces source text with an altered version that stays readable but exaggerates the traits that break products: longer strings, accented or non-Latin characters, and delimiters around each string to reveal clipping. It surfaces the big three i18n bugs cheaply and early: hard-coded strings (they never get transformed, so they stand out), layout overflow, and encoding or font gaps. It runs throughout development, long before localization vendors are involved.

## Example
"Settings" might be shown as "[!!! Ŝéttîñĝŝ !!!]" so testers immediately spot truncation or an untransformed (hard-coded) string.

## Common mistake
Waiting for real translations to find internationalization and layout bugs. By the time a localization vendor delivers, the design is locked and fixes are expensive, and the same overflow, clipping, and hard-coded-string problems could have been caught weeks earlier with a pseudo locale on every build.

## In practice
- **Run it early and continuously:** turn on a pseudo locale from the first screens and keep it in CI, so untransformed strings and clipped layouts surface on every build. Use a reserved, never-real locale name (Microsoft uses `qps-ploc`; ICU provides `en-XA` for accents and `en-XB` for bidirectional). See [Pseudolocalization (Microsoft Learn)](https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization).
- **Read each signal:** padding simulates [text-expansion](text-expansion.md), bracket delimiters expose truncation and string concatenation, and non-Latin padding exposes font and encoding gaps.
- **It complements, not replaces, real QA:** pseudoloc proves a product is localizable; it does not validate an actual translation.

## Related terms
[Internationalization](internationalization.md) · [Localization](localization.md) · [Text expansion](text-expansion.md)

## Further reading
- Foundations: [Pseudolocalization (Microsoft Learn)](https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization)
