---
term: Wancho script
slug: wancho-script
aliases: []
level: advanced
depth: core
summary: >-
  The Wancho script is used to write the Wancho language of Arunachal Pradesh,
  India.
related:
  - alphabet
  - ol-chiki
  - warang-citi
  - tone-mark
  - endangered-language
status: voice-passed
version_added: 0.1
updated: 2026-07-08T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Noto Sans Wancho (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Wancho
    type: design-tool
  - title: Unicode Wancho code chart (U+1E2C0)
    url: https://www.unicode.org/charts/PDF/U1E2C0.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Wancho script

## Definition

The Wancho [script](script.md) is used to write the Wancho language of Arunachal Pradesh, India. It is an [alphabet](alphabet.md) recently devised to write Wancho,<sup>1</sup> a Sino-Tibetan language used mainly in the southeast of Arunachal Pradesh, and also in Assam, Nagaland, Myanmar, and Bhutan.<sup>2</sup> It was devised between 2001 and 2012 by Banwang Losu, a teacher in Longding District, Arunachal Pradesh.<sup>3</sup>

For example, the Wancho word 𞋝𞋀𞋔 (ŋak, "banana leaf") is written left to right, each vowel and consonant its own full letter.

{% hint style="info" %}
This glossary doesn't cover every Wancho script property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Wancho script profile

These properties of the Wancho script apply to any language that uses it in its [writing system](writing-system.md). Beyond the [script rules](script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](orthography.md).

| Property                             | Wancho script                                                                                                                                           |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Autonym](../linguistics/autonym.md) | Not attested in the sources cited here; the script is referred to as "Wancho" in the Latin alphabet                                                     |
| Languages                            | Wancho                                                                                                                                                  |
| Letter case                          | None (no uppercase and lowercase)                                                                                                                       |
| [Marks](mark.md)                     | [Tone marks](tone-mark.md) sit on vowel letters to write tone (Wancho is a tonal language); the vowels themselves are full letters, not dependent marks |
| Numerals                             | Wancho digits (U+1E2F0 to U+1E2F9), alongside common ASCII digits                                                                                       |
| Script type                          | [Alphabet](alphabet.md)                                                                                                                                 |
| [Symbols](symbol.md)                 | Full letters for consonants and vowels                                                                                                                  |

### Wancho script rules and digital use considerations

If your design system supports languages that use the Wancho script, here are some considerations to keep in mind:

