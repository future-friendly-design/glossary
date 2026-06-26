---
term: Segmentation
slug: segmentation
aliases: [text segmentation, text boundaries]
tags: [i18n-engineering]
level: advanced
depth: deep
summary: Segmentation is the process of dividing text into meaningful units such as characters, words, or sentences.
related: [icu, cldr, internationalization, grapheme-cluster]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Intl.Segmenter (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Segmenter
    type: code
  - title: "UAX #29: Unicode Text Segmentation"
    url: https://unicode.org/reports/tr29/
    type: authority
license: CC-BY-4.0
---

# Segmentation

## Definition
Segmentation is the process of dividing text into meaningful units such as characters, words, or sentences.

### Why it matters in design systems
What counts as a character, word, or sentence boundary differs by writing system, so segmentation cannot rely on a simple rule like splitting on spaces. [Unicode](unicode.md) Standard Annex #29 defines default algorithms for [grapheme cluster](grapheme-cluster.md), word, and sentence boundaries, but it is explicit that scripts without spaces between words need dictionary-based tailoring rather than the default.<sup>1</sup>

So for a design system, anything that counts, truncates, or indexes text has to use a Unicode-aware segmenter. [Thai](thai-script.md), Japanese, and Chinese put no spaces between words, so word segmentation there needs a dictionary or model, not a delimiter, and even a single "character" can be a grapheme cluster of several code points.

### Example
Thai text runs words together with no spaces, so "คนไทย" cannot be split into words by looking for spaces; a segmentation algorithm is needed to find the boundaries.

### Common mistake
Splitting on whitespace to count words, truncate text, or build a search index. It silently fails for space-less scripts (producing one giant "word") and mishandles grapheme clusters at character level, so word counts, "read time" estimates, and search tokenization come out wrong for much of the world.

### In practice
- **Use a Unicode-aware segmenter:** in JavaScript, `Intl.Segmenter` with `granularity: "word"` (or `"sentence"`, `"grapheme"`) follows UAX #29; server-side, [ICU](icu.md) provides the same, including dictionary-based word breaking for Thai and CJK. See [Intl.Segmenter (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Segmenter).
- **Match the unit to the task:** count and truncate by grapheme cluster for "characters," segment by word for word counts and search, by sentence for snippets. Each is a different boundary.
- **Languages:** word segmentation quality is language-specific; confirm space-less scripts with the language experts and test with real content.

***

### Related terms and mentions
[CLDR](cldr.md) · [Grapheme cluster](grapheme-cluster.md) · [ICU](icu.md) · [Internationalization](internationalization.md) · [Internationalization & engineering](i18n-engineering.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Thai script](thai-script.md) · [Unicode](unicode.md)

### Further reading
- Code & specs: [Intl.Segmenter (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Segmenter)
- Foundations: [UAX #29: Unicode Text Segmentation](https://unicode.org/reports/tr29/)

### Sources
1. The default word-boundary rules are not adequate for scripts that lack spaces between words (such as Thai, Lao, Chinese, and Japanese), which require dictionary lookup or other mechanisms - Unicode Standard Annex #29: Unicode Text Segmentation [https://unicode.org/reports/tr29/](https://unicode.org/reports/tr29/)
