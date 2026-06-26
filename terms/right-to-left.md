---
term: Right-to-left
slug: right-to-left
aliases: [rtl]
tags: [writing-systems-scripts]
level: foundational
depth: core
summary: Right-to-left (RTL) is a text direction where a script is written and read from the right edge of the line to the left.
related: [text-direction, left-to-right, bidirectional-text, arabic-script, hebrew-script]
status: voice-passed
version_added: 0.1
updated: 2026-06-26
contributors: [sam-gordashko]
further_reading:
  - title: "dir (MDN HTML global attribute)"
    url: https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir
    type: code
  - title: "Structural markup and right-to-left text in HTML (W3C)"
    url: https://www.w3.org/International/questions/qa-html-dir
    type: authority
  - title: "Bidirectionality and RTL (Material Design 3)"
    url: https://m3.material.io/foundations/layout/bidirectionality-rtl
    type: resource
license: CC-BY-4.0
---

# Right-to-left

## Definition

Right-to-left (RTL) is a text direction where a script is written and read from the right edge of the line to the left.

For example, the [Arabic](arabic-script.md) and [Hebrew](hebrew-script.md) scripts run right to left.

### Why it matters in design systems

Several widely used scripts run right to left, including Arabic, Hebrew, Adlam, N'Ko, Syriac, and Thaana. On the web, right to left is never the default: you have to declare it with the `dir` attribute, because a language or script declaration alone does not set direction.<sup>1</sup>

So for a design system, supporting RTL is more than flipping the text. The whole layout mirrors, so spacing, alignment, and icons should be set with logical CSS properties rather than pinned to physical sides, and any [left-to-right](left-to-right.md) runs inside an RTL line, such as a brand name or a number, need the bidirectional algorithm to place them. That wider work is [bidirectional text](bidirectional-text.md), which is why declaring RTL is necessary but not sufficient on its own.

***

### Related terms and mentions

[Arabic script](arabic-script.md) · [Bidirectional text](bidirectional-text.md) · [Hebrew script](hebrew-script.md) · [Left-to-right](left-to-right.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Text direction](text-direction.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Code & specs: [dir (MDN HTML global attribute)](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)
* Foundations: [Structural markup and right-to-left text in HTML (W3C)](https://www.w3.org/International/questions/qa-html-dir)
* Resource library: [Bidirectionality and RTL (Material Design 3)](https://m3.material.io/foundations/layout/bidirectionality-rtl)

### Sources

1. Declaring the `dir` attribute is essential to support languages that use right-to-left scripts such as Adlam, Arabic, Hebrew, N'Ko, Syriac, and Thaana; a language declaration does not set directionality - Structural markup and right-to-left text in HTML (W3C) [https://www.w3.org/International/questions/qa-html-dir](https://www.w3.org/International/questions/qa-html-dir)
