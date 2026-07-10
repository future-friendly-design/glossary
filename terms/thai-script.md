---
term: Thai script
slug: thai-script
aliases:
  - thai
level: intermediate
depth: core
summary: The Thai script is used to write Thai and several other languages of the region, including Kuy, Lanna Tai, and Pali.
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

The Thai [script](../language-terms/writing-systems-and-scripts/script.md) is used to write Thai and several other languages of the region, including Kuy, Lanna Tai, and Pali.<sup>1</sup> It is an [abugida](../language-terms/writing-systems-and-scripts/abugida.md) descended from the [Brahmic](brahmic-scripts.md) family: each consonant carries an inherent vowel that vowel marks can change,<sup>2</sup> and marks above the consonant set the tone.<sup>3</sup>

For example, ภาษาไทย ("phasa Thai", "Thai language") is written solid, with no spaces between the words, the way Thai runs throughout.

{% hint style="info" %}
This glossary doesn't cover every Thai script property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Thai script profile

These properties of the Thai script apply to any language that uses it in its [writing system](../language-terms/writing-systems-and-scripts/writing-system.md). Beyond the [script rules](../language-terms/writing-systems-and-scripts/script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

| Property | Thai script |
| --- | --- |
| [Autonym](autonym.md) | อักษรไทย |
| Languages | Thai, Kuy, Lanna Tai, Pali, and others |
| Letter case | None (no uppercase and lowercase) |
| [Marks](../language-terms/writing-systems-and-scripts/mark.md) | Vowel marks (written before, after, above, or below the consonant) and four [tone marks](../language-terms/writing-systems-and-scripts/tone-mark.md) above |
| Numerals | Thai digits ๐ to ๙ (alongside common ASCII digits) |
| Script type | [Abugida](../language-terms/writing-systems-and-scripts/abugida.md) |
| [Symbols](../language-terms/writing-systems-and-scripts/symbol.md) | Consonants carrying an inherent vowel, plus vowel marks written around them |

### Thai script rules and digital use considerations

If your design system supports languages that use the Thai script, here are some considerations to keep in mind:

| Rule or feature | How it works in the Thai script | Design systems |
| --- | --- | --- |
| [Complex text layout](complex-text-layout.md) | Yes, shaping required | The vowel marks and tone marks stacked above and below the consonant have to be positioned by the font's [OpenType](opentype.md) rules and applied at render time by the platform's [text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md), and word breaking depends on segmentation rather than spaces, so a tool or font that cannot do both renders or wraps the text incorrectly, not just unstyled;<sup>4</sup> you need a [typeface](typeface.md) and [font](font.md) with Thai coverage before any of it will render |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | [Left to right](../language-terms/writing-systems-and-scripts/left-to-right.md)<sup>5</sup> | Left-aligned text as the default |
| [Tone marks](../language-terms/writing-systems-and-scripts/tone-mark.md) | Four tone marks sit above the consonant, stacking above an upper vowel mark when both are present<sup>6</sup> | Test a syllable with both an above-vowel and a tone mark so the marks stack in the right order; loose [letter spacing](letter-spacing.md) can collide with the stacked marks and does nothing to show word boundaries the text itself does not mark |
| [Unicode](unicode.md) block | Thai, [U+0E00 to U+0E7F](https://www.unicode.org/charts/PDF/U0E00.pdf) | No special handling beyond ensuring [font coverage](font-coverage.md) of the block |
| Vowel marks | A vowel mark can sit before, after, above, or below its consonant; the ones that appear to the left are stored in that visual order, so, unlike [Devanagari](devanagari.md), the renderer does not reorder them<sup>7</sup> | Thai does not reorder its left-side vowels, so do not apply Indic reordering logic to Thai text |
| [Word segmentation](../programming-terms/text-for-digital-products-and-the-web/segmentation.md) | Thai has no spaces between words, so line breaking relies on dictionary-based segmentation; a zero-width space can mark an explicit break point<sup>8</sup> | Do not split Thai on spaces or on individual characters; line breaking, search, and truncation need a segmenter such as [ICU](icu.md) |

### In practice

* **Cover the script before you commit a typeface:** confirm the font positions the stacked vowel marks and tone marks (above and below the consonant), not just the base consonants. [Noto Sans Thai](https://fonts.google.com/noto/specimen/Noto+Sans+Thai) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Test with a real phrase, not a glyph grid:** type a syllable that has both an above-vowel and a tone mark and confirm they stack in the right order; then set a real Thai paragraph and confirm it wraps at word boundaries rather than mid-word. Tool support for [complex text layout](complex-text-layout.md) varies, so test early.
* **Treat word breaking as a first-class problem, not just the script:** because Thai has no spaces, line breaking, search, and truncation all depend on dictionary-based [word segmentation](../programming-terms/text-for-digital-products-and-the-web/segmentation.md), which is language- and library-specific. Do not split Thai on spaces or on individual characters; use a segmenter such as [ICU](icu.md), and pull per-language conventions from [locale](locale.md) data that Unicode's [CLDR](cldr.md) publishes.
* **If a rule above is not documented, you may be the source:** for an under-resourced language the conventions may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Abugida](../language-terms/writing-systems-and-scripts/abugida.md) · [Autonym](autonym.md) · [Brahmic scripts](brahmic-scripts.md) · [CLDR](cldr.md) · [Complex text layout](complex-text-layout.md) · [Devanagari](devanagari.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [ICU](icu.md) · [Language](../language-terms/linguistics/language.md) · [Left-to-right](../language-terms/writing-systems-and-scripts/left-to-right.md) · [Letter spacing](letter-spacing.md) · [Locale](locale.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Noto fonts](noto-fonts.md) · [OpenType](opentype.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Segmentation](../programming-terms/text-for-digital-products-and-the-web/segmentation.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Tone mark](../language-terms/writing-systems-and-scripts/tone-mark.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Code & specs: [Developing OpenType Fonts for Thai Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/thai)
* Design tools: [Noto Sans Thai (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Thai)
* Foundations: [Unicode Thai code chart (U+0E00)](https://www.unicode.org/charts/PDF/U0E00.pdf)

### Sources

1. The Thai script is used to write the Thai language and other Southeast Asian languages, such as Kuy, Lanna Tai, and Pali - The Unicode Standard, Version 17.0, Chapter 16: Southeast Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/)
2. Thai is a member of the Indic family of scripts descended from Brahmi, and in common with most Brahmi-derived scripts each Thai consonant letter represents a syllable possessing an inherent vowel sound - The Unicode Standard, Version 17.0, Chapter 16: Southeast Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/)
3. Thai modifies the original Brahmi letter shapes and extends the number of letters to accommodate features of the Thai language, including tone marks derived from superscript digits - The Unicode Standard, Version 17.0, Chapter 16: Southeast Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/)
4. The Thai shaping engine positions the vowel marks and tone marks on the base consonant with the OpenType mark (mark-to-base) and mkmk (mark-to-mark) features - Developing OpenType Fonts for Thai Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/thai](https://learn.microsoft.com/en-us/typography/script-development/thai)
5. As in all scripts of this family, the predominant writing direction of Thai is from left to right - The Unicode Standard, Version 17.0, Chapter 16: Southeast Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/)
6. For the purpose of rendering, the Thai combining marks above (U+0E31, U+0E34..U+0E37, U+0E47..U+0E4E) should be displayed outward from the base character they modify, in the order in which they appear in the text - The Unicode Standard, Version 17.0, Chapter 16: Southeast Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/)
7. In the Thai encoding, the letter-sized glyphs that are placed before (left of) the base consonant letter, in full or partial representation of a vowel sign, are, in fact, encoded as separate characters that are typed and stored before the base consonant character. This encoding for left-side Thai vowel sign glyphs (and similarly in Lao and in Tai Viet) differs from the conventions for all other Indic scripts, which uniformly encode all vowels after the base consonant - The Unicode Standard, Version 17.0, Chapter 16: Southeast Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/)
8. Thai words are not separated by spaces; instead, spaces are introduced where Western typography would use a comma or period, and a zero-width space (U+200B) can be used to indicate explicit word or line break opportunities - The Unicode Standard, Version 17.0, Chapter 16: Southeast Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/)
</content>
