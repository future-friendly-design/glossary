---
term: Bidirectional text
slug: bidirectional-text
aliases:
  - bidi
  - bidi text
level: advanced
depth: deep
summary: >-
  Bidirectional text mixes left-to-right and right-to-left text in the same
  line.
related:
  - text-direction
  - unicode
  - complex-text-layout
  - left-to-right
  - right-to-left
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: unicode-bidi (MDN)
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi
    type: code
  - title: Unicode Bidirectional Algorithm basics (W3C)
    url: https://www.w3.org/International/articles/inline-bidi-markup/uba-basics
    type: authority
  - title: Bidirectionality and RTL (Material Design 3)
    url: https://m3.material.io/foundations/layout/bidirectionality-rtl
    type: resource
license: CC-BY-4.0
tags:
  - writing-systems-scripts
  - shaping-layout
  - i18n-engineering
---

# Bidirectional text

## Definition

Bidirectional text refers to mixing both left-to-right and right-to-left text directions in the same line of text.

For example, an Arabic sentence with the English brand name `iPhone` and the year `2026` in it runs both ways at once.

### Why it matters in design systems

Scripts like [Arabic](../../terms/arabic-script.md) and [Hebrew](../../terms/hebrew-script.md) run right to left, but numbers and embedded Latin-script text run left to right. So the order the characters are stored in, called the logical order, is not the order they are displayed in, called the visual order.

A computer cannot guess that order. The [Unicode](../../terms/unicode.md) Bidirectional Algorithm works it out from each character's direction property, and it leans on the [base direction](text-direction.md) of the line to resolve neutral characters like spaces and punctuation.<sup>1</sup> Setting that base direction correctly is what keeps mixed text from coming out scrambled.

So for a design system, bidirectional text is necessary but not sufficient on its own. Marking a block right to left is only the start; embedded runs that go the other way, such as a brand name or a file path, still need to be isolated, and the layout around them has to flip with logical CSS properties. That wider work is [complex text layout](../../terms/complex-text-layout.md).

### Example

An Arabic sentence containing the English brand `iPhone` and the year `2026` needs the bidi algorithm to lay out each run correctly: the Arabic flows right to left, while `iPhone` and `2026` each read left to right inside it.

### Common mistake

Assuming the algorithm handles everything once the text is marked right to left. The classic bug is an embedded opposite-direction run, a Latin-script product name, a URL, or a user-entered value inside Arabic, reordering wrongly because the surrounding base direction or isolation is off, so a bracket or period jumps to the wrong end. Joining strings of unknown direction (a name, a file path) without isolating them is the usual cause.

### In practice

* **Set base direction; do not fight the algorithm:** use the HTML `dir` attribute (or `dir="auto"` for data whose direction you do not know) and the CSS `direction` property, the [text direction](text-direction.md) concept. Avoid manually overriding `unicode-bidi`, which MDN flags as not intended for web authors.
* **Isolate embedded runs:** wrap inserted opposite- or unknown-direction content (user names, brands, paths) in a `<bdi>` element or `unicode-bidi: isolate` so it cannot disturb the surrounding text.<sup>2</sup>
* **Use logical CSS properties:** `margin-inline`, `text-align: start`, and the like let a layout flip correctly between [left-to-right](left-to-right.md) and [right-to-left](right-to-left.md) instead of being pinned to physical sides. This is part of [complex text layout](../../terms/complex-text-layout.md). Confirm right-to-left behaviour with the language experts for those locales.

***

### Related terms and mentions

[Arabic script](../../terms/arabic-script.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Hebrew script](../../terms/hebrew-script.md) · [Left-to-right](left-to-right.md) · [Right-to-left](right-to-left.md) · [Script rules](script-rules.md) · [Text direction](text-direction.md) · [Unicode](../../terms/unicode.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [unicode-bidi (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi)
* Foundations: [Unicode Bidirectional Algorithm basics (W3C)](https://www.w3.org/International/articles/inline-bidi-markup/uba-basics)
* Resource library: [Bidirectionality and RTL (Material Design 3)](https://m3.material.io/foundations/layout/bidirectionality-rtl)

### Sources

1. The order of characters in memory (logical order) is not the same as the order in which they are displayed (visual order), and the algorithm resolves neutral characters from the prevailing base direction - Unicode Bidirectional Algorithm basics (W3C) [https://www.w3.org/International/articles/inline-bidi-markup/uba-basics](https://www.w3.org/International/articles/inline-bidi-markup/uba-basics)
2. The `bdi` element and `unicode-bidi: isolate` isolate a run of text so its direction does not affect the surrounding text - unicode-bidi (MDN) [https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi](https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi)
