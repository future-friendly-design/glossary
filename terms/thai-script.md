---
term: Thai script
slug: thai-script
aliases:
  - thai
level: intermediate
depth: core
summary: The Thai script is a script used to write Thai and several other languages of the region, including Kuy, Pali, and Sanskrit.
related:
  - abugida
  - brahmic-scripts
  - tone-mark
  - segmentation
  - complex-text-layout
status: voice-passed
version_added: 0.1
updated: 2026-07-04
contributors:
  - sam-gordashko
further_reading:
  - title: Developing OpenType Fonts for Thai Script (Microsoft)
    url: https://learn.microsoft.com/en-us/typography/script-development/thai
    type: code
  - title: Noto Sans Thai (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Thai
    type: design-tool
  - title: 'Unicode Thai code chart (U+0E00)'
    url: https://www.unicode.org/charts/PDF/U0E00.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Thai script

## Definition

The Thai script is a [script](../language-terms/writing-systems-and-scripts/script.md) used to write Thai and several other languages of the region, including Kuy, Pali, and Sanskrit.<sup>1</sup> It is an [abugida](../language-terms/writing-systems-and-scripts/abugida.md) descended from the [Brahmic](brahmic-scripts.md) family: each consonant carries an inherent vowel that vowel marks can change, and marks above the consonant set the tone.<sup>2</sup>

For example, ภาษาไทย ("phasa Thai", "Thai language") is written solid, with no spaces between the words, the way Thai runs throughout.

The Thai script is one script within the writing system of each language that uses it. This page describes the script itself; how a given language uses it, its spelling, punctuation, and which symbols, is that language's [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

### At a glance

| Property | Thai script |
| --- | --- |
| Script type | [Abugida](../language-terms/writing-systems-and-scripts/abugida.md) |
| Autonym | อักษรไทย |
| Symbols | consonants carrying an inherent vowel, plus vowel marks written around them |
| Marks | vowel marks (written before, after, above, or below the consonant) and four [tone marks](../language-terms/writing-systems-and-scripts/tone-mark.md) above |
| Letter case | None (no uppercase and lowercase) |
| Numerals | Thai digits ๐ to ๙ (alongside common ASCII digits) |
| Unicode block | Thai, [U+0E00 to U+0E7F](https://www.unicode.org/charts/PDF/U0E00.pdf) |
| [Complex text layout](complex-text-layout.md) | Yes, mark positioning and word segmentation required |
| Languages | Thai, Kuy, Pali, Sanskrit, and others |

### Script rules and features

Script rules apply to any language that uses the Thai script in its writing system. This glossary doesn't cover every rule; select a linked term to navigate to its page.

| Rule or feature | How it works in the Thai script |
| --- | --- |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | Left to right |
| [Word segmentation](../programming-terms/text-for-digital-products-and-the-web/segmentation.md) | Thai has no spaces between words, so line breaking relies on dictionary-based segmentation; a zero-width space can mark an explicit break point |
| [Tone marks](../language-terms/writing-systems-and-scripts/tone-mark.md) | four tone marks sit above the consonant, stacking above an upper vowel mark when both are present |

### Why it matters in design systems

Treat this entry as a starting playbook for the Thai script, as best as the glossary documents it today. The Definition already settles one decision: you need a [typeface](typeface.md) and [font](font.md) with Thai coverage, because the rules above will not render without it.

Where you cannot be creative is the script rules. Text runs left to right.<sup>3</sup> A vowel mark can sit before, after, above, or below its consonant; the ones that appear to the left are stored in that visual order, so, unlike [Devanagari](devanagari.md), the renderer does not reorder them.<sup>4</sup> Because Thai writes words without spaces, where a line may break is not obvious from the text: it depends on dictionary-based [word segmentation](../programming-terms/text-for-digital-products-and-the-web/segmentation.md), not on spaces.<sup>5</sup> And the vowel marks and tone marks that sit above and below the consonant have to be stacked and positioned correctly, which the font's [OpenType](opentype.md) rules carry and the platform's [text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) applies at render time, the step that turns stored characters into positioned glyphs.<sup>6</sup> These are not styling choices: get the mark stacking or the line breaking wrong and the text renders or wraps incorrectly, not just unstyled.

Everything else is a free design choice: the typeface's personality, weight, size, colour, and spacing, within what the script allows (loose [letter spacing](letter-spacing.md) can collide with the marks stacked above and below, and it does nothing to show word boundaries the text itself does not mark) and what the language's [orthography](../language-terms/writing-systems-and-scripts/orthography.md) calls for. And where the glossary is silent, a rule left undocumented is an open question, not a settled "no", so verify it with people who read the language rather than guessing.

### In practice

* **Cover the script before you commit a typeface:** confirm the font positions the stacked vowel marks and tone marks (above and below the consonant), not just the base consonants. [Noto Sans Thai](https://fonts.google.com/noto/specimen/Noto+Sans+Thai) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Test with a real phrase, not a glyph grid:** type a syllable that has both an above-vowel and a tone mark and confirm they stack in the right order; then set a real Thai paragraph and confirm it wraps at word boundaries rather than mid-word. Tool support for [complex text layout](complex-text-layout.md) varies, so test early.
* **Treat word breaking as a first-class problem, not just the script:** because Thai has no spaces, line breaking, search, and truncation all depend on dictionary-based [word segmentation](../programming-terms/text-for-digital-products-and-the-web/segmentation.md), which is language- and library-specific. Do not split Thai on spaces or on individual characters; use a segmenter such as [ICU](icu.md), and pull per-language conventions from [locale](locale.md) data that Unicode's [CLDR](cldr.md) publishes.
* **If a rule above is not documented, you may be the source:** for an under-resourced language the conventions may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Abugida](../language-terms/writing-systems-and-scripts/abugida.md) · [Autonym](autonym.md) · [Brahmic scripts](brahmic-scripts.md) · [CLDR](cldr.md) · [Complex text layout](complex-text-layout.md) · [Devanagari](devanagari.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [ICU](icu.md) · [Language](../language-terms/linguistics/language.md) · [Letter spacing](letter-spacing.md) · [Locale](locale.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Noto fonts](noto-fonts.md) · [OpenType](opentype.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Segmentation](../programming-terms/text-for-digital-products-and-the-web/segmentation.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Tone mark](../language-terms/writing-systems-and-scripts/tone-mark.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Code & specs: [Developing OpenType Fonts for Thai Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/thai)
* Design tools: [Noto Sans Thai (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Thai)
* Foundations: [Unicode Thai code chart (U+0E00)](https://www.unicode.org/charts/PDF/U0E00.pdf)

### Sources

1. The Thai script is used to write the Thai language and other Southeast Asian languages, such as Kuy, Lanna Tai, and Pali - The Unicode Standard, Version 16.0, Chapter 16: Southeast Asia-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-16/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-16/)
2. Thai is a member of the Indic family of scripts descended from Brahmi, and in common with most Brahmi-derived scripts each Thai consonant letter represents a syllable possessing an inherent vowel sound - The Unicode Standard, Version 16.0, Chapter 16: Southeast Asia-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-16/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-16/)
3. As in all scripts of this family, the predominant writing direction of Thai is from left to right - The Unicode Standard, Version 16.0, Chapter 16: Southeast Asia-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-16/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-16/)
4. Vowels that occur to the left side of their consonant are represented in visual order before the consonant, even though they are pronounced afterward; this differs from other Indic scripts, which encode all vowels after the base consonant and reorder them for display - The Unicode Standard, Version 16.0, Chapter 16: Southeast Asia-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-16/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-16/)
5. Thai words are not separated by spaces; instead, spaces are introduced where Western typography would use a comma or period, and a zero-width space (U+200B) can be used to indicate explicit word or line break opportunities - The Unicode Standard, Version 16.0, Chapter 16: Southeast Asia-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-16/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-16/)
6. The Thai shaping engine positions the vowel marks and tone marks on the base consonant with the OpenType mark (mark-to-base) and mkmk (mark-to-mark) features - Developing OpenType Fonts for Thai Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/thai](https://learn.microsoft.com/en-us/typography/script-development/thai)
