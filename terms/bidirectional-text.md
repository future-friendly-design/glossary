---
term: Bidirectional text
slug: bidirectional-text
aliases: [bidi, bidi text]
tags: [characters-encoding]
level: advanced
depth: deep
summary: Bidirectional text mixes left-to-right and right-to-left scripts in the same line.
related: [text-direction, unicode, complex-text-layout]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "unicode-bidi (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi
    type: code
  - title: "Unicode Bidirectional Algorithm basics (W3C)"
    url: https://www.w3.org/International/articles/inline-bidi-markup/uba-basics
    type: authority
license: CC-BY-4.0
---

## Definition
Bidirectional text mixes left-to-right and right-to-left scripts in the same line.

## Why it matters
Scripts like Arabic and Hebrew run right to left, but numbers and embedded Latin text run left to right, so the order characters are displayed in (visual order) differs from the order they are stored in (logical order). The Unicode Bidirectional Algorithm (UAX #9) works out the correct visual order from each character's directional property, resolving neutral characters like spaces and punctuation by context. Getting the base direction right is what keeps mixed text from coming out scrambled.

## Example
An Arabic sentence containing the English brand "iPhone" and the year "2026" needs the bidi algorithm to lay out each run correctly.

## Common mistake
Assuming the algorithm handles everything once the text is marked RTL. The classic bug is an embedded opposite-direction run, a Latin product name, a URL, or a user-entered value inside Arabic, reordering wrongly because the surrounding base direction or isolation is off, so a bracket or period jumps to the wrong end. Concatenating strings of unknown direction (a name, a file path) without isolating them is the usual cause.

## In practice
- **Set base direction; do not fight the algorithm:** use the HTML `dir` attribute (or `dir="auto"` for data whose direction you do not know) and the CSS `direction` property (the [text-direction](text-direction.md) concept). Avoid manually overriding `unicode-bidi`, which MDN flags as not intended for web authors.
- **Isolate embedded runs:** wrap inserted opposite- or unknown-direction content (user names, brands, paths) in a `<bdi>` element or `unicode-bidi: isolate` so it cannot disturb the surrounding text. See [unicode-bidi (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi).
- **Use logical CSS properties:** `margin-inline`, `text-align: start`, and the like let a layout flip correctly between LTR and RTL instead of being pinned to physical sides. This is part of [complex-text-layout](complex-text-layout.md). Confirm RTL behavior with the language experts for those locales.

## Related terms
[text-direction](text-direction.md) · [unicode](unicode.md) · [complex-text-layout](complex-text-layout.md)

## Further reading
- Code & specs: [unicode-bidi (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi)
- Foundations: [Unicode Bidirectional Algorithm basics (W3C)](https://www.w3.org/International/articles/inline-bidi-markup/uba-basics)
