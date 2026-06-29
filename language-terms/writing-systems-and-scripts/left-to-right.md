---
term: Left-to-right
slug: left-to-right
aliases:
  - ltr
level: foundational
depth: core
summary: >-
  Left-to-right (LTR) is a text direction where a script is written and read
  from the left edge of the line to the right.
related:
  - text-direction
  - right-to-left
  - bidirectional-text
status: voice-passed
version_added: 0.1
updated: 2026-06-26T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: dir (MDN HTML global attribute)
    url: https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir
    type: code
  - title: Structural markup and right-to-left text in HTML (W3C)
    url: https://www.w3.org/International/questions/qa-html-dir
    type: authority
  - title: Bidirectionality and RTL (Material Design 3)
    url: https://m3.material.io/foundations/layout/bidirectionality-rtl
    type: resource
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Left-to-right

## Definition

Left-to-right (LTR) refers to the text direction script rule that defines reading and writing the script in horizontal lines running from left to right.&#x20;

For example, the [Latin](../../terms/latin-script.md) script used for English runs left to right.

### Why it matters in design systems

Most of the world's scripts run left to right, and on the web left to right is the default [base direction](text-direction.md) when none is set.<sup>1</sup> Because it is the default, LTR rarely asks you to make a decision, which is exactly why it is easy to bake in by accident.

So for a design system, the risk is building as if LTR is the only direction. A layout pinned to the left edge breaks the moment it meets a [right-to-left](right-to-left.md) script. Setting direction with logical CSS properties (such as `text-align: start` and `margin-inline`) lets the same layout serve both directions, so supporting LTR is necessary but not sufficient on its own.

***

### Related terms and mentions

[Bidirectional text](bidirectional-text.md) · [Latin script](../../terms/latin-script.md) · [Right-to-left](right-to-left.md) · [Script rules](script-rules.md) · [Text direction](text-direction.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [dir (MDN HTML global attribute)](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)
* Foundations: [Structural markup and right-to-left text in HTML (W3C)](https://www.w3.org/International/questions/qa-html-dir)
* Resource library: [Bidirectionality and RTL (Material Design 3)](https://m3.material.io/foundations/layout/bidirectionality-rtl)

### Sources

1. In the absence of a `dir` attribute, the base direction of text is left-to-right - Structural markup and right-to-left text in HTML (W3C) [https://www.w3.org/International/questions/qa-html-dir](https://www.w3.org/International/questions/qa-html-dir)
