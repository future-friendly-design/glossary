---
term: Tategaki
slug: tategaki
aliases: [vertical writing, 縦書き]
tags: [typography]
level: advanced
depth: deep
summary: Tategaki is vertical writing, set top to bottom with columns running right to left, traditional in Japanese and other East Asian scripts.
related: [full-width, font-coverage]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "writing-mode (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode
    type: code
  - title: "Vertical text (W3C Internationalization)"
    url: https://www.w3.org/International/articles/vertical-text/
    type: authority
license: CC-BY-4.0
---

## Definition
Tategaki is vertical writing, set top to bottom with columns running right to left, traditional in Japanese and other East Asian scripts.

## Why it matters
Tategaki was long the standard for Japanese and is still everywhere in novels, newspapers, manga, signage, and formal correspondence, while horizontal writing (yokogaki) became common later. The direction reshapes the whole object: a book set in tategaki binds on the right and its pages advance leftward, the reverse of an English book. For digital work this is not a niche concern, since CJK products often need both directions, and CSS `writing-mode` is what makes vertical layout possible on the web.

## Example
A Japanese novel is typically set in tategaki, read top to bottom and right to left.

## Common mistake
Assuming vertical text is just horizontal text rotated ninety degrees. It is not: individual glyph orientation, punctuation placement, and runs of embedded Latin letters or numbers (set upright in a horizontal cluster called tate-chu-yoko) all follow their own rules. Rotating a whole text block produces something a reader of the script will see as wrong. *(Flag for the language experts to confirm the specifics.)*

## In practice
- **CSS:** `writing-mode: vertical-rl` sets top-to-bottom, right-to-left flow. The W3C Internationalization [Vertical text](https://www.w3.org/International/articles/vertical-text/) article is the practical guide to the surrounding behavior, and [writing-mode (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode) covers the property. Prefer logical (flow-relative) CSS properties so layout adapts instead of being pinned to physical sides.
- **UI:** vertical text changes more than the paragraph. Scroll direction, form controls, line breaking, and bidirectional runs all shift, so test the whole component in vertical mode, not just the body copy.
- **Languages:** when tategaki versus yokogaki is expected is a culturally specific judgment; confirm usage with the language experts rather than guessing from the general rule.

## Related terms
[full-width](full-width.md) · [font-coverage](font-coverage.md)

## Further reading
- Code & specs: [writing-mode (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode)
- Foundations: [Vertical text (W3C Internationalization)](https://www.w3.org/International/articles/vertical-text/)
