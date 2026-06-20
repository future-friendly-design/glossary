---
term: Vertical trim
slug: vertical-trim
aliases: [leading trim, leading-trim]
tags: [typography]
level: advanced
depth: deep
summary: Vertical trim removes the extra space a font reserves above and below its letters so text aligns to cap height and baseline.
tool_names:
  figma: Vertical trim
  css: text-box-trim
related: [cap-height, baseline, line-height, leading]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "text-box-trim (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/text-box-trim
    type: code
  - title: "Explore text properties (Figma Help)"
    url: https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties
    type: design-tool
license: CC-BY-4.0
---

## Definition
Vertical trim removes the extra space a font reserves above and below its letters so text aligns to cap height and baseline.

## Why it matters
Every font builds in space above the [[cap-height]] and below the [[baseline]]. It stays invisible until you try to center a label in a button or stack text tightly, and the text sits slightly off no matter what padding you use. Vertical trim strips that reserved space so the text aligns to its actual cap height and baseline, which is what finally makes optical centering predictable instead of a hand-tuning exercise.

## Example
Enabling vertical trim on a button label optically centers the text without hand-tuning the padding.

## Also called
Figma: Vertical trim · CSS: `text-box-trim`. The earlier proposed CSS names were `leading-trim` and `text-edge`; the feature was renamed to `text-box-trim` and `text-box-edge` (shorthand `text-box`).

## Common mistake
Copying the trimmed look from a Figma mockup straight into CSS and assuming it just works. The CSS that maps to it (`text-box-trim` with `text-box-edge`) is still limited in availability, so it does not work in every major browser yet. Teams often fall back to fixed heights, zero-line-height tricks, or a library like Capsize. If designers do not flag that a component uses vertical trim, the build quietly drifts from the design.

## In practice
- **Tools:** in Figma, vertical trim is set to "Cap height to baseline" and trims the space from the first and last lines. The [Bejamas walkthrough](https://bejamas.com/blog/everything-you-need-to-know-about-figma-s-vertical-trim-feature) shows enabling it step by step; [Explore text properties (Figma Help)](https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties) covers the surrounding text controls.
- **CSS:** it maps to `text-box-trim` and `text-box-edge` (formerly `leading-trim` / `text-edge`), which are not yet widely supported. Check browser support before relying on them in production. See [text-box-trim (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/text-box-trim).
- **Tokens and handoff:** treat "uses vertical trim" as part of the component spec and call it out at handoff. It changes the box model a developer has to reproduce, so a value copied from Dev Mode without that context will not behave the same in the browser.

## Related terms
[[cap-height]] · [[baseline]] · [[line-height]] · [[leading]]

## Further reading
- Code & specs: [text-box-trim (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/text-box-trim)
- Design tools: [Explore text properties (Figma Help)](https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties)
