---
term: Wancho script
slug: wancho-script
aliases: []
level: advanced
depth: core
summary: The Wancho script is used to write the Wancho language of Arunachal Pradesh, India.
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

The Wancho [script](../language-terms/writing-systems-and-scripts/script.md) is used to write the Wancho language of Arunachal Pradesh, India. It is an [alphabet](../language-terms/writing-systems-and-scripts/alphabet.md) recently devised to write Wancho,<sup>1</sup> a Sino-Tibetan language used mainly in the southeast of Arunachal Pradesh, and also in Assam, Nagaland, Myanmar, and Bhutan.<sup>2</sup> It was devised between 2001 and 2012 by Banwang Losu, a teacher in Longding District, Arunachal Pradesh.<sup>3</sup>

For example, the Wancho word 𞋝𞋀𞋔 (ŋak, "banana leaf") is written left to right, each vowel and consonant its own full letter.

{% hint style="info" %}
This glossary doesn't cover every Wancho script property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Wancho script profile

These properties of the Wancho script apply to any language that uses it in its [writing system](../language-terms/writing-systems-and-scripts/writing-system.md). Beyond the [script rules](../language-terms/writing-systems-and-scripts/script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

| Property | Wancho script |
| --- | --- |
| [Autonym](autonym.md) | Not attested in the sources cited here; the script is referred to as "Wancho" in the Latin alphabet |
| Languages | Wancho |
| Letter case | None (no uppercase and lowercase) |
| [Marks](../language-terms/writing-systems-and-scripts/mark.md) | [Tone marks](../language-terms/writing-systems-and-scripts/tone-mark.md) sit on vowel letters to write tone (Wancho is a tonal language); the vowels themselves are full letters, not dependent marks |
| Numerals | Wancho digits (U+1E2F0 to U+1E2F9), alongside common ASCII digits |
| Script type | [Alphabet](../language-terms/writing-systems-and-scripts/alphabet.md) |
| [Symbols](../language-terms/writing-systems-and-scripts/symbol.md) | Full letters for consonants and vowels |

### Wancho script rules and digital use considerations

If your design system supports languages that use the Wancho script, here are some considerations to keep in mind:

| Rule or feature | How it works in the Wancho script | Design systems |
| --- | --- | --- |
| [Complex text layout](complex-text-layout.md) | Not required for ordering: no reordering or contextual shaping,<sup>4</sup> though tone marks position on their letters | Not complex to shape, no reordering or contextual analysis; the platform's [text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) and the font's [OpenType](opentype.md) rules mostly map each letter straight to its glyph, the one positioning job being the tone marks |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | Left to right | Left-aligned text as the default |
| [Tone marks](../language-terms/writing-systems-and-scripts/tone-mark.md) | Wancho is a tonal language, and tone is written with tone marks placed on the vowel letters<sup>5</sup> | The font has to place the tone marks correctly on their vowel letters, so test mark placement, not just the base letters |
| [Unicode](unicode.md) block | Wancho, [U+1E2C0 to U+1E2FF](https://www.unicode.org/charts/PDF/U1E2C0.pdf) | The Wancho script is a very recent, purpose-built community script for a small language community, so fonts, a [keyboard layout](keyboard-layout.md), and rendering for it are a concrete deliverable; a Latin or [Devanagari](devanagari.md) font will not render it, so confirm [font coverage](font-coverage.md) |

### In practice

* **Cover the script, its tone marks, and a way to type it:** confirm the font ships the Wancho letters, tone marks, and digits, positions the tone marks correctly, and is paired with a [keyboard layout](keyboard-layout.md). [Noto Sans Wancho](https://fonts.google.com/noto/specimen/Noto+Sans+Wancho) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Test with a real word, tone marks included:** set a real Wancho word with its tone marks and confirm the marks sit on the right letters at your text sizes.
* **Check the orthography, and which script the community uses:** Wancho is written in the Wancho script, Devanagari, and Latin, so do not assume one script. Pull per-language conventions from [locale](locale.md) data that Unicode's [CLDR](cldr.md) publishes.
* **If a rule above is not documented, you may be the source:** for an [endangered](endangered-language.md) or under-resourced language the conventions may not be in any library yet. Capture them with fluent speakers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Alphabet](../language-terms/writing-systems-and-scripts/alphabet.md) · [Autonym](autonym.md) · [CLDR](cldr.md) · [Complex text layout](complex-text-layout.md) · [Devanagari](devanagari.md) · [Endangered language](endangered-language.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [Keyboard layout](keyboard-layout.md) · [Language](../language-terms/linguistics/language.md) · [Latin script](../language-terms/writing-systems-and-scripts/latin-script.md) · [Locale](locale.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Noto fonts](noto-fonts.md) · [Ol Chiki](ol-chiki.md) · [OpenType](opentype.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Tone mark](../language-terms/writing-systems-and-scripts/tone-mark.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Warang Citi](warang-citi.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Design tools: [Noto Sans Wancho (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Wancho)
* Foundations: [Unicode Wancho code chart (U+1E2C0)](https://www.unicode.org/charts/PDF/U1E2C0.pdf)

### Sources

1. The Wancho script is an alphabet recently devised to write the Wancho language - The Unicode Standard, Version 17.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/)
2. Wancho is a Sino-Tibetan language used mainly in the southeast of Arunachal Pradesh, as well as in Assam, Nagaland, Myanmar, and Bhutan - The Unicode Standard, Version 17.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/)
3. The script was devised between 2001 and 2012 by Banwang Losu, a teacher at a government middle school in his home village in Longding District, Arunachal Pradesh - Michael Everson, Proposal to encode the Wancho script in the UCS (L2/17-067R2, N4787R2) [https://www.unicode.org/L2/L2017/17067r2-n4787r2-wancho.pdf](https://www.unicode.org/L2/L2017/17067r2-n4787r2-wancho.pdf)
4. Wancho is a simple alphabetic script comprised of letters which represent both consonants and vowels. There are no conjunct characters - Michael Everson, Proposal to encode the Wancho script in the UCS (L2/17-067R2, N4787R2) [https://www.unicode.org/L2/L2017/17067r2-n4787r2-wancho.pdf](https://www.unicode.org/L2/L2017/17067r2-n4787r2-wancho.pdf)
5. Diacritical marks are used on vowel letters to indicate tone - Michael Everson, Proposal to encode the Wancho script in the UCS (L2/17-067R2, N4787R2) [https://www.unicode.org/L2/L2017/17067r2-n4787r2-wancho.pdf](https://www.unicode.org/L2/L2017/17067r2-n4787r2-wancho.pdf)
</content>
