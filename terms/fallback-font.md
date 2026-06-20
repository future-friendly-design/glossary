---
term: Fallback font
slug: fallback-font
aliases: [font stack, font fallback]
tags: [typography]
level: intermediate
depth: deep
summary: A fallback font is the next font a system uses when the preferred one is unavailable or missing a needed character.
related: [font-coverage, font-subsetting, font]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "font-family (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/font-family
    type: code
license: CC-BY-4.0
---

## Definition
A fallback font is the next font a system uses when the preferred one is unavailable or missing a needed character.

## Why it matters
In CSS, `font-family` is a priority list (a "font stack"), and the browser picks the first available font that can render each character, working one character at a time. Ending the stack with a generic family like `sans-serif` guarantees there is always an acceptable substitute. Fallbacks do double duty: they cover the case where the preferred font fails to load, and the case where it loads but lacks a glyph for a particular character, which ties directly to [font-coverage](font-coverage.md).

## Example
In `font-family: Inter, Helvetica, sans-serif`, Helvetica and then `sans-serif` act as fallbacks if Inter fails to load.

## Common mistake
Leaving the generic family off the end of the stack, or assuming the fallback looks close enough. A fallback with different metrics (a different x-height or width) makes text visibly jump when the web font finishes loading and swaps in, the layout shift known as FOUT. Always end with a generic, and treat the fallback's shape as something to manage, not ignore.

## In practice
- **CSS and performance:** end every stack with a generic family, and to reduce the swap-in shift, match the fallback's metrics to the web font using `@font-face` metric overrides (`size-adjust`, `ascent-override`, `descent-override`) or a tool that generates them. See [font-family (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family).
- **Coverage:** fallbacks are the safety net for [font-coverage](font-coverage.md) gaps, since a character the primary font lacks is drawn by the next font in the stack that has it. Order the stack so that substitute is acceptable for every script you support.
- **Languages:** for multilingual interfaces, include script-appropriate fallbacks (for example a CJK fallback) rather than trusting the generic family alone to produce a good result.

## Related terms
[font-coverage](font-coverage.md) · [font-subsetting](font-subsetting.md) · [font](font.md)

## Further reading
- Code & specs: [font-family (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family)
