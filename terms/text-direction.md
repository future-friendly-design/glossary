---
term: Text direction
slug: text-direction
aliases: [writing direction, base direction, directionality]
tags: [writing-systems-scripts]
level: foundational
depth: core
summary: Text direction is the way a script flows, such as left-to-right or right-to-left.
related: [bidirectional-text, complex-text-layout, left-to-right, right-to-left]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
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

# Text direction

## Definition

Text direction is the way a script flows, such as left-to-right or right-to-left.

For example, [Latin](latin-script.md) runs [left to right](left-to-right.md), while [Arabic](arabic-script.md) and [Hebrew](hebrew-script.md) run [right to left](right-to-left.md).

### Why it matters in design systems

A [script](../language-terms/writing-systems-and-scripts/script.md) has a natural direction, but the direction of a whole paragraph or element is a separate setting, called its base direction, and you have to set it on purpose. The same script can sit in either base direction depending on context, so the script alone does not decide it. On the web you set base direction with the HTML `dir` attribute or the CSS `direction` property. The W3C is explicit that a language or script declaration does not set direction; you must always declare it yourself.<sup>1</sup>

Base direction is also what makes mixed text come out right. When one line holds both directions, such as an Arabic sentence with an English brand name in it, the [Unicode Bidirectional Algorithm](bidirectional-text.md) uses the base direction to work out the visual order and to resolve neutral characters like spaces and punctuation.<sup>2</sup>

So for a design system, getting direction right is necessary but not sufficient. Setting the base direction is the first decision. A layout that truly flips also needs logical CSS properties, such as `margin-inline` and `text-align: start`, so spacing and alignment follow the text instead of being pinned to the left edge. That groundwork is what makes [complex text layout](complex-text-layout.md) possible.

***

### Related terms and mentions

[Arabic script](arabic-script.md) · [Bidirectional text](bidirectional-text.md) · [Complex text layout](complex-text-layout.md) · [Hebrew script](hebrew-script.md) · [Latin script](latin-script.md) · [Left-to-right](left-to-right.md) · [Right-to-left](right-to-left.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Code & specs: [dir (MDN HTML global attribute)](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)
* Foundations: [Structural markup and right-to-left text in HTML (W3C)](https://www.w3.org/International/questions/qa-html-dir)
* Resource library: [Bidirectionality and RTL (Material Design 3)](https://m3.material.io/foundations/layout/bidirectionality-rtl)

### Sources

1. A language or script declaration does not set text direction; the base direction must be declared with the `dir` attribute - Structural markup and right-to-left text in HTML (W3C) [https://www.w3.org/International/questions/qa-html-dir](https://www.w3.org/International/questions/qa-html-dir)
2. The Unicode Bidirectional Algorithm reorders text for display from the prevailing base direction, which also resolves neutral characters such as spaces and punctuation - Unicode Bidirectional Algorithm basics (W3C) [https://www.w3.org/International/articles/inline-bidi-markup/uba-basics](https://www.w3.org/International/articles/inline-bidi-markup/uba-basics)
