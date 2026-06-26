---
term: Baseline
slug: baseline
aliases: []
tags: [typography]
level: foundational
depth: deep
summary: The baseline is the invisible line that most letters sit on.
related: [cap-height, x-height, ascender, descender, leading, vertical-trim, hanging-baseline]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Baseline (Google Fonts Knowledge)"
    url: https://fonts.google.com/knowledge/glossary/baseline
    type: resource
license: CC-BY-4.0
---

# Baseline

## Definition
The baseline is the invisible line that most letters sit on.

## Why it matters
The baseline is the anchor the whole vertical system is measured from. [x-height](x-height.md), [cap-height](cap-height.md), and the reach of [ascender](ascender.md)s and [descender](descender.md)s are all distances from it, and line spacing is measured baseline to baseline. Most letters rest on it; descenders, like the tails of "g," "p," and "y," drop below it. Once you can see the baseline, a lot of vertical alignment stops being guesswork.

## Example
The bottoms of "o," "n," and "m" rest on the baseline, while the tail of "g" hangs below it.

## Common mistake
Treating the baseline as the bottom of the text. It is not: descenders extend below it, and the font also reserves extra space above and below the letters on top of that. That reserved space is why a line of text rarely sits where you expect inside a fixed-height box, and why centering a label often needs a nudge.

## In practice
- **Tools and tokens:** the baseline is what [vertical-trim](vertical-trim.md) and the CSS `text-box-trim` feature align to when they strip a font's built-in over and under space, so a label sits optically centered in a button with no manual padding. That makes the baseline the reference point for tight, predictable vertical rhythm.
- **Line spacing:** because leading is measured baseline to baseline, the baseline is the reference for [line-height](line-height.md) and [leading](leading.md). Reasoning about spacing in baseline terms is more reliable than eyeballing the gap between lines.
- **Languages:** the single sit-on-the-line baseline is a Latin-centric model. Some scripts align differently (Devanagari hangs its letters from a top line, a [hanging baseline](hanging-baseline.md), rather than sitting them on a bottom one), so do not assume every script shares one baseline behaviour. Confirm with the script experts for multilingual work.

## Related terms
[Cap height](cap-height.md) · [x-height](x-height.md) · [Ascender](ascender.md) · [Descender](descender.md) · [Hanging baseline](hanging-baseline.md) · [Leading](leading.md) · [Vertical trim](vertical-trim.md)

## Further reading
- Resource library: [Baseline (Google Fonts Knowledge)](https://fonts.google.com/knowledge/glossary/baseline)
