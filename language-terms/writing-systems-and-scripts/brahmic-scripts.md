---
term: Brahmic scripts
slug: brahmic-scripts
aliases:
  - Indic scripts
  - Brahmic family
level: intermediate
depth: core
summary: >-
  Brahmic scripts are a family of related scripts used across South and
  Southeast Asia, all descended from the ancient Brahmi script.
related:
  - abugida
  - conjunct
  - matra
  - virama
  - complex-text-layout
status: voice-passed
version_added: 0.1
updated: 2026-07-07T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: 'The Unicode Standard, Chapter 12: South Asia-I'
    url: https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/
    type: authority
  - title: Noto (Google Fonts)
    url: https://fonts.google.com/noto
    type: design-tool
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Brahmic scripts

## Definition

Brahmic scripts are a family of related scripts used across South and Southeast Asia, all descended from the ancient Brahmi script.<sup>1</sup> They are almost all [abugidas](abugida.md): most symbols stand for a consonant plus an inherent vowel, generally the short /a/, which dependent vowels ([matras](matra.md)) can change.<sup>2</sup>

Brahmic is a family, not a single script: the members share a structure but differ enough that you design for each one, not for "Brahmic" as a whole. Unicode itself warns that implementations should not assume the South Indian scripts work just as Devanagari does.<sup>3</sup>

{% hint style="info" %}
This glossary doesn't cover every Brahmic script or every shared feature; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../../CONTRIBUTING.md), they will be linked.
{% endhint %}

### What unites the members

These are the traits the family holds in common. Individual members vary, so treat this as the shared starting point, not a specification for any one script.

| Shared feature                      | Across the Brahmic family                                                                                                                       | Design systems                                                                                                                                                                                                                                 |
| ----------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Origin                              | All descend from the ancient Brahmi script                                                                                                      | Because the members share one ancestor and structure, supporting one Brahmic script builds much of the infrastructure the others need                                                                                                          |
| Script type                         | Almost all are [abugidas](abugida.md): each consonant carries an inherent vowel, generally /a/                                                  | Plan for consonant-plus-vowel units, not one glyph per sound                                                                                                                                                                                   |
| Vowel marks                         | Dependent vowels ([matras](matra.md)) attach to a consonant to change its inherent vowel                                                        | Matras can attach above, below, or to either side, and some reorder ahead of their consonant, so the font's mark positioning and [reordering](../../programming-terms/text-for-digital-products-and-the-web/reordering.md) have to be in place |
| [Virama](virama.md)                 | A virama (halant) suppresses the inherent vowel<sup>4</sup>                                                                                     | The shaping engine has to act on the virama to form the right cluster, so test it rather than assuming a bare glyph                                                                                                                            |
| [Conjuncts](conjunct.md)            | Consonant clusters can combine into conjunct forms<sup>5</sup>                                                                                  | The font must ship the conjunct glyphs; confirm real clusters render, not just isolated consonants                                                                                                                                             |
| [Text direction](text-direction.md) | With minor historical exceptions, left to right<sup>6</sup>                                                                                     | Left-aligned text as the default                                                                                                                                                                                                               |
| Rendering                           | [Complex text layout](../../terms/complex-text-layout.md): real shaping, mark positioning, and sometimes reordering, not simple glyph placement | You need real [text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) and [OpenType](../../terms/opentype.md) rules; simple glyph placement renders the text wrong, not just unstyled                    |

### Members

The Brahmic family is large and this glossary doesn't cover every member; here are some to be aware of, spanning the South Asian and Southeast Asian branches, with a page linked where one exists. The Example column shows each linked script's own name, and the last column notes how each member departs from the shared pattern (verified per script, not assumed from the family). Select a linked term to navigate to its glossary page.

