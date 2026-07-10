---
term: Hiragana
slug: hiragana
aliases: []
level: intermediate
depth: core
summary: Hiragana is a script used to write Japanese, one of the language's two kana syllabaries.
related:
  - syllabary
  - katakana
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
  - title: 'Unicode Hiragana code chart (U+3040)'
    url: https://www.unicode.org/charts/PDF/U3040.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Hiragana

## Definition

Hiragana is a [script](../language-terms/writing-systems-and-scripts/script.md) used to write Japanese, one of the language's two kana [syllabaries](../language-terms/writing-systems-and-scripts/syllabary.md). Each rounded, cursive symbol stands for a syllable, and hiragana carries Japanese words written phonetically along with sentence particles and inflectional endings.<sup>1</sup> Its symbols are simplified, stylized versions of certain [Han characters](han-characters.md).<sup>2</sup>

For example, the script's own name, ひらがな ("hiragana"), is four symbols: hi, ra, ga, na (が is か "ka" with the voiced-sound mark).

{% hint style="info" %}
This glossary doesn't cover every hiragana property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Hiragana profile

These properties of hiragana apply to any language that uses it in its [writing system](../language-terms/writing-systems-and-scripts/writing-system.md). Beyond the [script rules](../language-terms/writing-systems-and-scripts/script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

| Property | Hiragana |
| --- | --- |
| [Autonym](autonym.md) | ひらがな |
| Languages | Japanese |
| Letter case | None (no uppercase and lowercase) |
| [Marks](../language-terms/writing-systems-and-scripts/mark.md) | Voiced-sound mark (dakuten) and semi-voiced-sound mark (handakuten), which turn a base symbol into its voiced or semi-voiced counterpart; small kana modify the preceding sound |
| Numerals | Common ASCII digits (Japanese also uses kanji numerals) |
| Script type | [Syllabary](../language-terms/writing-systems-and-scripts/syllabary.md) |
| [Symbols](../language-terms/writing-systems-and-scripts/symbol.md) | Symbols each standing for a syllable (mora): a vowel alone, or a consonant plus a vowel |

### Hiragana rules and digital use considerations

If your design system supports languages that use hiragana, here are some considerations to keep in mind:

| Rule or feature | How it works in hiragana | Design systems |
| --- | --- | --- |
| [Bidirectional text](../language-terms/writing-systems-and-scripts/bidirectional-text.md) | Japanese text runs left to right, or top to bottom when set vertically, but a line or column can still become bidirectional when right-to-left content, such as an Arabic or Hebrew name, is embedded in it | The embedded right-to-left run then needs the Unicode bidirectional algorithm to reorder correctly<sup>3</sup>; isolate embedded content whose direction you do not control, so it cannot disturb the surrounding text |
| [Complex text layout](complex-text-layout.md) | Not required: no reordering or contextual analysis, and a voiced or semi-voiced syllable is usually its own precomposed symbol<sup>4</sup> (see OpenType and Text shaping below) | Hiragana needs no per-symbol shaping, so the design-critical work is layout, not glyph substitution: the mixed-script line, the vertical forms, and any ruby (see those rows below) |
| [OpenType](opentype.md) | The font uses standard [OpenType features](opentype-features.md) for glyph substitution and, when text is set vertically, a vertical-forms feature that swaps in the vertical glyph forms<sup>5</sup>; there are no joining or reordering features | Confirm the font actually ships the vertical kana forms if you set text vertically, not just the horizontal glyphs. See the Text shaping row below |
| Ruby (furigana) | Hiragana is set small above or beside [kanji](han-characters.md) to show their pronunciation<sup>6</sup> | If you support ruby, confirm it renders and positions correctly; it is a layout feature, not decorative styling |
| Script mixing | In ordinary Japanese, hiragana is interspersed with [katakana](katakana.md) and [kanji](han-characters.md), the Japanese [Han characters](han-characters.md)<sup>7</sup> | You are never setting hiragana by itself, so the three scripts have to share one line, sit on compatible metrics, and read as one text; confirm the font covers all three with harmonized weights |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | Horizontal [left to right](../language-terms/writing-systems-and-scripts/left-to-right.md), and traditionally [vertical](vertical-text.md): top to bottom in columns running right to left ([tategaki](../language-terms/writing-systems-and-scripts/tategaki.md))<sup>8</sup> | Support vertical layout if your text calls for it (see OpenType and Text shaping below for how the vertical forms are substituted) |
| [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) | Little to none for horizontal text: the [shaping engine](shaping-engine.md) places one glyph per symbol, with no joining or reordering. Vertical setting is the exception: the engine reads the font's vertical-forms feature (see OpenType above) and substitutes the vertical glyph forms | Horizontal kana renders in any tool as long as the font is present; vertical kana needs a pipeline that applies the vertical forms, so test vertical layout in the actual design tools your team uses, not just the browser |
| [Unicode](unicode.md) block | Hiragana, [U+3040 to U+309F](https://www.unicode.org/charts/PDF/U3040.pdf) | No special handling beyond ensuring [font coverage](font-coverage.md) of the block, alongside the katakana and kanji hiragana shares a line with |
| Voiced-sound marks | A base symbol takes a voiced mark (dakuten) or semi-voiced mark (handakuten) to form its voiced or semi-voiced counterpart | A voiced or semi-voiced syllable is usually its own precomposed symbol, with the base-plus-[combining mark](../programming-terms/text-for-digital-products-and-the-web/combining-mark.md) form used mainly for kana outside that set,<sup>9</sup> so confirm the marks render, not just the base symbols |

### In practice

* **Cover all three scripts, not just the kana:** confirm the font sets hiragana, [katakana](katakana.md), and [kanji](han-characters.md) together with compatible weights and metrics, and renders the voiced-sound marks, not just the base symbols. [Noto Sans Japanese](https://fonts.google.com/noto/specimen/Noto+Sans+JP) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Test with a real sentence, not a kana grid:** set a real Japanese sentence that mixes all three scripts, and if you support vertical text ([tategaki](../language-terms/writing-systems-and-scripts/tategaki.md)) or ruby, confirm those render too. Tool support for [complex text layout](complex-text-layout.md) and vertical text varies, so test early.
* **Check the orthography, not just the script:** whether a word is written in hiragana, katakana, or kanji is an orthographic choice, not a free one, so do not swap scripts to fit a layout. Pull per-language conventions from [locale](locale.md) data that Unicode's [CLDR](cldr.md) publishes.
* **If a rule above is not documented, you may be the source:** the conventions for a use you support may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Autonym](autonym.md) · [Bidirectional text](../language-terms/writing-systems-and-scripts/bidirectional-text.md) · [CJK](cjk.md) · [CLDR](cldr.md) · [Combining mark](../programming-terms/text-for-digital-products-and-the-web/combining-mark.md) · [Complex text layout](complex-text-layout.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [Han characters](han-characters.md) · [Katakana](katakana.md) · [Language](../language-terms/linguistics/language.md) · [Left-to-right](../language-terms/writing-systems-and-scripts/left-to-right.md) · [Locale](locale.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Noto fonts](noto-fonts.md) · [OpenType](opentype.md) · [OpenType features](opentype-features.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Reordering](../programming-terms/text-for-digital-products-and-the-web/reordering.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Shaping engine](shaping-engine.md) · [Syllabary](../language-terms/writing-systems-and-scripts/syllabary.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Tategaki](../language-terms/writing-systems-and-scripts/tategaki.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Vertical text](vertical-text.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Code & specs: [Requirements for Japanese Text Layout (W3C)](https://www.w3.org/TR/jlreq/)
* Design tools: [Noto Sans Japanese (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+JP)
* Foundations: [Unicode Hiragana code chart (U+3040)](https://www.unicode.org/charts/PDF/U3040.pdf)

### Sources

1. Hiragana is the cursive syllabary used to write Japanese words phonetically and to write sentence particles and inflectional endings - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
2. The Japanese developed two syllabaries, Hiragana and Katakana, whose shapes are simplified or stylized versions of certain ideographs - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
3. This annex describes specifications for the positioning of characters in text containing characters flowing from right to left, such as Arabic or Hebrew - Unicode Standard Annex #9: Unicode Bidirectional Algorithm [https://www.unicode.org/reports/tr9/](https://www.unicode.org/reports/tr9/)
4. This document describes requirements for general Japanese layout realized with technologies like CSS, SVG and XSL-FO - Requirements for Japanese Text Layout (W3C) [https://www.w3.org/TR/jlreq/](https://www.w3.org/TR/jlreq/)
5. Transforms default glyphs into glyphs that are appropriate for upright presentation in vertical writing mode - Registered features, u-z (OpenType): 'vert' Vertical Alternates [https://learn.microsoft.com/en-us/typography/opentype/spec/features_uz](https://learn.microsoft.com/en-us/typography/opentype/spec/features_uz)
6. Hiragana is also commonly used to indicate the pronunciation of Japanese words - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
7. When used in writing Japanese or Korean, the Han characters are interspersed with other scripts unique to those languages (Hiragana and Katakana for Japanese; Hangul syllables for Korean) - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
8. Traditionally, the basic writing direction followed the conventions of Chinese handwriting, in top-down vertical lines arranged from right to left across the page; under the influence of Western printing technologies, a horizontal, left-to-right directionality has become common - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
9. All common precomposed combinations of base syllable forms using these marks are already encoded as characters, and use of these precomposed forms is the predominant JIS usage - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
