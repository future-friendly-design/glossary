---
term: Thai script
slug: thai-script
aliases:
  - thai
level: intermediate
depth: core
summary: >-
  The Thai script is used to write Thai and several other languages of the
  region, including Kuy, Lanna Tai, and Pali.
related:
  - abugida
  - brahmic-scripts
  - tone-mark
  - segmentation
  - complex-text-layout
status: voice-passed
version_added: 0.1
updated: 2026-07-04T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Developing OpenType Fonts for Thai Script (Microsoft)
    url: https://learn.microsoft.com/en-us/typography/script-development/thai
    type: code
  - title: Noto Sans Thai (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Thai
    type: design-tool
  - title: Unicode Thai code chart (U+0E00)
    url: https://www.unicode.org/charts/PDF/U0E00.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Thai script

## Definition

The Thai [script](script.md) is used to write Thai and several other languages of the region, including Kuy, Lanna Tai, and Pali.<sup>1</sup> It is an [abugida](abugida.md) descended from the [Brahmic](brahmic-scripts.md) family: each consonant carries an inherent vowel that vowel marks can change,<sup>2</sup> and marks above the consonant set the tone.<sup>3</sup>

For example, ภาษาไทย ("phasa Thai", "Thai language") is written solid, with no spaces between the words, the way Thai runs throughout.

{% hint style="info" %}
This glossary doesn't cover every Thai script property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Thai script profile

These properties of the Thai script apply to any language that uses it in its [writing system](writing-system.md). Beyond the [script rules](script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](orthography.md).

| Property                          | Thai script                                                                                                  |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| [Autonym](../../terms/autonym.md) | อักษรไทย                                                                                                     |
| Languages                         | Thai, Kuy, Lanna Tai, Pali, and others                                                                       |
| Letter case                       | None (no uppercase and lowercase)                                                                            |
| [Marks](mark.md)                  | Vowel marks (written before, after, above, or below the consonant) and four [tone marks](tone-mark.md) above |
| Numerals                          | Thai digits ๐ to ๙ (alongside common ASCII digits)                                                           |
| Script type                       | [Abugida](abugida.md)                                                                                        |
| [Symbols](symbol.md)              | Consonants carrying an inherent vowel, plus vowel marks written around them                                  |

### Thai script rules and digital use considerations

If your design system supports languages that use the Thai script, here are some considerations to keep in mind:

| Rule or feature                                                                                    | How it works in the Thai script                                                                                                                                                                                                                                                                                                                      | Design systems                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| -------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Bidirectional text](bidirectional-text.md)                                                        | The script runs left to right, but a line can still become bidirectional when right-to-left content (an Arabic or Hebrew name, for example) is embedded in it                                                                                                                                                                                        | Then the embedded right-to-left run needs the Unicode bidirectional algorithm to reorder correctly; isolate embedded content whose direction you do not control, so it cannot disturb the surrounding text<sup>4</sup>                                                                                                                                                                                                                         |
| [Complex text layout](../../terms/complex-text-layout.md)                                          | Yes, shaping required                                                                                                                                                                                                                                                                                                                                | Handled by the font's [OpenType](../../terms/opentype.md) rules and applied at render time by the platform's [text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md); see the OpenType and Text shaping rows below for what your font needs to support, and note that word breaking is separate (see Word segmentation below). Get it wrong and the text renders or wraps incorrectly, not just unstyled |
| [Font](../../terms/font.md) (open source)                                                          | [Noto Sans Thai](https://fonts.google.com/noto/specimen/Noto+Sans+Thai) is a free, open-source font from Google's [Noto](../../terms/noto-fonts.md) project, covering the script's characters and the OpenType features they need (see OpenType and Text shaping)                                                                                    | Treat the typeface as a foundational choice, and confirm it covers every language you support that uses the script (see [font coverage](../../terms/font-coverage.md)), not just one                                                                                                                                                                                                                                                           |
| [OpenType](../../terms/opentype.md)                                                                | The font must include the specific [OpenType features](../../terms/opentype-features.md) for positioning the vowel marks and tone marks above and below the consonant (including stacking a tone mark above an upper vowel mark) and for composing or decomposing certain vowel signs, beyond plain glyph substitution; it needs no glyph reordering | A font can cover the characters and still leave these features out, so confirm it actually ships them, not just the base glyphs<sup>5</sup>. See the Text shaping row below                                                                                                                                                                                                                                                                    |
| [Text direction](text-direction.md)                                                                | [Left to right](left-to-right.md)<sup>6</sup>                                                                                                                                                                                                                                                                                                        | Left-aligned text as the default                                                                                                                                                                                                                                                                                                                                                                                                               |
| [Text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md)      | Shaping happens at render time: the platform's [shaping engine](../../terms/shaping-engine.md) reads the font's OpenType features (see OpenType above) and positions the stacked vowel marks and tone marks for correct display                                                                                                                      | A correct font is necessary but not sufficient: a tool or pipeline that places glyphs without shaping renders the script wrong even with a fully-featured font. Test in the actual design tools your team uses, not just the browser                                                                                                                                                                                                           |
| [Tone marks](tone-mark.md)                                                                         | Four tone marks sit above the consonant, stacking above an upper vowel mark when both are present<sup>7</sup>                                                                                                                                                                                                                                        | Test a syllable with both an above-vowel and a tone mark so the marks stack in the right order; loose [letter spacing](../../terms/letter-spacing.md) can collide with the stacked marks and does nothing to show word boundaries the text itself does not mark                                                                                                                                                                                |
| [Unicode](../../terms/unicode.md) block                                                            | Thai, [U+0E00 to U+0E7F](https://www.unicode.org/charts/PDF/U0E00.pdf)                                                                                                                                                                                                                                                                               | No special handling beyond ensuring [font coverage](../../terms/font-coverage.md) of the block                                                                                                                                                                                                                                                                                                                                                 |
| Vowel marks                                                                                        | A vowel mark can sit before, after, above, or below its consonant; the ones that appear to the left are stored in that visual order, so the renderer does not reorder them<sup>8</sup>                                                                                                                                                               | Thai stores its left-side vowels in visual order and does not reorder them, so do not apply reordering logic to Thai text                                                                                                                                                                                                                                                                                                                      |
| [Word segmentation](../../programming-terms/text-for-digital-products-and-the-web/segmentation.md) | Thai has no spaces between words, so line breaking relies on dictionary-based segmentation; a zero-width space can mark an explicit break point<sup>9</sup>                                                                                                                                                                                          | Do not split Thai on spaces or on individual characters; line breaking, search, and truncation need a segmenter such as [ICU](../../terms/icu.md)                                                                                                                                                                                                                                                                                              |

### In practice

* **Cover the script before you commit a typeface:** confirm the font ships the Thai glyphs AND the [shaping rules](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) that position them, not just the base consonants. See [font coverage](../../terms/font-coverage.md).
* **Test with a real phrase, not a glyph grid:** type a syllable that has both an above-vowel and a tone mark and confirm they stack in the right order; then set a real Thai paragraph and confirm it wraps at word boundaries rather than mid-word. Tool support for [complex text layout](../../terms/complex-text-layout.md) varies, so test early.
* **Treat word breaking as a first-class problem, not just the script:** because Thai has no spaces, line breaking, search, and truncation all depend on dictionary-based [word segmentation](../../programming-terms/text-for-digital-products-and-the-web/segmentation.md), which is language- and library-specific. Do not split Thai on spaces or on individual characters; use a segmenter such as [ICU](../../terms/icu.md), and pull per-language conventions from [locale](../../terms/locale.md) data that Unicode's [CLDR](../../terms/cldr.md) publishes.
* **If a rule above is not documented, you may be the source:** for an under-resourced language the conventions may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Abugida](abugida.md) · [Autonym](../../terms/autonym.md) · [Bidirectional text](bidirectional-text.md) · [Brahmic scripts](brahmic-scripts.md) · [CLDR](../../terms/cldr.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Devanagari](devanagari.md) · [Font](../../terms/font.md) · [Font coverage](../../terms/font-coverage.md) · [Glyph](../../terms/glyph.md) · [ICU](../../terms/icu.md) · [Language](../linguistics/language.md) · [Left-to-right](left-to-right.md) · [Letter spacing](../../terms/letter-spacing.md) · [Locale](../../terms/locale.md) · [Mark](mark.md) · [Noto fonts](../../terms/noto-fonts.md) · [OpenType](../../terms/opentype.md) · [OpenType features](../../terms/opentype-features.md) · [Orthography](orthography.md) · [Script](script.md) · [Script rules](script-rules.md) · [Segmentation](../../programming-terms/text-for-digital-products-and-the-web/segmentation.md) · [Shaping engine](../../terms/shaping-engine.md) · [Symbol](symbol.md) · [Text direction](text-direction.md) · [Text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Tone mark](tone-mark.md) · [Typeface](../../terms/typeface.md) · [Unicode](../../terms/unicode.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [Developing OpenType Fonts for Thai Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/thai)
* Design tools: [Noto Sans Thai (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Thai)
* Foundations: [Unicode Thai code chart (U+0E00)](https://www.unicode.org/charts/PDF/U0E00.pdf)

### Sources

1. The Thai script is used to write the Thai language and other Southeast Asian languages, such as Kuy, Lanna Tai, and Pali - The Unicode Standard, Version 17.0, Chapter 16: Southeast Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/)
2. Thai is a member of the Indic family of scripts descended from Brahmi, and in common with most Brahmi-derived scripts each Thai consonant letter represents a syllable possessing an inherent vowel sound - The Unicode Standard, Version 17.0, Chapter 16: Southeast Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/)
3. Thai modifies the original Brahmi letter shapes and extends the number of letters to accommodate features of the Thai language, including tone marks derived from superscript digits - The Unicode Standard, Version 17.0, Chapter 16: Southeast Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/)
4. This annex describes specifications for the positioning of characters in text containing characters flowing from right to left, such as Arabic or Hebrew - Unicode Standard Annex #9: Unicode Bidirectional Algorithm [https://www.unicode.org/reports/tr9/](https://www.unicode.org/reports/tr9/)
5. The Thai shaping engine positions the vowel marks and tone marks on the base consonant with the OpenType mark (mark-to-base) and mkmk (mark-to-mark) features - Developing OpenType Fonts for Thai Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/thai](https://learn.microsoft.com/en-us/typography/script-development/thai)
6. As in all scripts of this family, the predominant writing direction of Thai is from left to right - The Unicode Standard, Version 17.0, Chapter 16: Southeast Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/)
7. For the purpose of rendering, the Thai combining marks above (U+0E31, U+0E34..U+0E37, U+0E47..U+0E4E) should be displayed outward from the base character they modify, in the order in which they appear in the text - The Unicode Standard, Version 17.0, Chapter 16: Southeast Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/)
8. In the Thai encoding, the letter-sized glyphs that are placed before (left of) the base consonant letter, in full or partial representation of a vowel sign, are, in fact, encoded as separate characters that are typed and stored before the base consonant character. This encoding for left-side Thai vowel sign glyphs (and similarly in Lao and in Tai Viet) differs from the conventions for all other Indic scripts, which uniformly encode all vowels after the base consonant - The Unicode Standard, Version 17.0, Chapter 16: Southeast Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/)
9. Thai words are not separated by spaces; instead, spaces are introduced where Western typography would use a comma or period, and a zero-width space (U+200B) can be used to indicate explicit word or line break opportunities - The Unicode Standard, Version 17.0, Chapter 16: Southeast Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-16/)
