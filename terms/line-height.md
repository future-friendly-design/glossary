---
term: Line height
slug: line-height
aliases: [line spacing]
tags: [typography, figma, frontend, css]
level: foundational
depth: deep
summary: Line height is the property in CSS and design tools that sets the total vertical space a line of text occupies, including the text itself.
tool_names:
  figma: Line height
  css: line-height
related: [leading, vertical-trim, measure]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "line-height (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/line-height
    type: code
  - title: "Explore text properties (Figma Help)"
    url: https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties
    type: design-tool
  - title: "WCAG 2.1: 1.4.12 Text Spacing"
    url: https://www.w3.org/WAI/WCAG21/Understanding/text-spacing.html
    type: authority
  # type: resource -> empty until a matching pick exists in DS | Designer Resources;
  # a talk/guide on web vertical rhythm would fit here.
license: CC-BY-4.0
---

## Definition
Line height is the property in CSS and design tools that sets the total vertical space a line of text occupies, including the text itself.

## Why it matters
This is where leading actually gets set in the tools you use every day: the CSS `line-height` property and Figma's "Line height" control. Same goal as leading, give text room to breathe, but here's the subtlety that trips people up. Classic leading was the space *added between* lines. Line height is the height of the *whole* line box, text included. They aim at the same thing and measure it differently, which is exactly why "leading" and "line height" feel like they should be identical and then don't quite line up.

## Example
In CSS, `line-height: 1.5` on 16px text produces 24px line boxes. In Figma, setting Line height to 150% on 16px text does the same.

## Also called
Figma: Line height · CSS: `line-height`. The print-world term for the same idea is [[leading]].

## Common mistake
Treating leading and line height as the same number you can swap freely. They target the same look but measure differently, so a "20px of leading" mental model doesn't map cleanly onto `line-height: 20px`. The other classic trap is CSS-specific: a unitless `line-height: 1.5` scales with the font size, while `line-height: 24px` stays locked at 24 even when the text grows.

## In practice
Three connections worth building into a design system:
- **Tokens:** store line height as a unitless ratio (like `1.5`), not a pixel value, so it scales when font sizes change. Pixel-locked line heights are a common source of broken vertical rhythm in a token system.
- **Accessibility:** WCAG 2.1 (Success Criterion 1.4.12, Text Spacing) expects content to stay usable when a reader bumps line height to at least 1.5x the font size, so avoid layouts that clip or overlap when text spacing increases. See [Understanding 1.4.12](https://www.w3.org/WAI/WCAG21/Understanding/text-spacing.html). *(Verify exact wording before publish.)*
- **Languages:** scripts with tall ascenders or stacked diacritics (for example Thai, Devanagari, or Vietnamese with its layered marks) can clip at a line height tuned only for Latin text, so test multilingual content and give it more vertical room. *(Flag for the language experts to confirm specifics.)*

In Figma, "Auto" line height varies by typeface, so set an explicit value when you need consistency across fonts. The [MDN line-height page](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height) shows how the unit choices behave.

## Related terms
[[leading]] · [[vertical-trim]] · [[measure]]

## Further reading
- Code & specs: [line-height (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height)
- Design tools: [Explore text properties (Figma Help)](https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties)
- Foundations: [WCAG 2.1: 1.4.12 Text Spacing](https://www.w3.org/WAI/WCAG21/Understanding/text-spacing.html)
- *Resource library: (empty until a matching pick exists in DS | Designer Resources; a talk or guide on web vertical rhythm would fit here)*
