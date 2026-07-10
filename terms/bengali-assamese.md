---
term: Bengali-Assamese
slug: bengali-assamese
aliases:
  - bengali
  - bangla
  - eastern nagari
level: intermediate
depth: core
summary: Bengali-Assamese is a script used to write Bengali (Bangla), Assamese, and other languages of eastern South Asia.
related:
  - abugida
  - brahmic-scripts
  - devanagari
  - conjunct
  - matra
status: voice-passed
version_added: 0.1
updated: 2026-07-06
contributors:
  - sam-gordashko
further_reading:
  - title: Developing OpenType Fonts for Bengali Script (Microsoft)
    url: https://learn.microsoft.com/en-us/typography/script-development/bengali
    type: code
  - title: Noto Sans Bengali (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Bengali
    type: design-tool
  - title: 'Unicode Bengali code chart (U+0980)'
    url: https://www.unicode.org/charts/PDF/U0980.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Bengali-Assamese

## Definition

Bengali-Assamese is a [script](../language-terms/writing-systems-and-scripts/script.md) used to write Bengali (Bangla), Assamese, and other languages of eastern South Asia.<sup>1</sup> It is a [Brahmic](brahmic-scripts.md) [abugida](../language-terms/writing-systems-and-scripts/abugida.md) historically related to Devanagari: each consonant carries an inherent vowel that added marks can change.<sup>2</sup>

For example, বাংলা ("Bangla") is the name of the Bengali language, written in this script.

{% hint style="info" %}
This glossary doesn't cover every Bengali-Assamese property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Bengali-Assamese profile

These properties of the Bengali-Assamese script apply to any language that uses it in its [writing system](../language-terms/writing-systems-and-scripts/writing-system.md). Beyond the [script rules](../language-terms/writing-systems-and-scripts/script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

| Property | Bengali-Assamese |
| --- | --- |
| [Autonym](autonym.md) | বাংলা লিপি |
| Languages | Bengali (Bangla), Assamese, and others |
| Letter case | None (no uppercase and lowercase) |
| [Marks](../language-terms/writing-systems-and-scripts/mark.md) | Dependent vowels ([matra](../language-terms/writing-systems-and-scripts/matra.md), some written to the left), the hasant (the [virama](../language-terms/writing-systems-and-scripts/virama.md)) that forms conjuncts, and nasalization marks |
| Numerals | Bengali digits ০ to ৯ (alongside common ASCII digits) |
| Script type | [Abugida](../language-terms/writing-systems-and-scripts/abugida.md) |
| [Symbols](../language-terms/writing-systems-and-scripts/symbol.md) | Consonants carrying an inherent vowel, plus independent vowels |

### Bengali-Assamese rules and digital use considerations

If your design system supports languages that use the Bengali-Assamese script, here are some considerations to keep in mind:

| Rule or feature | How it works in the Bengali-Assamese script | Design systems |
| --- | --- | --- |
| [Bidirectional text](../language-terms/writing-systems-and-scripts/bidirectional-text.md) | The script runs left to right, but a line can still become bidirectional when right-to-left content (an Arabic or Hebrew name, for example) is embedded in it | Then the embedded right-to-left run needs the Unicode bidirectional algorithm to reorder correctly; isolate embedded content whose direction you do not control, so it cannot disturb the surrounding text<sup>3</sup> |
| [Complex text layout](complex-text-layout.md) | Yes, shaping required | Handled by the font's [OpenType](opentype.md) rules and applied at render time by the platform's [text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md); see the OpenType and Text shaping rows below for what your font needs to support. Get it wrong and the text renders incorrectly, not just unstyled |
| [Conjuncts](../language-terms/writing-systems-and-scripts/conjunct.md) | Consonant clusters combine into conjunct forms using the hasant (the [virama](../language-terms/writing-systems-and-scripts/virama.md))<sup>4</sup> | Confirm the font forms conjunct glyphs; if a full conjunct is unavailable the documented fallback is half-form glyphs, not the cluster shown as separate symbols<sup>5</sup> |
| [Hanging baseline](../language-terms/writing-systems-and-scripts/hanging-baseline.md) | Symbols join along a top line and hang from it<sup>6</sup> | You cannot add spacing that breaks the top line joining the symbols |
| [OpenType](opentype.md) | The font must include the specific [OpenType features](opentype-features.md) for conjunct and half-form composition, reordering of the pre-base (left-side) vowel sign, below-base consonant forms, and positioning of the dependent-vowel and other marks above and below the base, beyond plain glyph substitution | A font can cover the characters and still leave these features out, so confirm it actually ships them, not just the base glyphs<sup>7</sup>. See the Text shaping row below |
| [Reordering](../programming-terms/text-for-digital-products-and-the-web/reordering.md) | A left-side vowel mark (dependent vowel) is typed after its consonant but displays before it, so the renderer reorders it<sup>8</sup> | A tool or font that cannot reorder places the vowel in the wrong position, so test a word with a left-side vowel mark |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | [Left to right](../language-terms/writing-systems-and-scripts/left-to-right.md)<sup>9</sup> | Left-aligned text as the default |
| [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) | Shaping happens at render time: the platform's [shaping engine](shaping-engine.md) reads the font's OpenType features (see OpenType above) and reorders the vowel signs, forms the conjuncts, and positions the marks for correct display | A correct font is necessary but not sufficient: a tool or pipeline that places glyphs without shaping renders the script wrong even with a fully-featured font. Test in the actual design tools your team uses, not just the browser |
| [Unicode](unicode.md) block | Bengali, [U+0980 to U+09FF](https://www.unicode.org/charts/PDF/U0980.pdf) | The block covers Bengali; Assamese uses letters Bengali does not, among them ৰ for "ra" and ৱ for "wa", so "supports Bengali" is not the same as "supports Assamese". Confirm [font coverage](font-coverage.md) of the Assamese letters too<sup>10</sup> |

### In practice

* **Cover the script before you commit a typeface:** confirm the font ships the Bengali glyphs AND the [shaping rules](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) that position them, plus the Assamese symbols such as ৰ and ৱ if you support Assamese, not just the base Bengali symbols. [Noto Sans Bengali](https://fonts.google.com/noto/specimen/Noto+Sans+Bengali) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Test with a real word, not a glyph grid:** type a word with a conjunct and a left-side vowel mark and confirm they form and reorder; if you support Assamese, test a word that uses ৰ and confirm the Assamese "ra" renders, since the Bengali র and Assamese ৰ are different [characters](character.md) that are easy to swap in data. Tool support for [complex text layout](complex-text-layout.md) varies, so test early.
* **Check the orthography per language, not just the script:** Bengali and Assamese share the script and still differ in which symbols they use. Do not hardcode one language's choices; pull them from [locale](locale.md) data. Unicode's [CLDR](cldr.md) publishes per-language conventions as machine-readable data.
* **If a rule above is not documented, you may be the source:** for an under-resourced language the conventions may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Abugida](../language-terms/writing-systems-and-scripts/abugida.md) · [Autonym](autonym.md) · [Bidirectional text](../language-terms/writing-systems-and-scripts/bidirectional-text.md) · [Brahmic scripts](brahmic-scripts.md) · [Character](character.md) · [CLDR](cldr.md) · [Complex text layout](complex-text-layout.md) · [Conjunct](../language-terms/writing-systems-and-scripts/conjunct.md) · [Devanagari](devanagari.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [Hanging baseline](../language-terms/writing-systems-and-scripts/hanging-baseline.md) · [Language](../language-terms/linguistics/language.md) · [Left-to-right](../language-terms/writing-systems-and-scripts/left-to-right.md) · [Locale](locale.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Matra](../language-terms/writing-systems-and-scripts/matra.md) · [Noto fonts](noto-fonts.md) · [OpenType](opentype.md) · [OpenType features](opentype-features.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Reordering](../programming-terms/text-for-digital-products-and-the-web/reordering.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Shaping engine](shaping-engine.md) · [Syloti Nagri](syloti-nagri.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Virama](../language-terms/writing-systems-and-scripts/virama.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Code & specs: [Developing OpenType Fonts for Bengali Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/bengali)
* Design tools: [Noto Sans Bengali (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Bengali)
* Foundations: [Unicode Bengali code chart (U+0980)](https://www.unicode.org/charts/PDF/U0980.pdf)

### Sources

1. The Bangla script is used for writing languages such as Bangla, Assamese, Bishnupriya Manipuri, Daphla, Garo, Hallam, Khasi, Mizo, Munda, Naga, Rian, and Santali - The Unicode Standard, Version 17.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)
2. The Bangla script is a North Indian script historically related to Devanagari, and, in common with the other scripts of the region, is an abugida in which each consonant carries an inherent vowel - The Unicode Standard, Version 17.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)
3. This annex describes specifications for the positioning of characters in text containing characters flowing from right to left, such as Arabic or Hebrew - Unicode Standard Annex #9: Unicode Bidirectional Algorithm [https://www.unicode.org/reports/tr9/](https://www.unicode.org/reports/tr9/)
4. Like other Brahmic scripts, Bangla uses the hasant to form conjunct characters from consonant clusters - The Unicode Standard, Version 17.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)
5. If the coded character sequence would normally render with a full conjunct, but such a conjunct is not available, the fallback rendering is to use half-forms - The Unicode Standard, Version 17.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)
6. In Bengali a top bar joins the symbols, and the hanging baseline is based on that top bar - Bengali (r12a script notes) [https://r12a.github.io/scripts/beng/bn.html](https://r12a.github.io/scripts/beng/bn.html)
7. A font's OpenType rules select and position the correct Bengali forms (conjuncts, reordered vowel marks, mark placement), which the shaping engine applies when the text is rendered - Developing OpenType Fonts for Bengali Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/bengali](https://learn.microsoft.com/en-us/typography/script-development/bengali)
8. Indic-script rendering reorders elements from the logical (character) order to the visual (glyph) order, which is why a left-side vowel sign stored after its consonant displays before it - The Unicode Standard, Version 17.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)
9. The scripts of the Indic family, including Bangla, are written from left to right - The Unicode Standard, Version 17.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)
10. Assamese employs letters not used for the Bangla language, including U+09F0 ৰ for the Assamese "ra" and U+09F1 ৱ for the Assamese "wa", along with some Assamese-specific ligature forms - The Unicode Standard, Version 17.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)
