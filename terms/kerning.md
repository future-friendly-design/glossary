---
term: Kerning
slug: kerning
aliases: []
tags: [typography]
level: intermediate
depth: deep
summary: Kerning is the adjustment of space between two specific letters so their pairing looks evenly balanced.
related: [tracking, leading]
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

# Kerning

## Definition
Kerning is the adjustment of space between two specific letters so their pairing looks evenly balanced.

## Why it matters
Some letter pairs just don't sit well together. A capital "A" next to a "V", or a "T" leaning over an "o", can leave a gap that looks like someone hit the spacebar by accident. Kerning closes those gaps. The good news: most of the time you get it for free, because type designers bake kerning pairs into the font, so the spacing is handled before you touch the text. You mostly notice kerning when it's missing, and that's almost always at large sizes: logos, display headlines, the big stuff where one awkward gap is impossible to unsee.

## Example
In the word "Wave", the "Wa" can show a visible gap with kerning turned off. Kerning pulls the two letters closer so the spacing reads even.

## Common mistake
Reaching for tracking (or Figma's "Letter spacing") to fix one ugly gap. Tracking spaces out *everything* evenly, so you fix the one pair and quietly wreck the rest of the word. Kerning is the per-pair tool; tracking is the whole-run tool. Different knobs.

## In practice
For a design system, kerning is mostly a font-choice decision, not a per-component setting: pick families with well-built kerning tables and you inherit good spacing everywhere, no token required. Reserve manual kerning for display and brand assets (logos, large headlines) where the type is big enough that a gap shows. A quick check that anyone on the team can run: flip the text upside down, or blur your eyes until you stop reading words. Your brain switches from reading to seeing shapes, and uneven spacing pops out.

## Related terms
[Tracking](tracking.md) · [Leading](leading.md)

## Further reading
- Foundations: [Kerning, tracking, leading and spacing (TypeType)](https://typetype.org/blog/kerning-tracking-leading-and-spacing-in-typography/)