| Rule or feature                                                                                             | How it works in the Wancho script                                                                                                                                                                                                                                                                   | Design systems                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| ----------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Bidirectional text](bidirectional-text.md)                                                                 | The script runs left to right, but a line can still become bidirectional when right-to-left content (an Arabic or Hebrew name, for example) is embedded in it                                                                                                                                       | Then the embedded right-to-left run needs the Unicode bidirectional algorithm to reorder correctly; isolate embedded content whose direction you do not control, so it cannot disturb the surrounding text<sup>4</sup>                                                                                                                                                                                                                          |
| [Complex text layout](../../programming-terms/text-for-digital-products-and-the-web/complex-text-layout.md) | Not required for ordering: no reordering or contextual shaping,<sup>5</sup> the one shaping job being tone-mark positioning                                                                                                                                                                         | So there is no reordering or contextual analysis; see the OpenType and Text shaping rows below for the tone-mark positioning                                                                                                                                                                                                                                                                                                                    |
| [Font](../../programming-terms/text-for-digital-products-and-the-web/font.md) (open source)                 | [Noto Sans Wancho](https://fonts.google.com/noto/specimen/Noto+Sans+Wancho) is a free, open-source font from Google's [Noto](../../design-terms/typography/noto-fonts.md) project, covering the script's characters and the OpenType features they need (see OpenType and Text shaping)             | Treat the typeface as a foundational choice, and confirm it covers every language you support that uses the script (see [font coverage](../../programming-terms/text-for-digital-products-and-the-web/font-coverage.md)), not just one                                                                                                                                                                                                          |
| [OpenType](../../design-terms/typography/opentype.md)                                                       | The font uses standard [OpenType features](../../design-terms/typography/opentype-features.md): glyph substitution, [kerning](../../design-terms/typography/kerning.md), and optional ligatures, plus mark positioning to place the tone marks correctly over their vowel letters<sup>6</sup>       | Confirm the font ships the mark-positioning feature, not just the base letters, so the tone marks land on the right vowels. See the Text shaping row below                                                                                                                                                                                                                                                                                      |
| [Text direction](text-direction.md)                                                                         | [Left to right](left-to-right.md)                                                                                                                                                                                                                                                                   | Left-aligned text as the default                                                                                                                                                                                                                                                                                                                                                                                                                |
| [Text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md)               | Shaping is limited to mark positioning: the [shaping engine](../../programming-terms/text-for-digital-products-and-the-web/shaping-engine.md) reads the font's OpenType features (see OpenType above) and places the tone marks on their vowel letters; there are no positional forms or reordering | A correct font is necessary but not sufficient: a tool that places glyphs without shaping can misplace the tone marks. Test in the actual design tools your team uses, not just the browser                                                                                                                                                                                                                                                     |
| [Tone marks](tone-mark.md)                                                                                  | Wancho is a tonal language, and tone is written with tone marks placed on the vowel letters<sup>7</sup>                                                                                                                                                                                             | The font has to place the tone marks correctly on their vowel letters, so test mark placement, not just the base letters                                                                                                                                                                                                                                                                                                                        |
| [Unicode](../../programming-terms/text-for-digital-products-and-the-web/unicode.md) block                   | Wancho, [U+1E2C0 to U+1E2FF](https://www.unicode.org/charts/PDF/U1E2C0.pdf)                                                                                                                                                                                                                         | The Wancho script is a very recent, purpose-built community script for a small language community, so fonts, a [keyboard layout](../../programming-terms/text-for-digital-products-and-the-web/keyboard-layout.md), and rendering for it are a concrete deliverable; a Latin or [Devanagari](devanagari.md) font will not render it, so confirm [font coverage](../../programming-terms/text-for-digital-products-and-the-web/font-coverage.md) |

### In practice

* **Cover the script, its tone marks, and a way to type it:** confirm the font ships the Wancho letters, tone marks, and digits, positions the tone marks correctly, and is paired with a [keyboard layout](../../programming-terms/text-for-digital-products-and-the-web/keyboard-layout.md). See [font coverage](../../programming-terms/text-for-digital-products-and-the-web/font-coverage.md).
* **Test with a real word, tone marks included:** set a real Wancho word with its tone marks and confirm the marks sit on the right letters at your text sizes.
* **Check the orthography, and which script the community uses:** Wancho is written in the Wancho script, Devanagari, and Latin, so do not assume one script. Pull per-language conventions from [locale](../../programming-terms/text-for-digital-products-and-the-web/locale.md) data that Unicode's [CLDR](../../programming-terms/text-for-digital-products-and-the-web/cldr.md) publishes.
* **If a rule above is not documented, you may be the source:** for an [endangered](../linguistics/endangered-language.md) or under-resourced language the conventions may not be in any library yet. Capture them with fluent speakers, write them into your specs and tokens, and add them here (see [how to contribute](../../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Alphabet](alphabet.md) · [Autonym](../linguistics/autonym.md) · [Bidirectional text](bidirectional-text.md) · [CLDR](../../programming-terms/text-for-digital-products-and-the-web/cldr.md) · [Complex text layout](../../programming-terms/text-for-digital-products-and-the-web/complex-text-layout.md) · [Devanagari script](devanagari.md) · [Endangered language](../linguistics/endangered-language.md) · [Font](../../programming-terms/text-for-digital-products-and-the-web/font.md) · [Font coverage](../../programming-terms/text-for-digital-products-and-the-web/font-coverage.md) · [Glyph](../../programming-terms/text-for-digital-products-and-the-web/glyph.md) · [Kerning](../../design-terms/typography/kerning.md) · [Keyboard layout](../../programming-terms/text-for-digital-products-and-the-web/keyboard-layout.md) · [Language](../linguistics/language.md) · [Latin script](latin-script.md) · [Left-to-right](left-to-right.md) · [Locale](../../programming-terms/text-for-digital-products-and-the-web/locale.md) · [Mark](mark.md) · [Noto fonts](../../design-terms/typography/noto-fonts.md) · [Ol Chiki script](ol-chiki.md) · [OpenType](../../design-terms/typography/opentype.md) · [OpenType features](../../design-terms/typography/opentype-features.md) · [Orthography](orthography.md) · [Script](script.md) · [Script rules](script-rules.md) · [Shaping engine](../../programming-terms/text-for-digital-products-and-the-web/shaping-engine.md) · [Symbol](symbol.md) · [Text direction](text-direction.md) · [Text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Tone mark](tone-mark.md) · [Typeface](../../design-terms/typography/typeface.md) · [Unicode](../../programming-terms/text-for-digital-products-and-the-web/unicode.md) · [Warang Citi script](warang-citi.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Design tools: [Noto Sans Wancho (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Wancho)
* Foundations: [Unicode Wancho code chart (U+1E2C0)](https://www.unicode.org/charts/PDF/U1E2C0.pdf)

### Sources

1. The Wancho script is an alphabet recently devised to write the Wancho language - The Unicode Standard, Version 17.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/)
2. Wancho is a Sino-Tibetan language used mainly in the southeast of Arunachal Pradesh, as well as in Assam, Nagaland, Myanmar, and Bhutan - The Unicode Standard, Version 17.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/)
3. The script was devised between 2001 and 2012 by Banwang Losu, a teacher at a government middle school in his home village in Longding District, Arunachal Pradesh - Michael Everson, Proposal to encode the Wancho script in the UCS (L2/17-067R2, N4787R2) [https://www.unicode.org/L2/L2017/17067r2-n4787r2-wancho.pdf](https://www.unicode.org/L2/L2017/17067r2-n4787r2-wancho.pdf)
4. This annex describes specifications for the positioning of characters in text containing characters flowing from right to left, such as Arabic or Hebrew - Unicode Standard Annex #9: Unicode Bidirectional Algorithm [https://www.unicode.org/reports/tr9/](https://www.unicode.org/reports/tr9/)
5. Wancho is a simple alphabetic script comprised of letters which represent both consonants and vowels. There are no conjunct characters - Michael Everson, Proposal to encode the Wancho script in the UCS (L2/17-067R2, N4787R2) [https://www.unicode.org/L2/L2017/17067r2-n4787r2-wancho.pdf](https://www.unicode.org/L2/L2017/17067r2-n4787r2-wancho.pdf)
6. Relative positions of the four diacritical marks over the vowels of Wancho; generally they are centred over the chief curve at the top of the character - Michael Everson, Proposal to encode the Wancho script in the UCS (L2/17-067R2, N4787R2) [https://www.unicode.org/L2/L2017/17067r2-n4787r2-wancho.pdf](https://www.unicode.org/L2/L2017/17067r2-n4787r2-wancho.pdf)
7. Diacritical marks are used on vowel letters to indicate tone - Michael Everson, Proposal to encode the Wancho script in the UCS (L2/17-067R2, N4787R2) [https://www.unicode.org/L2/L2017/17067r2-n4787r2-wancho.pdf](https://www.unicode.org/L2/L2017/17067r2-n4787r2-wancho.pdf)