| Script                                  | Languages                        | Example          | Distinctive in the family                                                                                                                                             |
| --------------------------------------- | -------------------------------- | ---------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Devanagari](devanagari.md)             | Hindi, Marathi, Sanskrit, Nepali | देवनागरी         | Hangs its symbols from a continuous headline stroke ([shirorekha](shirorekha.md))                                                                                     |
| [Bengali-Assamese](bengali-assamese.md) | Bengali, Assamese                | বাংলা লিপি       | Also written along a headline ([hanging baseline](hanging-baseline.md)); its own [conjunct](conjunct.md) forms                                                        |
| [Tamil](tamil-script.md)                | Tamil, Badaga                    | தமிழ் அரிச்சுவடி | Sits on a [baseline](../../design-terms/typography/baseline.md); very few [conjuncts](conjunct.md)                                                                    |
| Telugu                                  | Telugu                           |                  | Rounded southern forms; vowel marks mostly above the consonant                                                                                                        |
| Kannada                                 | Kannada                          |                  | Rounded southern forms, closely related to Telugu                                                                                                                     |
| Malayalam                               | Malayalam                        |                  | Rounded southern forms; historically rich in conjuncts                                                                                                                |
| Gujarati                                | Gujarati                         |                  | Like Devanagari, but without the headline stroke                                                                                                                      |
| Gurmukhi                                | Punjabi                          |                  | Written along a headline                                                                                                                                              |
| Odia                                    | Odia                             |                  | Rounded, curved tops                                                                                                                                                  |
| Sinhala                                 | Sinhala                          |                  | Rounded forms                                                                                                                                                         |
| [Syloti Nagri](syloti-nagri.md)         | Sylheti                          | ꠍꠤꠟꠐꠤ ꠘꠣꠉꠞꠤ      | Small consonant set; a hasanta (like a [virama](virama.md)) forms [conjuncts](conjunct.md)                                                                            |
| [Thai](thai-script.md)                  | Thai                             | อักษรไทย         | No spaces between words, needing [word segmentation](../../programming-terms/text-for-digital-products-and-the-web/segmentation.md); some vowel marks sit to the left |
| Lao, Khmer, Myanmar                     | Lao, Khmer, Burmese              |                  | Southeast Asian branch; Khmer [stacks](stacking-script.md) subscript consonants                                                                                       |
| [Tibetan](tibetan-script.md)            | Tibetan, Dzongkha                | བོད་ཡིག          | [Stacks](stacking-script.md) consonants vertically; a [tsheg](tsheg.md) marks syllables                                                                               |

### In practice

* **Cover the specific member, not "Brahmic" in general:** confirm the [font](../../terms/font.md) ships the glyphs AND the shaping rules for the exact script you need, not just a related one. The [Noto](../../terms/noto-fonts.md) project covers the family with free, open-licensed families per script, and reaches scripts where commercial fonts are scarce. See [font coverage](../../terms/font-coverage.md).
* **Reuse the infrastructure, but re-test each member:** if you already support one Brahmic script, you likely have the [complex text layout](../../terms/complex-text-layout.md) pieces in place, but test the new member with a real word, because conjuncts, reordering, and mark placement differ from script to script.
* **Verify per script, not by family:** the shared structure is a starting point, not a guarantee; confirm each member's rules against its own page and a fluent reader rather than generalizing from Devanagari.
* **If a rule is not documented, you may be the source:** for an under-resourced member the conventions may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Abugida](abugida.md) · [Baseline](../../design-terms/typography/baseline.md) · [Bengali-Assamese script](bengali-assamese.md) · [CLDR](../../terms/cldr.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Conjunct](conjunct.md) · [Devanagari script](devanagari.md) · [Font](../../terms/font.md) · [Font coverage](../../terms/font-coverage.md) · [Glyph](../../terms/glyph.md) · [Hanging baseline](hanging-baseline.md) · [Language](../linguistics/language.md) · [Locale](../../terms/locale.md) · [Mark](mark.md) · [Matra](matra.md) · [Noto fonts](../../terms/noto-fonts.md) · [OpenType](../../terms/opentype.md) · [Orthography](orthography.md) · [Reordering](../../programming-terms/text-for-digital-products-and-the-web/reordering.md) · [Script](script.md) · [Segmentation](../../programming-terms/text-for-digital-products-and-the-web/segmentation.md) · [Shirorekha](shirorekha.md) · [Stacking script](stacking-script.md) · [Syloti Nagri script](syloti-nagri.md) · [Symbol](symbol.md) · [Tamil](tamil-script.md) · [Text direction](text-direction.md) · [Text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Thai script](thai-script.md) · [Tibetan](tibetan-script.md) · [Tsheg](tsheg.md) · [Unicode](../../terms/unicode.md) · [Virama](virama.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Design tools: [Noto (Google Fonts)](https://fonts.google.com/noto)
* Foundations: [The Unicode Standard, Chapter 12: South Asia-I](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)

### Sources

1. Most of the scripts of South Asia are derived from the ancient Brahmi script - The Unicode Standard, Version 17.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)
2. They are all abugidas in which most symbols stand for a consonant plus an inherent vowel - The Unicode Standard, Version 17.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)
3. Implementations should not assume that they work just as Devanagari does - The Unicode Standard, Version 17.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)
4. Absence of the inherent vowel is frequently marked with a special sign, denoted by the Sanskrit word virama - The Unicode Standard, Version 17.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)
5. A consonant cluster is depicted with a conjunct glyph if such a glyph is available in the current font - The Unicode Standard, Version 17.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)
6. With minor historical exceptions, they are written from left to right - The Unicode Standard, Version 17.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)
