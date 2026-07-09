---
term: CJK
slug: cjk
aliases:
  - CJK characters
  - CJKV
level: intermediate
depth: core
summary: CJK is a collective term for the writing systems of China, Japan, and Korea.
related:
  - han-characters
  - hiragana
  - katakana
  - hangul
  - logographic
status: voice-passed
version_added: 0.1
updated: 2026-07-07
contributors:
  - sam-gordashko
further_reading:
  - title: 'Unicode FAQ: Chinese and Japanese'
    url: https://www.unicode.org/faq/han_cjk.html
    type: authority
  - title: Noto (Google Fonts)
    url: https://fonts.google.com/noto
    type: design-tool
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# CJK

## Definition

CJK is a collective term for the writing systems of China, Japan, and Korea.<sup>1</sup> The three traditions share a large stock of [Han characters](han-characters.md), which Unicode encodes once as a unified set used across the written Chinese, Japanese, and Korean languages.<sup>2</sup> The grouping is sometimes written CJKV, which is more accurate in a historical sense because earlier Vietnamese writing also used Han characters.<sup>3</sup>

CJK is a convenience grouping, not a single script: what the members have in common is a set of shared engineering concerns, not a common ancestor, so you design for each script, not for "CJK" as a whole. Unicode's own guidance is that font choice is language-dependent, advising that a CJK font intended for one language be used to present that language's text.<sup>4</sup>

{% hint style="info" %}
This glossary doesn't cover every CJK script or every shared concern; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../CONTRIBUTING.md), they will be linked.
{% endhint %}

### What unites the members

These are the traits the group holds in common. The members are different scripts, so treat this as the shared starting point, not a specification for any one of them.

| Shared feature | Across the CJK group | Design systems |
| --- | --- | --- |
| Grouping | the writing systems of China, Japan, and Korea (CJK; CJKV includes Vietnam historically) | Because the members share the engineering concerns below, build that infrastructure once and it serves all three traditions; then scope which scripts you actually ship |
| [Han characters](han-characters.md) | all three traditions use Han characters (hanzi, kanji, hanja), encoded once as CJK Unified Ideographs | Set the text's language so the shared [code points](code-point.md) render with the right regional glyphs |
| Square layout | characters are written within uniformly sized squares ([full-width](full-width.md)), so text sets on a fixed grid<sup>5</sup> | Design to a fixed character grid rather than proportional spacing |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | traditionally [vertical](vertical-text.md) (top to bottom, columns right to left); horizontal left to right is now common<sup>6</sup> | Vertical layout is a real requirement, not an edge case, if you support traditional setting |
| Script mixing | Han characters are interspersed with the region's other scripts (kana in Japanese, hangul in Korean)<sup>7</sup> | Two or three scripts share one line, so the font has to harmonize them at compatible weights and metrics |
| Rendering | it needs no [complex text layout](complex-text-layout.md) reordering, but the correct glyph is language-dependent (Han unification)<sup>8</sup> and the fonts are very large<sup>9</sup> | Budget for very large fonts ([subsetting](font-subsetting.md), loading) and an [input method editor](input-method-editor.md) for text entry |

### Members

The CJK group gathers several scripts and this glossary doesn't cover every one; here are the main members, with a page linked where one exists. The Example column shows each linked script's own name, and the last column notes what makes each member its own thing. Select a linked term to navigate to its glossary page.

| Script | Languages | Example | Distinctive in the group |
| --- | --- | --- | --- |
| [Han characters](han-characters.md) | Chinese, Japanese, Korean | 漢字 | [logographic](../language-terms/writing-systems-and-scripts/logographic.md); tens of thousands of characters; the shared core, with language-dependent glyphs |
| [Hiragana](hiragana.md) | Japanese | ひらがな | cursive kana [syllabary](../language-terms/writing-systems-and-scripts/syllabary.md); native words, particles, and inflections |
| [Katakana](katakana.md) | Japanese (also Ainu) | カタカナ | angular kana syllabary; loanwords and emphasis |
| [Hangul](hangul.md) | Korean | 한글 | [featural](../language-terms/writing-systems-and-scripts/featural-alphabet.md); letters (jamo) composed into square syllable blocks |
| Bopomofo (Zhuyin) | Mandarin Chinese | | phonetic symbols used to teach and annotate pronunciation, mainly in Taiwan |

### In practice

* **Cover the specific member, and set the language:** confirm the [font](font.md) covers the script you need, and tag the text's language so Han characters render with the right regional glyphs. The [Noto](noto-fonts.md) project ships free, open-licensed CJK families (separate Simplified Chinese, Traditional Chinese, Japanese, and Korean), and reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Budget for scale and input:** CJK fonts carry tens of thousands of glyphs, so plan [subsetting](font-subsetting.md) and loading, and rely on an [input method editor](input-method-editor.md) for text entry rather than a one-key-per-character keyboard.
* **Verify per script, not by group:** the shared square grid and big-font concerns are a starting point, not a guarantee; a syllabary, a logography, and a featural block behave differently, so confirm each member on its own page and with a fluent reader.
* **If a rule is not documented, you may be the source:** for a language or use you support the conventions may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[CLDR](cldr.md) · [Code point](code-point.md) · [Complex text layout](complex-text-layout.md) · [Featural script](../language-terms/writing-systems-and-scripts/featural-alphabet.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Font subsetting](font-subsetting.md) · [Full-width](full-width.md) · [Glyph](glyph.md) · [Han characters](han-characters.md) · [Hangul](hangul.md) · [Hiragana](hiragana.md) · [Input method editor (IME)](input-method-editor.md) · [Katakana](katakana.md) · [Language](../language-terms/linguistics/language.md) · [Locale](locale.md) · [Logographic](../language-terms/writing-systems-and-scripts/logographic.md) · [Noto fonts](noto-fonts.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Reordering](../programming-terms/text-for-digital-products-and-the-web/reordering.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Syllabary](../language-terms/writing-systems-and-scripts/syllabary.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Unicode](unicode.md) · [Vertical text](vertical-text.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Design tools: [Noto (Google Fonts)](https://fonts.google.com/noto)
* Foundations: [Unicode FAQ: Chinese and Japanese](https://www.unicode.org/faq/han_cjk.html)

### Sources

1. The term "CJK" (Chinese, Japanese, and Korean) is used to describe the languages that currently use Han ideographic characters - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
2. The Unicode Standard contains a set of unified Han ideographic characters used in the written Chinese, Japanese, and Korean languages - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
3. The term "CJKV" would be more accurate in a historical sense, because earlier Vietnamese writing systems were based on Han ideographs - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
4. It is therefore advisable that a CJK font intended for Japanese be used for presenting Japanese text to Japanese users - Unicode FAQ: Chinese and Japanese [https://www.unicode.org/faq/han_cjk.html](https://www.unicode.org/faq/han_cjk.html)
5. In all these East Asian scripts, the characters (Chinese ideographs, Japanese kana, Korean Hangul syllables, and Yi syllables) are written within uniformly sized rectangles, usually squares - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
6. Traditionally, the basic writing direction followed the conventions of Chinese handwriting, in top-down vertical lines arranged from right to left across the page - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
7. When used in writing Japanese or Korean, the Han characters are interspersed with other scripts unique to those languages (Hiragana and Katakana for Japanese; Hangul syllables for Korean) - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
8. There may be a wide variation in the glyphs used in different countries and for different applications - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
9. The Han ideographic characters constitute a very large set, numbering in the tens of thousands - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
