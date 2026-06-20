---
term: Leading
slug: leading
aliases: [line spacing]
tags: [typography]
level: foundational
depth: deep
summary: Leading is the vertical space between lines of text, measured from one baseline to the next.
related: [line-height, tracking, baseline, measure]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Kerning, tracking, leading and spacing (TypeType)"
    url: https://typetype.org/blog/kerning-tracking-leading-and-spacing-in-typography/
    type: authority
license: CC-BY-4.0
---

## Definition
Leading is the vertical space between lines of text, measured from one baseline to the next.

## Why it matters
Leading controls how open or cramped a paragraph feels, and it can do more for readability than which font you picked. Too tight and the lines collide, so your eye loses its place jumping to the next line. Too loose and the lines drift apart until they stop reading as one paragraph. Nobody notices it when it's right; everybody feels it when it's wrong. The name is a nice bit of history: it comes from the strips of lead typesetters slid between rows of metal type to space them out.

## Example
Setting roughly 24px of line spacing on 16px text gives body copy comfortable room to breathe.

## Also called
In design tools and on the web, you set leading through the "line height" control, which measures it slightly differently. See [line-height](line-height.md).

## Common mistake
Leaving it on "Auto" and never revisiting it, or matching leading to the font size (single spacing), which is almost always too tight for more than a line or two of reading.

## In practice
For body text, a ratio of about 1.4 to 1.6 times the font size is a comfortable starting range, and it pairs naturally with a token approach: store line height as a unitless ratio so it scales with your font-size tokens instead of locking to pixels. Two things change the right value: longer line lengths want more leading (the eye needs a clearer runway to the next line), and scripts with tall ascenders or stacked marks need more vertical room. The mechanics of setting it live in [line-height](line-height.md).

## Related terms
[line-height](line-height.md) · [tracking](tracking.md) · [baseline](baseline.md) · [measure](measure.md)

## Further reading
- Foundations: [Kerning, tracking, leading and spacing (TypeType)](https://typetype.org/blog/kerning-tracking-leading-and-spacing-in-typography/)
