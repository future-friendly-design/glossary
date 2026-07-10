---
term: Ol Chiki
slug: ol-chiki
aliases:
  - Ol Chemet
  - Ol Cemet'
  - Santali alphabet
level: advanced
depth: core
summary: Ol Chiki is a script used to write Santali, a Munda language of India.
related:
  - alphabet
  - brahmic-scripts
  - warang-citi
  - wancho-script
  - devanagari
status: voice-passed
version_added: 0.1
updated: 2026-07-08T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Noto Sans Ol Chiki (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Ol+Chiki
    type: design-tool
  - title: Unicode Ol Chiki code chart (U+1C50)
    url: https://www.unicode.org/charts/PDF/U1C50.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Ol Chiki

## Definition

Ol Chiki is a [script](../language-terms/writing-systems-and-scripts/script.md) used to write Santali, a Munda language of India.<sup>1</sup> It is an [alphabet](../language-terms/writing-systems-and-scripts/alphabet.md), with a full letter for every vowel rather than the dependent vowel marks of the region's [Brahmic](brahmic-scripts.md) abugidas, and it is written left to right. It was created in 1925 by Pandit Raghunath Murmu,<sup>2</sup> and is used primarily for the southern [dialect](dialect.md) of Santali spoken in the state of Odisha.<sup>3</sup>

For example, the script's own name ᱚᱞ ᱪᱤᱠᱤ ("Ol Chiki") is written left to right, each vowel and consonant its own full letter.

{% hint style="info" %}
This glossary doesn't cover every Ol Chiki property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Ol Chiki profile

These properties of Ol Chiki apply to any language that uses it in its [writing system](../language-terms/writing-systems-and-scripts/writing-system.md). Beyond the [script rules](../language-terms/writing-systems-and-scripts/script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

| Property | Ol Chiki |
| --- | --- |
| [Autonym](autonym.md) | ᱚᱞ ᱪᱤᱠᱤ |
| Languages | Santali |
| Letter case | None (no uppercase and lowercase) |
| [Marks](../language-terms/writing-systems-and-scripts/mark.md) | Vowels are full letters, not dependent marks; a small set of modifier symbols is also encoded<sup>4</sup> |
| Numerals | Ol Chiki digits (U+1C50 to U+1C59), alongside common ASCII digits |
| Script type | [Alphabet](../language-terms/writing-systems-and-scripts/alphabet.md) |
| [Symbols](../language-terms/writing-systems-and-scripts/symbol.md) | Full letters for consonants and vowels (30 letters)<sup>5</sup> |

### Ol Chiki rules and digital use considerations

If your design system supports languages that use Ol Chiki, here are some considerations to keep in mind:

| Rule or feature | How it works in Ol Chiki | Design systems |
| --- | --- | --- |
| [Complex text layout](complex-text-layout.md) | Not required: a linear alphabet, rendered directly (no conjuncts or reordering)<sup>6</sup> | Not complex to shape, no reordering or contextual analysis; the platform's [text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) and the font's [OpenType](opentype.md) rules mostly map each letter straight to its glyph |
| Full vowel letters | Every vowel is a full letter, unlike the dependent vowel signs of the region's [Brahmic](brahmic-scripts.md) abugidas | A Latin or [Devanagari](devanagari.md) font will not render Ol Chiki, so you need a [typeface](typeface.md) and [font](font.md) with Ol Chiki coverage |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | [Left to right](../language-terms/writing-systems-and-scripts/left-to-right.md) | Left-aligned text as the default |
| [Unicode](unicode.md) block | Ol Chiki, [U+1C50 to U+1C7F](https://www.unicode.org/charts/PDF/U1C50.pdf) | Santali is one of the scheduled languages of India with millions of speakers, and Ol Chiki has a real and growing digital footprint, so fonts, a [keyboard layout](keyboard-layout.md), and rendering for it are a concrete deliverable; confirm [font coverage](font-coverage.md) |

### In practice

* **Cover the script and give people a way to type it:** confirm the font ships the Ol Chiki letters and digits, and pair it with a [keyboard layout](keyboard-layout.md) so the community can actually enter text. [Noto Sans Ol Chiki](https://fonts.google.com/noto/specimen/Noto+Sans+Ol+Chiki) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Test with a real word, not a letter grid:** set a real Santali word and confirm the letters and any modifier symbols render cleanly at your text sizes.
* **Check the orthography, and which script the community uses:** Santali is written in Ol Chiki, Devanagari, Bengali, Odia, and Latin in different places, so do not assume one script. Pull per-language conventions from [locale](locale.md) data that Unicode's [CLDR](cldr.md) publishes.
* **If a rule above is not documented, you may be the source:** the conventions for a use you support may not be in any library yet. Capture them with fluent speakers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Alphabet](../language-terms/writing-systems-and-scripts/alphabet.md) · [Autonym](autonym.md) · [Brahmic scripts](brahmic-scripts.md) · [CLDR](cldr.md) · [Complex text layout](complex-text-layout.md) · [Devanagari](devanagari.md) · [Dialect](dialect.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [Keyboard layout](keyboard-layout.md) · [Language](../language-terms/linguistics/language.md) · [Latin script](../language-terms/writing-systems-and-scripts/latin-script.md) · [Left-to-right](../language-terms/writing-systems-and-scripts/left-to-right.md) · [Locale](locale.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Noto fonts](noto-fonts.md) · [OpenType](opentype.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Warang Citi](warang-citi.md) · [Wancho script](wancho-script.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Design tools: [Noto Sans Ol Chiki (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Ol+Chiki)
* Foundations: [Unicode Ol Chiki code chart (U+1C50)](https://www.unicode.org/charts/PDF/U1C50.pdf)

### Sources

1. Ol Chiki is an alphabetic script invented in the 20th century to write Santali, a Munda language of India - The Unicode Standard, Version 17.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/)
2. Ol Chiki was created in 1925 by Pandit Raghunath Murmu (secondary source, interim pending an upgrade to a primary attribution) - Ol Chiki script (Wikipedia) [https://en.wikipedia.org/wiki/Ol\_Chiki\_script](https://en.wikipedia.org/wiki/Ol_Chiki_script)
3. It is used primarily for the southern dialect of Santali spoken in the state of Odisha - The Unicode Standard, Version 17.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/)
4. In addition to these, a number of modifier letters are used to indicate tone, nasalization, length, and deglottalization - Michael Everson, Final proposal to encode the Ol Chiki script in the UCS (L2/05-243R, N2984R) [https://www.unicode.org/L2/L2005/05243r-n2984-ol-chiki.pdf](https://www.unicode.org/L2/L2005/05243r-n2984-ol-chiki.pdf)
5. Characters are arranged in a 5 by 6 matrix, named in a conventional way as shown in the names list - Michael Everson, Final proposal to encode the Ol Chiki script in the UCS (L2/05-243R, N2984R) [https://www.unicode.org/L2/L2005/05243r-n2984-ol-chiki.pdf](https://www.unicode.org/L2/L2005/05243r-n2984-ol-chiki.pdf)
6. Ol Chiki is alphabetic, sharing none of the syllabic properties of the other Indic scripts - Michael Everson, Final proposal to encode the Ol Chiki script in the UCS (L2/05-243R, N2984R) [https://www.unicode.org/L2/L2005/05243r-n2984-ol-chiki.pdf](https://www.unicode.org/L2/L2005/05243r-n2984-ol-chiki.pdf)
</content>
