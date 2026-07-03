---
term: Bidirectional text
slug: bidirectional-text
aliases:
  - bidi
  - bidi text
level: advanced
depth: deep
summary: >-
  Bidirectional text mixes left-to-right and right-to-left text in the same
  line.
related:
  - text-direction
  - unicode
  - complex-text-layout
  - left-to-right
  - right-to-left
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: unicode-bidi (MDN)
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi
    type: code
  - title: Unicode Bidirectional Algorithm basics (W3C)
    url: https://www.w3.org/International/articles/inline-bidi-markup/uba-basics
    type: authority
  - title: Bidirectionality and RTL (Material Design 3)
    url: https://m3.material.io/foundations/layout/bidirectionality-rtl
    type: resource
license: CC-BY-4.0
tags:
  - writing-systems-scripts
  - shaping-layout
  - i18n-engineering
---

# Bidirectional text

## Definition

Bidirectional text refers to the [text direction](text-direction.md) [script rule](script-rules.md) where both [left-to-right (LTR) ](left-to-right.md)and [right-to-left (RTL)](right-to-left.md) text appears in the same line.&#x20;

For example, a line like `مرحبا iPhone 2026` mixes an Arabic greeting (right to left) with a Latin-script brand name and digits (left to right).

### Why it matters in design systems

Scripts like [Arabic](../../terms/arabic-script.md) and [Hebrew](../../terms/hebrew-script.md) run right-to-left, but numbers and embedded [Latin-script](../../terms/latin-script.md) text run left-to-right. So the order the characters are stored in, called the logical order, is not the order they are displayed in, called the visual order.

A computer cannot guess that order. [Unicode](../../terms/unicode.md), the universal computer programming standard that assigns every symbol a unique ID number, has a Bidirectional Algorithm that considers each character's direction property and the [base direction](text-direction.md) of the line to resolve neutral characters like spaces and punctuation that sit between text of opposite directions.<sup>1</sup> Setting that base direction correctly is what keeps mixed text from coming out scrambled.

Bidirectional text is a property of your content, not a mode you switch on. The moment a right-to-left interface shows a Latin-script brand name, a username, a URL, or a price, a single line of text carries both directions, and that turns up in real data whether or not anyone planned for it.

So in a design-system, components and content slots have to hold mixed, and often unknown, text direction: text inputs, list rows, tables, breadcrumbs, tags, anything that displays user data or identifiers. Ideally these components get designed and reviewed with the bidirectional text content, and their spacing and alignment design decisions are given names that refer to a logical position (for example, start and end) rather than left and right, so one layout serves both directions.&#x20;

Bidirectional text is only the content-level reality here; mirroring the wider layout and flipping directional icons is the system-level response, which makes bidirectional text part of a [complex text layout](../../terms/complex-text-layout.md).

### Example

Take an English sentence with an Arabic phrase dropped into it, such as `The title is مفتاح معايير الويب in Arabic`. Its base direction is left to right, so the line reads left to right overall, but the embedded Arabic phrase مفتاح معايير الويب runs right to left inside it.<sup>2</sup>

That reordering is also why punctuation can land in the wrong spot. A comma that belongs to the English sentence correctly sits to the right of the Arabic, because as a neutral character between opposite-direction runs it takes on the left-to-right base direction.<sup>3</sup> The trap is punctuation that belongs to the embedded run itself: if the Arabic phrase ended with an exclamation mark you would expect it at the left edge of the Arabic, but by default it is treated the same way and lands on the right instead.<sup>4</sup> Setting the base direction correctly, and isolating each embedded run, is what keeps the brand name, the digits, and the punctuation in the right place.

### Common mistake

Assuming that marking the block right to left is enough, and the algorithm will handle whatever goes inside it. The real trap is concatenation: building a string from data whose direction you do not control, a user name, a file path, a URL, or a translated label, and inserting it without isolating it. A run whose direction disagrees with the surrounding line reorders against its neighbours, and the block direction you set does nothing to contain it; each inserted run of unknown direction has to be isolated on its own.

### In practice

* **Set base direction; do not fight the algorithm:** use the HTML `dir` attribute (or `dir="auto"` for data whose direction you do not know) and the CSS `direction` property, the text direction concept. Avoid manually overriding `unicode-bidi`, which MDN flags as not intended for web authors.
* **Isolate embedded runs:** wrap inserted opposite- or unknown-direction content (user names, brands, paths) in a `<bdi>` element<sup>5</sup> or `unicode-bidi: isolate`<sup>6</sup> so it cannot disturb the surrounding text.
* **Use logical CSS properties:** `margin-inline`, `text-align: start`, and the like let a layout flip correctly between [left-to-right](left-to-right.md) and [right-to-left](right-to-left.md) instead of being pinned to physical sides. This is part of [complex text layout](../../terms/complex-text-layout.md). Confirm right-to-left behaviour with readers of those languages.

***

### Related terms and mentions

[Arabic script](../../terms/arabic-script.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Hebrew script](../../terms/hebrew-script.md) · [Latin script](../../terms/latin-script.md) · [Left-to-right](left-to-right.md) · [Right-to-left](right-to-left.md) · [Script rules](script-rules.md) · [Text direction](text-direction.md) · [Unicode](../../terms/unicode.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [unicode-bidi (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi)
* Foundations: [Unicode Bidirectional Algorithm basics (W3C)](https://www.w3.org/International/articles/inline-bidi-markup/uba-basics)
* Resource library: [Bidirectionality and RTL (Material Design 3)](https://m3.material.io/foundations/layout/bidirectionality-rtl)

### Sources

1. The order of characters in memory (logical order) is not the same as the order in which they are displayed (visual order); a neutral character between two strong characters of the same direction assumes that direction and extends the run, while a neutral between opposite-direction runs is treated as having the prevailing base direction - Unicode Bidirectional Algorithm basics (W3C) [https://www.w3.org/International/articles/inline-bidi-markup/uba-basics](https://www.w3.org/International/articles/inline-bidi-markup/uba-basics)
2. When an Arabic phrase such as مفتاح معايير الويب is embedded in a left-to-right sentence, the Arabic runs right to left while the surrounding text runs left to right - Unicode Bidirectional Algorithm basics (W3C) [https://www.w3.org/International/articles/inline-bidi-markup/uba-basics](https://www.w3.org/International/articles/inline-bidi-markup/uba-basics)
3. A comma added after the last Arabic character is regarded as left to right (the base direction) and is therefore displayed to the right of the Arabic text, as part of the right-hand directional run - Unicode Bidirectional Algorithm basics (W3C) [https://www.w3.org/International/articles/inline-bidi-markup/uba-basics](https://www.w3.org/International/articles/inline-bidi-markup/uba-basics)
4. An exclamation mark ending an Arabic title is treated just like that comma and ends up to the right of the Arabic by default, rather than at the left edge where it belongs - Unicode Bidirectional Algorithm basics (W3C) [https://www.w3.org/International/articles/inline-bidi-markup/uba-basics](https://www.w3.org/International/articles/inline-bidi-markup/uba-basics)
5. The `bdi` element tells the bidirectional algorithm to treat the text it contains in isolation, so its direction neither influences nor is influenced by the surrounding text - bdi (MDN) [https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/bdi](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/bdi)
6. The `unicode-bidi: isolate` value calculates the element's directionality without considering its content, isolating it from its siblings - unicode-bidi (MDN) [https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi](https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi)
