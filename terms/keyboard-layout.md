---
term: Keyboard layout
slug: keyboard-layout
aliases: []
tags: [i18n-engineering]
level: foundational
depth: core
summary: A keyboard layout is the mapping between physical keys and the characters they produce, which varies by language and region.
related: [input-method-editor, internationalization, locale]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Keyboard layout (Wikipedia)"
    url: https://en.wikipedia.org/wiki/Keyboard_layout
    type: authority
license: CC-BY-4.0
---

## Definition
A keyboard layout is the mapping between physical keys and the characters they produce, which varies by language and region.

## Why it matters
Different regions use different layouts so that the most-used letters and accented characters are easy to reach: QWERTY, AZERTY (France), QWERTZ (German-speaking countries), and Dvorak among many others. The layout is a software mapping separate from the printed key caps, so the same hardware can produce different characters depending on the active layout. It matters for internationalization because shortcuts and special characters move around with the layout, so a keystroke combination that works on one is not guaranteed on another.

## Example
On a French AZERTY layout, the A and Q keys are swapped compared with US QWERTY.

## Related terms
[[input-method-editor]] · [[internationalization]] · [[locale]]

## Further reading
- Foundations: [Keyboard layout (Wikipedia)](https://en.wikipedia.org/wiki/Keyboard_layout)
