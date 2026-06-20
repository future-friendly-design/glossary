---
term: Stacking script
slug: stacking-script
aliases: [vertical stacking, stacked consonants]
tags: [shaping-layout]
level: advanced
depth: core
summary: A stacking script is one where consonants pile up vertically to form a cluster, as in Tibetan and many Indic scripts.
related: [conjunct, reordering, complex-text-layout, tsheg]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Requirements for Tibetan Text Layout (W3C)"
    url: https://www.w3.org/TR/tlreq/
    type: authority
license: CC-BY-4.0
---

## Definition
A stacking script is one where consonants pile up vertically to form a cluster, as in Tibetan and many Indic scripts.

## Why it matters
In stacking behavior, a consonant cluster is drawn with letters placed above and below each other rather than side by side, forming a single vertical stack. Tibetan stacks a root letter with subjoined consonants beneath it, and Indic scripts can stack [[conjunct]]s vertically. This complicates line height and glyph composition, and a practical tell of weak rendering support is stacks that come apart and sit horizontally instead. It is a reason vertical space and font support need real testing for these scripts, not Latin assumptions.

## Example
A Tibetan cluster with a subjoined consonant draws the second consonant directly beneath the first.

## Related terms
[[conjunct]] · [[reordering]] · [[complex-text-layout]] · [[tsheg]]

## Further reading
- Foundations: [Requirements for Tibetan Text Layout (W3C)](https://www.w3.org/TR/tlreq/)
