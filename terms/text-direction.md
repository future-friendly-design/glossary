---
term: Text direction
slug: text-direction
aliases: [writing direction, base direction, directionality]
tags: [characters-encoding]
level: foundational
depth: core
summary: Text direction is the way a script flows, such as left-to-right or right-to-left.
related: [bidirectional-text, complex-text-layout]
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
license: CC-BY-4.0
---

## Definition
Text direction is the way a script flows, such as left-to-right or right-to-left.

## Why it matters
Most scripts are written left-to-right (LTR), while Arabic, Hebrew, and others are right-to-left (RTL). A document or element also has a base direction that governs how mixed content and neutral characters are laid out. On the web you set base direction with the HTML `dir` attribute or the CSS `direction` property, and choosing it correctly is what makes [bidirectional-text](bidirectional-text.md) display properly. Direction is distinct from script: the same script can appear in either base direction depending on context, so it is a setting you make deliberately, not something the script alone decides.

## Example
Setting `dir="rtl"` on an Arabic paragraph makes it start at the right edge and align right.

## Related terms
[bidirectional-text](bidirectional-text.md) · [complex-text-layout](complex-text-layout.md)

## Further reading
- Code & specs: [dir (MDN HTML global attribute)](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)
- Foundations: [Structural markup and right-to-left text in HTML (W3C)](https://www.w3.org/International/questions/qa-html-dir)
