---
term: Katakana
slug: katakana
aliases: []
level: intermediate
depth: core
summary: Katakana is a script used to write Japanese, one of the language's two kana syllabaries.
related:
  - syllabary
  - hiragana
  - han-characters
  - tategaki
  - cjk
status: voice-passed
version_added: 0.1
updated: 2026-07-06
contributors:
  - sam-gordashko
further_reading:
  - title: Requirements for Japanese Text Layout (W3C)
    url: https://www.w3.org/TR/jlreq/
    type: code
  - title: Noto Sans Japanese (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+JP
    type: design-tool
  - title: 'Unicode Katakana code chart (U+30A0)'
    url: https://www.unicode.org/charts/PDF/U30A0.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Katakana

## Definition

Katakana is a [script](../language-terms/writing-systems-and-scripts/script.md) used to write Japanese, one of the language's two kana syllabaries. It is a [syllabary](../language-terms/writing-systems-and-scripts/syllabary.md): each angular, noncursive symbol stands for a syllable, and katakana is used to write non-Japanese words phonetically,<sup>1</sup> and to write Japanese words with visual emphasis.<sup>2</sup>

For example, the loanword コーヒー ("kōhī", from English "coffee") is written in katakana, using the prolonged sound mark (ー) to lengthen its vowels.

{% hint style="info" %}
This glossary doesn't cover every katakana property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Katakana profile

These properties of katakana apply to any language that uses it in its [writing system](../language-terms/writing-systems-and-scripts/writing-system.md). Beyond the [script rules](../language-terms/writing-systems-and-scripts/script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

| Property | Katakana |
| --- | --- |
| [Autonym](autonym.md) | カタカナ |
| Languages | Japanese; extended katakana also writes Ainu |
| Letter case | None (no uppercase and lowercase) |
| [Marks](../language-terms/writing-systems-and-scripts/mark.md) | Voiced-sound mark (dakuten) and semi-voiced-sound mark (handakuten); the prolonged sound mark (ー) lengthens a vowel; small kana modify the preceding sound |
| Numerals | Common ASCII digits (Japanese also uses kanji numerals) |
| Script type | [Syllabary](../language-terms/writing-systems-and-scripts/syllabary.md) |
| [Symbols](../language-terms/writing-systems-and-scripts/symbol.md) | Symbols each standing for a syllable (mora), matching the [hiragana](hiragana.md) set but angular in form |

### Katakana rules and digital use considerations

If your design system supports languages that use katakana, here are some considerations to keep in mind:

| Rule or feature | How it works in katakana | Design systems |
| --- | --- | --- |
| [Complex text layout](complex-text-layout.md) | Not required for shaping: no reordering or contextual analysis, and voiced syllables are usually their own precomposed symbols<sup>3</sup> | Katakana is simple to shape, so the design-critical work is layout and data handling, not glyph substitution; the vertical forms and the mixed-script line still resolve at render time through the platform's [text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md), not styling |
| Half-width katakana | legacy systems produce half-width katakana as separate compatibility characters, distinct from the [full-width](full-width.md) forms<sup>4</sup> | Apply [normalization](normalization.md) to the full-width forms before you compare or search, or identical-looking text will fail to match<sup>5</sup> |
| Katakana versus hiragana | katakana covers the same syllables as [hiragana](hiragana.md)<sup>6</sup> | Which script a word uses is a meaning choice, not a free swap: katakana marks a word as a loanword or as emphasized, roughly the way italics work in Latin text, so do not switch scripts to fit a layout |
| Script mixing | in ordinary Japanese, katakana is interspersed with [hiragana](hiragana.md) and [kanji](han-characters.md), the Japanese [Han characters](han-characters.md)<sup>7</sup> | You are never setting katakana by itself: the three scripts share one line and have to read as one text, so confirm the font covers all three with harmonized weights and metrics |
| Sound marks | voiced (dakuten) and semi-voiced (handakuten) marks form voiced counterparts, and the prolonged sound mark lengthens a vowel<sup>8</sup> | Voiced syllables are usually their own precomposed symbols, with the base-plus-[combining mark](../programming-terms/text-for-digital-products-and-the-web/combining-mark.md) form used mainly for kana outside that set, such as the Ainu phonetic extensions,<sup>9</sup> so confirm the marks and the prolonged sound mark render, not just the base symbols |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | Horizontal left to right, and traditionally vertical: top to bottom in columns running right to left ([tategaki](../language-terms/writing-systems-and-scripts/tategaki.md))<sup>10</sup> | Support vertical layout if your text calls for it; vertical setting substitutes the font's [OpenType](opentype.md) vertical forms, placed by the layout engine rather than by styling |
| [Unicode](unicode.md) block | Katakana, [U+30A0 to U+30FF](https://www.unicode.org/charts/PDF/U30A0.pdf) (plus half-width forms and Katakana Phonetic Extensions) | No special handling beyond ensuring [font coverage](font-coverage.md) of the block, alongside the hiragana and kanji katakana shares a line with |

### In practice

* **Cover all three scripts, not just the kana:** confirm the font sets katakana, [hiragana](hiragana.md), and [kanji](han-characters.md) together with compatible weights and metrics, and renders the sound marks, not just the base symbols. [Noto Sans Japanese](https://fonts.google.com/noto/specimen/Noto+Sans+JP) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Normalize half-width katakana before you compare or search:** legacy data often carries half-width katakana as separate compatibility code points, so apply [normalization](normalization.md) to the [full-width](full-width.md) forms before matching, or identical-looking text will fail to compare equal. Test vertical text ([tategaki](../language-terms/writing-systems-and-scripts/tategaki.md)) early if you support it.
* **Check the orthography, not just the script:** whether a word is written in katakana, hiragana, or kanji is an orthographic choice that carries meaning, so do not swap scripts to fit a layout. Pull per-language conventions from [locale](locale.md) data that Unicode's [CLDR](cldr.md) publishes.
* **If a rule above is not documented, you may be the source:** the conventions for a use you support may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Autonym](autonym.md) · [CJK](cjk.md) · [CLDR](cldr.md) · [Combining mark](../programming-terms/text-for-digital-products-and-the-web/combining-mark.md) · [Complex text layout](complex-text-layout.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Full-width](full-width.md) · [Glyph](glyph.md) · [Han characters](han-characters.md) · [Hiragana](hiragana.md) · [Language](../language-terms/linguistics/language.md) · [Locale](locale.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Normalization](normalization.md) · [Noto fonts](noto-fonts.md) · [OpenType](opentype.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Reordering](../programming-terms/text-for-digital-products-and-the-web/reordering.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Syllabary](../language-terms/writing-systems-and-scripts/syllabary.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Tategaki](../language-terms/writing-systems-and-scripts/tategaki.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Vertical text](vertical-text.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Code & specs: [Requirements for Japanese Text Layout (W3C)](https://www.w3.org/TR/jlreq/)
* Design tools: [Noto Sans Japanese (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+JP)
* Foundations: [Unicode Katakana code chart (U+30A0)](https://www.unicode.org/charts/PDF/U30A0.pdf)

### Sources

1. Katakana is the noncursive syllabary used to write non-Japanese (usually Western) words phonetically in Japanese - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
2. Katakana is also used to write Japanese words with visual emphasis - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
3. This document describes requirements for general Japanese layout realized with technologies like CSS, SVG and XSL-FO - Requirements for Japanese Text Layout (W3C) [https://www.w3.org/TR/jlreq/](https://www.w3.org/TR/jlreq/)
4. The Halfwidth and Fullwidth Forms block contains halfwidth forms of the Katakana and Hangul Compatibility Jamo characters - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
5. A process of removing alternate representations of equivalent sequences from textual data, to convert the data into a form that can be binary-compared for equivalence - Unicode Glossary: Normalization [https://www.unicode.org/glossary/#normalization](https://www.unicode.org/glossary/#normalization)
6. Katakana syllables are phonetically equivalent to corresponding Hiragana syllables - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
7. When used in writing Japanese or Korean, the Han characters are interspersed with other scripts unique to those languages (Hiragana and Katakana for Japanese; Hangul syllables for Korean) - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
8. U+30FC KATAKANA-HIRAGANA PROLONGED SOUND MARK is used predominantly with Katakana and occasionally with Hiragana to denote a lengthened vowel - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
9. All common precomposed combinations of base syllable forms using these marks are already encoded as characters, and use of these precomposed forms is the predominant JIS usage - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
10. Traditionally, the basic writing direction followed the conventions of Chinese handwriting, in top-down vertical lines arranged from right to left across the page; under the influence of Western printing technologies, a horizontal, left-to-right directionality has become common - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
</content>
