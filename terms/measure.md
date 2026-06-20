---
term: Measure
slug: measure
aliases: [line length]
tags: [typography]
level: intermediate
depth: deep
summary: Measure is the length of a line of text, usually counted in characters per line.
related: [leading, line-height]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Line length (Butterick's Practical Typography)"
    url: https://practicaltypography.com/line-length.html
    type: authority
  - title: "Measure, or line length (Google Fonts Knowledge)"
    url: https://fonts.google.com/knowledge/glossary/measure_line_length
    type: resource
license: CC-BY-4.0
---

## Definition
Measure is the length of a line of text, usually counted in characters per line.

## Why it matters
Measure is one of the quiet levers of readability. Lines that run too long tire the eye on the return sweep back to the start of the next line; lines that are too short chop up the reading rhythm. For body text the comfortable range is widely cited as roughly 45 to 75 characters per line, with about 66 often called the sweet spot for a single column. Butterick puts the workable range a little wider, at 45 to 90.

## Example
A body paragraph set to about 65 characters per line is easier to read than one stretching the full width of a wide screen.

## Common mistake
Letting body text run the full width of its container. On a large screen an unconstrained paragraph becomes a fatiguing 120-plus-character measure, even though nothing looks obviously broken. Text needs an explicit cap on its width; the container should not decide the measure for it.

## In practice
- **Tokens and CSS:** cap line length with the `ch` unit (for example `max-width: 66ch`), which tracks the font's character width, or apply a max-width token to text containers. This keeps the measure in the readable range across screen sizes.
- **Leading interaction:** as the measure widens, increase [leading](leading.md) (line height) so the reader can track from the end of one line back to the start of the next. Wide measure with tight [line-height](line-height.md) is hard to read.
- **Accessibility:** WCAG Success Criterion 1.4.8 (Visual Presentation, level AAA) calls for no more than 80 characters per line for blocks of text, which is a useful upper bound to design against. *(Confirm exact criterion wording before publish.)*

## Related terms
[leading](leading.md) · [line-height](line-height.md)

## Further reading
- Foundations: [Line length (Butterick's Practical Typography)](https://practicaltypography.com/line-length.html)
- Resource library: [Measure, or line length (Google Fonts Knowledge)](https://fonts.google.com/knowledge/glossary/measure_line_length)
