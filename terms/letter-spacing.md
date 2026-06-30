---
term: Letter spacing
slug: letter-spacing
aliases: []
level: foundational
depth: deep
summary: >-
  Letter spacing is the design-tool and CSS control that adds or removes uniform
  space between every character in a run of text.
tool_names:
  figma: Letter spacing
  css: letter-spacing
related:
  - tracking
  - kerning
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: letter-spacing (MDN)
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing
    type: code
  - title: Explore text properties (Figma Help)
    url: >-
      https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties
    type: design-tool
  - title: 'WCAG 2.1: 1.4.12 Text Spacing'
    url: https://www.w3.org/WAI/WCAG21/Understanding/text-spacing.html
    type: authority
license: CC-BY-4.0
tags:
  - typography
  - figma
  - frontend
  - css
---

# Letter spacing

## Definition

Letter spacing is the design-tool and CSS control that adds or removes uniform space between every character in a run of text.

## Why it matters

This is the field you reach for in Figma, or the property you set in CSS, when you want to open up or tighten text evenly. It is the implementation of the typographic idea called [tracking](../language-terms/writing-systems-and-scripts/tracking.md): tracking is the concept, letter spacing is the control. Knowing they are the same thing (and that neither is [kerning](kerning.md), which adjusts single pairs) saves a lot of confusion when a designer and a developer are describing the same text with different words.

## Example

In Figma, a small positive Letter spacing on an all-caps label spreads its characters apart evenly. On the web, `letter-spacing: 0.05em` does the same.

## Also called

Figma: Letter spacing · CSS: `letter-spacing`. The typographic term for the concept this controls is [tracking](../language-terms/writing-systems-and-scripts/tracking.md).

## Common mistake

Confusing it with kerning: letter spacing is uniform across the whole run, kerning adjusts single pairs. On the web, a second trap is setting it in pixels (`letter-spacing: 1px`) so it does not scale with the font size. And applying it to body text by reflex, where even a little too much hurts readability.

## In practice

* **Tokens:** use `em` units (like `0.05em`) so the spacing scales with the font size, and bake the common values into your type styles (a small positive value on label and overline styles, none on body). Pixel values lock the spacing and break under scaling.
* **Accessibility:** WCAG 2.1 (Success Criterion 1.4.12, Text Spacing) expects content to stay usable when a reader sets letter spacing to at least 0.12 times the font size, so avoid layouts that clip or overflow when text spacing increases. See [Understanding 1.4.12](https://www.w3.org/WAI/WCAG21/Understanding/text-spacing.html). _(Verify exact value before publish.)_
* **Languages:** letter spacing assumes letters that sit apart, like Latin. Applying a blanket value to connected or complex scripts can break them: Arabic letters that should join can come apart, and Indic conjuncts can be disrupted. Do not apply uniform letter spacing to multilingual text without testing. _(Flag for the language experts to confirm specifics.)_

In Figma the field is "Letter spacing," set in pixels or as a percentage of font size. The [MDN letter-spacing page](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing) covers the CSS behavior.

## Related terms

[Tracking](../language-terms/writing-systems-and-scripts/tracking.md) · [Kerning](kerning.md)

## Further reading

* Code & specs: [letter-spacing (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing)
* Design tools: [Explore text properties (Figma Help)](https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties)
* Foundations: [WCAG 2.1: 1.4.12 Text Spacing](https://www.w3.org/WAI/WCAG21/Understanding/text-spacing.html)
* _Resource library: (empty until a matching pick exists in DS | Designer Resources)_
