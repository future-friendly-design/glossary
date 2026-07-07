---
term: Han characters
slug: han-characters
aliases:
  - hanzi
  - kanji
  - hanja
  - Chinese characters
level: intermediate
depth: core
summary: Han characters are the logographic symbols used to write Chinese and, in part, Japanese and Korean.
related:
  - logographic
  - logosyllabary
  - cjk
  - hiragana
  - katakana
  - hangul
status: voice-passed
version_added: 0.1
updated: 2026-07-06
contributors:
  - sam-gordashko
further_reading:
  - title: Requirements for Chinese Text Layout (W3C)
    url: https://www.w3.org/TR/clreq/
    type: code
  - title: Noto Sans Simplified Chinese (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+SC
    type: design-tool
  - title: 'Unicode CJK Unified Ideographs code chart (U+4E00)'
    url: https://www.unicode.org/charts/PDF/U4E00.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Han characters

## Definition

Han characters are the [logographic](../language-terms/writing-systems-and-scripts/logographic.md) symbols used to write Chinese and, in part, Japanese and Korean. They are logographic: each character represents a word, not just a sound, and they developed from [pictographic](../language-terms/writing-systems-and-scripts/pictographic.md) and [ideographic](../language-terms/writing-systems-and-scripts/ideographic.md) principles.<sup>1</sup> They are known as hànzì in Chinese, kanji in Japanese, and hanja in Korean,<sup>2</sup> and although Unicode's block name calls them ideographs, that is a conventional cover term, not a claim that each is a picture of an idea.<sup>3</sup>

For example, the single character 人 ("person") is shared across the languages, read rén in Chinese and jin or nin in Japanese.

Han characters make up one script within the writing system of each language that uses them. This page describes the script itself; how a given language uses it, its spelling, punctuation, and which characters, is that language's [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

### At a glance

| Property | Han characters |
| --- | --- |
| Script type | [Logographic](../language-terms/writing-systems-and-scripts/logographic.md) (Chinese is more precisely a [logosyllabary](../language-terms/writing-systems-and-scripts/logosyllabary.md)) |
| Autonym | 漢字 |
| Symbols | logographic characters, each standing for a word or morpheme (and mapping to a spoken syllable) |
| Marks | Rare: historic ideographic tone marks (U+302A to U+302D) mark unusual pronunciations in classical texts; no regular combining vowel or tone marks in modern use |
| Letter case | None (no uppercase and lowercase) |
| Numerals | Han numerals (一, 二, 三, and so on) alongside common ASCII digits |
| Unicode block | CJK Unified Ideographs, [U+4E00 to U+9FFF](https://www.unicode.org/charts/PDF/U4E00.pdf) (plus many extension blocks) |
| [Complex text layout](complex-text-layout.md) | No reordering or contextual shaping, but the correct glyph is language-dependent (Han unification) and Japanese and Chinese support vertical setting ([tategaki](../language-terms/writing-systems-and-scripts/tategaki.md)) |
| Languages | Chinese, Japanese, Korean (historically also Vietnamese) |

### Script rules and features

Script rules apply to any language that uses Han characters in its writing system. This glossary doesn't cover every rule; select a linked term to navigate to its page.

| Rule or feature | How it works with Han characters |
| --- | --- |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | Horizontal left to right, and traditionally vertical: top to bottom in columns running right to left ([tategaki](../language-terms/writing-systems-and-scripts/tategaki.md)) |
| Han unification | one code point covers a character shared across Chinese, Japanese, and Korean, but its printed form can differ by region, so the correct glyph depends on the language; not yet documented as its own term, contribution welcome |

Where a rule doesn't have its own page yet, that's noted in the table; a contribution is welcome.

### Why it matters in design systems

Treat this entry as a starting playbook for Han characters, as best as the glossary documents it today. The Definition already settles one decision: you need a [typeface](typeface.md) and [font](font.md) with Han coverage for the languages you serve, and that is a bigger commitment than it sounds.

Where you cannot be creative is the script rules, and the first is scale. The Han characters number in the tens of thousands,<sup>4</sup> which drives [font](font.md) file size and [subsetting](font-subsetting.md), [glyph](glyph.md) coverage, and input: text entry relies on an [input method editor](input-method-editor.md) that converts typed sounds into characters, rather than one key per symbol. The second is Han unification: Unicode encodes a single set of unified Han characters shared across Chinese, Japanese, and Korean,<sup>5</sup> but the glyphs used can vary widely from country to country,<sup>6</sup> so the same [code point](code-point.md) should render with the region's expected form. That makes glyph selection language-dependent: you have to set the text's language and pick a matching font (a Chinese font and a Japanese font draw the same code point differently), or a reader sees the wrong regional forms. Text also runs horizontally now but is traditionally set vertically,<sup>7</sup> which layout has to support. These are not styling choices: miss the coverage, the language tag, or the vertical forms and the text renders wrongly or not at all, not just unstyled.

Where you are free is the rest: the typeface's personality, weight, size, colour, and spacing, within what the script allows and what the language's [orthography](../language-terms/writing-systems-and-scripts/orthography.md) calls for, since which characters and which regional forms a language uses (Simplified versus Traditional Chinese, Japanese and Korean forms) is an orthographic choice, not a free one. And where the glossary is silent, a rule left undocumented is an open question, not a settled "no", so verify it with people who read the language rather than guessing.

### In practice

* **Budget for coverage and size before you commit a typeface:** a Han font carries thousands of glyphs, so plan [subsetting](font-subsetting.md) and loading, and confirm the [font coverage](font-coverage.md) spans the characters your languages need. [Noto Sans Simplified Chinese](https://fonts.google.com/noto/specimen/Noto+Sans+SC) is a free, open-licensed option (with separate Traditional Chinese, Japanese, and Korean families), and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce.
* **Set the language so the right regional glyph shows:** because Han unification puts one code point behind region-varying forms, tag the text's language and choose a matching font, or Chinese and Japanese readers may see each other's character shapes. Test with a character known to differ across regions.
* **Check the orthography, not just the script:** Simplified and Traditional Chinese, and the Japanese and Korean character sets, differ in which characters and forms they use, so do not treat "Chinese" or "CJK" as one target. Pull per-language conventions from [locale](locale.md) data that Unicode's [CLDR](cldr.md) publishes.
* **If a rule above is not documented, you may be the source:** the conventions for a language or a use you support may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Autonym](autonym.md) · [CJK](cjk.md) · [CLDR](cldr.md) · [Code point](code-point.md) · [Complex text layout](complex-text-layout.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Font subsetting](font-subsetting.md) · [Glyph](glyph.md) · [Hangul](hangul.md) · [Hiragana](hiragana.md) · [Ideographic](../language-terms/writing-systems-and-scripts/ideographic.md) · [Input method editor (IME)](input-method-editor.md) · [Katakana](katakana.md) · [Language](../language-terms/linguistics/language.md) · [Locale](locale.md) · [Logographic](../language-terms/writing-systems-and-scripts/logographic.md) · [Logosyllabary](../language-terms/writing-systems-and-scripts/logosyllabary.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Pictographic](../language-terms/writing-systems-and-scripts/pictographic.md) · [Reordering](../programming-terms/text-for-digital-products-and-the-web/reordering.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Tategaki](../language-terms/writing-systems-and-scripts/tategaki.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Vertical text](vertical-text.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Code & specs: [Requirements for Chinese Text Layout (W3C)](https://www.w3.org/TR/clreq/)
* Design tools: [Noto Sans Simplified Chinese (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+SC)
* Foundations: [Unicode CJK Unified Ideographs code chart (U+4E00)](https://www.unicode.org/charts/PDF/U4E00.pdf)

### Sources

1. They are logographic (each character represents a word, not just a sound) characters that developed from pictographic and ideographic principles - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
2. Several standard romanizations of the term used to refer to East Asian ideographic characters are commonly used, including hànzì (Chinese), kanzi and colloquial kanji (Japanese), hanja (Korean), and Chữ hán (Vietnamese) - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
3. Taken literally, the word "ideograph" applies only to some of the ancient original character forms, but the term "Han ideographs" remains in English usage as a conventional cover term for the script as a whole - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
4. The Han ideographic characters constitute a very large set, numbering in the tens of thousands - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
5. The Unicode Standard contains a set of unified Han ideographic characters used in the written Chinese, Japanese, and Korean languages - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
6. There may be a wide variation in the glyphs used in different countries and for different applications - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
7. Traditionally, the basic writing direction followed the conventions of Chinese handwriting, in top-down vertical lines arranged from right to left across the page; under the influence of Western printing technologies, a horizontal, left-to-right directionality has become common - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
