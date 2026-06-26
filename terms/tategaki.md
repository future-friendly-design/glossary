---
term: Tategaki
slug: tategaki
aliases: [vertical writing, 縦書き]
tags: [writing-systems-scripts, shaping-layout]
level: advanced
depth: deep
summary: Tategaki is vertical writing, set top to bottom with columns running right to left, traditional in Japanese and other East Asian scripts.
related: [full-width, font-coverage]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "writing-mode (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode
    type: code
  - title: "Vertical text (W3C Internationalization)"
    url: https://www.w3.org/International/articles/vertical-text/
    type: authority
license: CC-BY-4.0
---

# Tategaki

## Definition

Tategaki is vertical writing, set top to bottom with columns running right to left, traditional in Japanese and other East Asian scripts.

For example, a Japanese novel is typically set in tategaki, read down each column and then leftward to the next.

### Why it matters in design systems

Tategaki was long the standard for Japanese and is still everywhere in novels, newspapers, manga, signage, and formal correspondence, while horizontal writing (yokogaki) became common later. The direction reshapes the whole object: a book set in tategaki binds on the right and its pages advance leftward, the reverse of an English book.

It is also not a rotation. In vertical text, ordinary digits lie on their side by default while fullwidth digits and enclosed numbers stand upright, and short runs of Latin letters or numbers are set upright in a horizontal cluster called tate-chu-yoko.<sup>1</sup> Each of those follows its own rule, so turning a horizontal block ninety degrees produces something a reader of the script sees as wrong.

So for a design system, setting the writing direction is necessary but not sufficient. CSS `writing-mode: vertical-rl` is what makes vertical layout possible on the web,<sup>2</sup> but the rest of the component, scroll direction, form controls, line breaking, and bidirectional runs, all shift with it. [CJK](cjk.md) products often need both directions, so vertical layout is a real requirement to design and test for, not a niche.

### Example

A Japanese novel is typically set in tategaki, read top to bottom and right to left. A short run of Western digits inside it, such as a year, is set upright as one horizontal cluster (tate-chu-yoko) rather than tipped on its side.

### Common mistake

Assuming vertical text is just horizontal text rotated ninety degrees. It is not: individual glyph orientation, punctuation placement, and runs of embedded Latin letters or numbers all follow their own rules.<sup>1</sup> Rotating a whole text block produces something a reader of the script will see as wrong.

### In practice

* **CSS:** `writing-mode: vertical-rl` sets top-to-bottom, right-to-left flow, and `text-orientation` controls whether embedded Latin stands upright or lies on its side. Prefer logical (flow-relative) CSS properties so the layout adapts instead of being pinned to physical sides.
* **UI:** vertical text changes more than the paragraph. Scroll direction, form controls, line breaking, and bidirectional runs all shift, so test the whole component in vertical mode, not just the body copy.
* **Languages:** whether tategaki or yokogaki is expected is a culturally specific judgment, so confirm the usage with readers of the language rather than guessing from the general rule.

***

### Related terms and mentions

[CJK](cjk.md) · [Font coverage](font-coverage.md) · [Full-width](full-width.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Code & specs: [writing-mode (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode)
* Foundations: [Vertical text (W3C Internationalization)](https://www.w3.org/International/articles/vertical-text/)

### Sources

1. In vertical text, ordinary number digits lie on their side by default whereas fullwidth digits and enclosed alphanumerics are upright by default, and short horizontal runs (tate-chu-yoko) are produced with `text-combine-upright` - Vertical text (W3C Internationalization) [https://www.w3.org/International/articles/vertical-text/](https://www.w3.org/International/articles/vertical-text/)
2. In Japanese, Chinese, and Korean the lines run right to left, set in CSS with `writing-mode: vertical-rl` - Vertical text (W3C Internationalization) [https://www.w3.org/International/articles/vertical-text/](https://www.w3.org/International/articles/vertical-text/)
