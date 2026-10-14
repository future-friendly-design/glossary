---
term: Truncation
slug: truncation
aliases:
  - text truncation
  - ellipsis
level: foundational
depth: deep
summary: >-
  Truncation is cutting text short so it fits the space it is given, usually
  with an ellipsis (…) to show that some of it is hidden.
tool_names:
  figma: Truncate text
  css: text-overflow
related:
  - text-expansion
  - internationalization
  - pseudolocalization
  - grapheme-cluster
status: voice-passed
version_added: 0.1
updated: 2026-10-14T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: text-overflow (MDN)
    url: >-
      https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/text-overflow
    type: code
  - title: 'Understanding SC 1.4.4: Resize Text (W3C WAI)'
    url: https://www.w3.org/WAI/WCAG22/Understanding/resize-text.html
    type: authority
license: CC-BY-4.0
tags:
  - i18n-engineering
---

# Truncation

## Definition

Truncation is cutting text short so it fits the space it is given, usually with an ellipsis (…) to show that some of it is hidden.<sup>1</sup>

Truncation is one of the things [internationalization (i18n)](internationalization.md) has to plan for, because translated text is often longer and can be cut off.<sup>2</sup> Internationalization is the design and development work that makes a product able to be adapted to other languages and places.

When the styling of a page truncates text, the words are not deleted. They are still there, only hidden, and the end of the visible text is either replaced with an ellipsis or clipped,<sup>3</sup> and a clip can cut through the middle of a character.<sup>4</sup> Cutting text in code is different: the characters after the cut are gone.

A design system usually gives a component three choices when its text does not fit: wrap the text onto another line, let the box grow, or truncate the text.

### Why it matters in design systems

Most people have seen a long name in a narrow table column end in three dots. The dots tell the reader that something is missing, but not what.

Translation makes this come up far more often. Text translated from a compact language such as English grows the most when it is short,<sup>5</sup> and a translation three times as long is not unusual for a single word ([text expansion](text-expansion.md)).<sup>6</sup> A button that fit its label in the first language can show only the first few [symbols](../../language-terms/writing-systems-and-scripts/symbol.md) of the second.

Cutting text also has an accessibility side. W3C's accessibility guidance on resizing text says truncation is acceptable when the reader can still get to the full text, on focus (when they tab or click to it) or when they select it, and when something other than the cut itself tells them it is there.<sup>7</sup> A truncated label with no way to read the rest fails the reader who needs it.

Where the cut falls depends on the [script](../../language-terms/writing-systems-and-scripts/script.md) and the writing direction, in three ways:

* **The unit of the cut.** Software should cut between whole [grapheme clusters](../text-in-software/grapheme-cluster.md), the units a reader sees as single characters.<sup>8</sup> The Hindi greeting नमस्ते, written in [Devanagari](../../language-terms/writing-systems-and-scripts/devanagari.md), is three grapheme clusters, न, म and स्ते, but six [code points](../text-in-software/code-point.md), the numbers [Unicode](../text-in-software/unicode.md) gives each [character](../text-in-software/character.md). Cut after the fourth code point, it becomes नमस्, which ends on a [virama](../../language-terms/writing-systems-and-scripts/virama.md), the [mark](../../language-terms/writing-systems-and-scripts/mark.md) that cancels the vowel sound built into a consonant, in the middle of the third cluster.
* **The side of the cut.** The ellipsis goes at the end of the line,<sup>9</sup> and the end is not always the right-hand side. In [right-to-left](../../language-terms/writing-systems-and-scripts/right-to-left.md) text the end is on the left. In [vertical text](../../terms/vertical-text.md), such as [Mongolian](../../language-terms/writing-systems-and-scripts/mongolian-script.md), the line runs from top to bottom, so the end is at the bottom.<sup>10</sup> In a line that mixes both directions ([bidirectional text](../../language-terms/writing-systems-and-scripts/bidirectional-text.md)), the hidden characters are the ones that sit visually at the end.<sup>11</sup>
* **Where a word ends.** Cutting at the end of a whole word means finding where words end. [Thai](../../language-terms/writing-systems-and-scripts/thai-script.md) does not put spaces between words,<sup>12</sup> so finding a word's end takes [segmentation](../text-in-software/segmentation.md), the process of dividing text into words, which for Thai needs software that knows the language's words.

