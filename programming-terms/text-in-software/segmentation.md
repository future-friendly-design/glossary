---
term: Segmentation
slug: segmentation
aliases:
  - text segmentation
  - text boundaries
level: advanced
depth: deep
summary: >-
  Segmentation is the process of dividing text into meaningful units such as
  characters, words, or sentences.
related:
  - icu
  - cldr
  - internationalization
  - grapheme-cluster
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Intl.Segmenter (MDN)
    url: >-
      https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Segmenter
    type: code
  - title: 'UAX #29: Unicode Text Segmentation'
    url: https://unicode.org/reports/tr29/
    type: authority
license: CC-BY-4.0
tags:
  - i18n-engineering
---

# Segmentation

## Definition

Segmentation is the process of dividing text into meaningful units such as characters, words, or sentences.

### Why it matters in design systems

Finding where one word ends and the next begins looks like a solved problem if you have only ever read English: cut the line at the spaces. That rule does not work for every language. Writing in [Thai](../../language-terms/writing-systems-and-scripts/thai-script.md), Lao, Chinese, and Japanese runs words together with no spaces at all, and even the smaller job, finding where one "character" ends, stops being obvious once a single written unit can be built out of several pieces.

So what counts as a "character", word, or sentence boundary differs by [writing system](../../language-terms/writing-systems-and-scripts/writing-system.md), and segmentation cannot rely on a simple rule like splitting on spaces. [Unicode](unicode.md) Standard Annex #29 defines default algorithms for [grapheme cluster](grapheme-cluster.md) boundaries (the unit a reader counts as one character), word boundaries, and sentence boundaries,<sup>1</sup> but it is explicit that scripts without spaces between words need dictionary-based tailoring rather than the default.<sup>2</sup>

So for a design system, anything that counts, truncates, or indexes text has to use a Unicode-aware segmenter. Thai, Japanese, and Chinese put no spaces between words, so word segmentation there needs a dictionary or a model, not a delimiter, and even a single "character" can be a grapheme cluster made of several stored characters.

### Example

Thai text runs words together with no spaces, so "คนไทย" cannot be split into words by looking for spaces; a segmentation algorithm is needed to find the boundaries.

### Common mistake

Splitting on whitespace to count words, truncate text, or build a search index. It silently fails for space-less scripts (producing one giant "word") and mishandles grapheme clusters at character level, so word counts, "read time" estimates, and search tokenization come out wrong for much of the world.

### In practice

* **Use a Unicode-aware segmenter:** in JavaScript, `Intl.Segmenter` with `granularity: "word"` (or `"sentence"`, `"grapheme"`) builds on the UAX #29 defaults;<sup>3</sup> server-side, [ICU](../internationalization-and-localization/icu.md) provides the same, including dictionary-based word breaking for Thai and CJK.<sup>4</sup> See [Intl.Segmenter (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Segmenter).
* **Match the unit to the task:** count and truncate by grapheme cluster for "characters," segment by word for word counts and search, by sentence for snippets. Each is a different boundary.
* **Languages:** word segmentation quality is language-specific; confirm space-less scripts with the language experts and test with real content.

***

### Related terms and mentions

[Character](character.md) · [CJK](../../language-terms/writing-systems-and-scripts/cjk.md) · [CLDR](../internationalization-and-localization/cldr.md) · [Grapheme cluster](grapheme-cluster.md) · [ICU](../internationalization-and-localization/icu.md) · [Internationalization (i18n)](../internationalization-and-localization/internationalization.md) · [Language](../../language-terms/linguistics/language.md) · [Script rules](../../language-terms/writing-systems-and-scripts/script-rules.md) · [Thai script](../../language-terms/writing-systems-and-scripts/thai-script.md) · [Unicode](unicode.md) · [Writing system](../../language-terms/writing-systems-and-scripts/writing-system.md) · [Internationalization & localization terms](../internationalization-and-localization/)

### Further reading

* Code & specs: [Intl.Segmenter (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Segmenter)
* Foundations: [UAX #29: Unicode Text Segmentation](https://unicode.org/reports/tr29/)

### Sources

1. "This annex describes guidelines for determining default segmentation boundaries between certain significant text elements: grapheme clusters ("user-perceived characters"), words, and sentences" - Unicode Standard Annex #29: Unicode Text Segmentation [https://unicode.org/reports/tr29/](https://unicode.org/reports/tr29/)
2. "reliable detection of word boundaries in languages such as Thai, Lao, Chinese, or Japanese requires the use of dictionary lookup or other mechanisms, analogous to English hyphenation" - Unicode Standard Annex #29: Unicode Text Segmentation, section 2 Conformance [https://unicode.org/reports/tr29/#Conformance](https://unicode.org/reports/tr29/#Conformance)
3. "Boundary determination is implementation-dependent, but general default algorithms are specified in Unicode Standard Annex #29" - ECMAScript Internationalization API Specification (ECMA-402), Abstract Operations for Segmenter Objects [https://tc39.es/ecma402/](https://tc39.es/ecma402/)
4. "ICU provides dictionary support for word boundaries in Chinese, Japanese, Thai, Lao, Khmer and Burmese" - ICU User Guide: Boundary Analysis [https://unicode-org.github.io/icu/userguide/boundaryanalysis/](https://unicode-org.github.io/icu/userguide/boundaryanalysis/)
