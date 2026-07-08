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

CJK is a convenience grouping, not a single script. This page describes what the members share; how any one of them works, its symbols and rules, is that script's own page. What they have in common is a set of shared engineering concerns, not a common ancestor.

### What unites the members

These are the traits the group holds in common. The members are different scripts, so treat this as the shared starting point, not a specification for any one of them.

| Shared feature | Across the CJK group |
| --- | --- |
| Grouping | the writing systems of China, Japan, and Korea (CJK; CJKV includes Vietnam historically) |
| [Han characters](han-characters.md) | all three traditions use Han characters (hanzi, kanji, hanja), encoded once as CJK Unified Ideographs |
| Square layout | characters are written within uniformly sized squares ([full-width](full-width.md)), so text sets on a fixed grid |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | traditionally [vertical](vertical-text.md) (top to bottom, columns right to left); horizontal left to right is now common |
| Script mixing | Han characters are interspersed with the region's other scripts (kana in Japanese, hangul in Korean) |
| Rendering | not complex in the reordering sense, but the correct glyph is language-dependent (Han unification) and fonts are very large |

### Members

The CJK group gathers a few different scripts; here they are, with a page linked where one exists. The Example column shows each linked script's own name, and the last column notes what makes each member its own thing. Select a linked term to navigate to its glossary page.

| Script | Languages | Example | Distinctive in the group |
| --- | --- | --- | --- |
| [Han characters](han-characters.md) | Chinese, Japanese, Korean | 漢字 | [logographic](../language-terms/writing-systems-and-scripts/logographic.md); tens of thousands of characters; the shared core, with language-dependent glyphs |
| [Hiragana](hiragana.md) | Japanese | ひらがな | cursive kana [syllabary](../language-terms/writing-systems-and-scripts/syllabary.md); native words, particles, and inflections |
| [Katakana](katakana.md) | Japanese | カタカナ | angular kana syllabary; loanwords and emphasis |
| [Hangul](hangul.md) | Korean | 한글 | [featural](../language-terms/writing-systems-and-scripts/featural-alphabet.md); letters (jamo) composed into square syllable blocks |
| Bopomofo (Zhuyin) | Mandarin Chinese | | phonetic symbols used to teach and annotate pronunciation, mainly in Taiwan |

### Why it matters in design systems

Treat this entry as a map of the group, not a playbook for any one member: for that, follow the link to the specific script. The value of the grouping is that it tells you what transfers and what does not.

What transfers is a set of shared engineering concerns. CJK characters are written within uniformly sized squares,<sup>4</sup> so text sets on a fixed grid; the writing is traditionally [vertical](vertical-text.md) as well as horizontal,<sup>5</sup> so vertical layout is a real requirement; the fonts are very large, so file size, [subsetting](font-subsetting.md), and loading matter; and text entry relies on an [input method editor](input-method-editor.md) rather than one key per symbol. Build that infrastructure once, and it serves all three traditions.

What does not transfer is the scripts themselves, and this is the trap: the members are genuinely different systems, so "CJK support" is not one deliverable. [Han characters](han-characters.md) are [logographic](../language-terms/writing-systems-and-scripts/logographic.md) and their glyphs vary by region, so you have to set the text's language or a reader sees the wrong forms; the Japanese kana are syllabaries interspersed with kanji;<sup>6</sup> Hangul composes letters into square blocks. Because the same Han [code point](code-point.md) can render with different regional glyphs,<sup>7</sup> glyph choice is language-dependent, so verify each member against its own page and a real word, and bound your choices by the language's [orthography](../language-terms/writing-systems-and-scripts/orthography.md) as well as the script. Where the glossary is silent, a rule left undocumented is an open question, not a settled "no".

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

1. The term "CJK" (Chinese, Japanese, and Korean) is used to describe the languages that currently use Han ideographic characters - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
2. The Unicode Standard contains a set of unified Han ideographic characters used in the written Chinese, Japanese, and Korean languages - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
3. The term "CJKV" would be more accurate in a historical sense, because earlier Vietnamese writing systems were based on Han ideographs - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
4. In all these East Asian scripts, the characters (Chinese ideographs, Japanese kana, Korean Hangul syllables, and Yi syllables) are written within uniformly sized rectangles, usually squares - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
5. Traditionally, the basic writing direction followed the conventions of Chinese handwriting, in top-down vertical lines arranged from right to left across the page - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
6. When used in writing Japanese or Korean, the Han characters are interspersed with other scripts unique to those languages (Hiragana and Katakana for Japanese; Hangul syllables for Korean) - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
7. There may be a wide variation in the glyphs used in different countries and for different applications - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