A truncation rule that was only tested in one language can break in all three ways at once, in a component that looks finished.

### Also called

Figma: Truncate text<sup>13</sup> · CSS: `text-overflow`

Both can also cut text after a set number of lines instead of one: Figma calls it Max lines, and CSS has `line-clamp`.<sup>14</sup>

### Common mistake

Cutting text to a fixed number of characters in code, such as "the first 20 characters". In JavaScript, the length of a piece of text counts [code units](../text-in-software/code-unit.md), the pieces a character is stored in, not the characters a reader sees.<sup>15</sup> A cut by that count can split an emoji or separate a symbol from its mark, so the reader sees a broken symbol before the ellipsis. Let the layout decide where to cut, or count grapheme clusters when a limit must be counted.

### In practice

* **Write the overflow rule into every component that holds text.** Say whether the text wraps, the box grows, or the text is truncated, and make truncation the last choice. Name the text that must never be truncated, such as button labels and error messages, because the cut part of those is often the meaning.
* **Choose the way back for each component.** A table cell or a navigation item can show its full text when it receives focus.<sup>16</sup> A truncated line inside a link, such as a headline on a card, can leave the full text to the page the link opens.<sup>17</sup>
* **Test with fake translations.** [Pseudolocalization](pseudolocalization.md) puts a marker at the start and end of every piece of text, often a bracket, so a missing end marker shows where text was truncated.<sup>18</sup>

***

### Related terms and mentions

[Bidirectional text](../../language-terms/writing-systems-and-scripts/bidirectional-text.md) · [Character](../text-in-software/character.md) · [Code point](../text-in-software/code-point.md) · [Code unit](../text-in-software/code-unit.md) · [Devanagari script](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Grapheme](../text-in-software/grapheme.md) · [Grapheme cluster](../text-in-software/grapheme-cluster.md) · [Internationalization (i18n)](internationalization.md) · [Language](../../language-terms/linguistics/language.md) · [Left-to-right](../../language-terms/writing-systems-and-scripts/left-to-right.md) · [Localization (l10n)](localization.md) · [Mark](../../language-terms/writing-systems-and-scripts/mark.md) · [Mongolian script](../../language-terms/writing-systems-and-scripts/mongolian-script.md) · [Pseudolocalization](pseudolocalization.md) · [Right-to-left](../../language-terms/writing-systems-and-scripts/right-to-left.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Segmentation](../text-in-software/segmentation.md) · [Surrogate pair](../text-in-software/surrogate-pair.md) · [Symbol](../../language-terms/writing-systems-and-scripts/symbol.md) · [Text direction](../../language-terms/writing-systems-and-scripts/text-direction.md) · [Text expansion](text-expansion.md) · [Thai script](../../language-terms/writing-systems-and-scripts/thai-script.md) · [Unicode](../text-in-software/unicode.md) · [Vertical text](../../terms/vertical-text.md) · [Virama](../../language-terms/writing-systems-and-scripts/virama.md) · [Internationalization & localization terms](./)

### Further reading

* Code: [text-overflow (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/text-overflow)
* Foundations: [Understanding SC 1.4.4: Resize Text (W3C WAI)](https://www.w3.org/WAI/WCAG22/Understanding/resize-text.html)

### Sources

1. "A common convention if text exceeds its space is to replace truncated text with an ellipsis" - Understanding SC 1.4.12: Text Spacing, W3C Web Accessibility Initiative [https://www.w3.org/WAI/WCAG22/Understanding/text-spacing.html](https://www.w3.org/WAI/WCAG22/Understanding/text-spacing.html)
2. "Expand the string to simulate the longer strings that can result from translation. Expanded strings reveal layout and truncation issues" - Pseudolocalization, Microsoft Learn [https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization](https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization)
3. "The text-overflow property sets how hidden overflow content is signaled to users. It can be clipped, display an ellipsis (…), or display a custom string" - text-overflow, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/text-overflow](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/text-overflow)
4. "Characters may be only partially rendered" - CSS Overflow Module Level 3, section text-overflow (clip), W3C [https://www.w3.org/TR/css-overflow-3/](https://www.w3.org/TR/css-overflow-3/)
5. "the smaller the source message, the higher the likely translation length" - Text size in translation, W3C Internationalization [https://www.w3.org/International/articles/article-text-size](https://www.w3.org/International/articles/article-text-size)
6. "The 300% expansion from English to Italian is not at all surprising for a small string such as this" - Text size in translation, W3C Internationalization [https://www.w3.org/International/articles/article-text-size](https://www.w3.org/International/articles/article-text-size)
7. "truncation is acceptable if the component's full content is available on focus or after user activation and an indication that this information can be accessed, is provided to the user in some way besides the fact that it is truncated" - Understanding SC 1.4.4: Resize Text, W3C Web Accessibility Initiative [https://www.w3.org/WAI/WCAG22/Understanding/resize-text.html](https://www.w3.org/WAI/WCAG22/Understanding/resize-text.html)
8. "The term "character" is used in this property definition for better readability and means "grapheme cluster" \[UAX29] for implementation purposes" - CSS Overflow Module Level 3, section text-overflow, W3C [https://www.w3.org/TR/css-overflow-3/](https://www.w3.org/TR/css-overflow-3/)
9. "place the ellipsis immediately adjacent to the end edge of the remaining inline content" - CSS Overflow Module Level 3, section text-overflow, W3C [https://www.w3.org/TR/css-overflow-3/](https://www.w3.org/TR/css-overflow-3/)
10. "Mongolian-based systems are typically written using a top-to-bottom inline direction with a rightward (left-to-right) block flow direction" - CSS Writing Modes Level 4, W3C [https://www.w3.org/TR/css-writing-modes-4/](https://www.w3.org/TR/css-writing-modes-4/)
11. "These examples demonstrate which characters get hidden to make room for the ellipsis in a bidi situation: those visually at the end edge of the line" - CSS Overflow Module Level 3, section text-overflow, W3C [https://www.w3.org/TR/css-overflow-3/](https://www.w3.org/TR/css-overflow-3/)
12. "Thai words are not separated by spaces" - The Unicode Standard, Version 18.0, Chapter 16: Southeast Asia-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-16/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-16/)
13. "Toggle Truncate text to hide any content that goes beyond the maximum number of lines" - Explore text properties, Figma Help Center [https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties](https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties)
14. "The line-clamp CSS property allows limiting of the contents of a block to the specified number of lines" - line-clamp, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/line-clamp](https://developer.mozilla.org/en-US/docs/Web/CSS/line-clamp)
15. "This property returns the number of code units in the string" - String: length, MDN [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length)
16. "a mechanism is provided to reveal the truncated text on the page (for instance, the text appears on focus or on activation)" - Understanding SC 1.4.12: Text Spacing, W3C Web Accessibility Initiative [https://www.w3.org/WAI/WCAG22/Understanding/text-spacing.html](https://www.w3.org/WAI/WCAG22/Understanding/text-spacing.html)
17. "where the ellipsis is part of a section of content which includes a link, the truncated text is revealed on the linked page" - Understanding SC 1.4.12: Text Spacing, W3C Web Accessibility Initiative [https://www.w3.org/WAI/WCAG22/Understanding/text-spacing.html](https://www.w3.org/WAI/WCAG22/Understanding/text-spacing.html)
18. "Wrapping a string instantly reveals truncations in the product user interface because the delimiter is missing" - Pseudolocalization, Microsoft Learn [https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization](https://learn.microsoft.com/en-us/globalization/methodology/pseudolocalization)
