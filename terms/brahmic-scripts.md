---
term: Brahmic scripts
slug: brahmic-scripts
aliases:
  - Indic scripts
  - Brahmic family
level: intermediate
depth: core
summary: Brahmic scripts are a family of related scripts used across South and Southeast Asia, all descended from the ancient Brahmi script.
related:
  - abugida
  - conjunct
  - matra
  - virama
  - complex-text-layout
status: voice-passed
version_added: 0.1
updated: 2026-07-07
contributors:
  - sam-gordashko
further_reading:
  - title: 'The Unicode Standard, Chapter 12: South Asia-I'
    url: https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/
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

Brahmic scripts are a family of related scripts used across South and Southeast Asia, all descended from the ancient Brahmi script.<sup>1</sup> They are almost all [abugidas](../language-terms/writing-systems-and-scripts/abugida.md): most symbols stand for a consonant plus an inherent vowel, generally the short /a/, which dependent vowels ([matras](../language-terms/writing-systems-and-scripts/matra.md)) can change.<sup>2</sup>

Brahmic is a family, not a single script. This page describes what the members share; how any one member works, its symbols, conjuncts, and rules, is that script's own page. The members share a structure but differ enough that you design for each one, not for "Brahmic" as a whole: Unicode itself warns that implementations should not assume the South Indian scripts work just as Devanagari does.<sup>3</sup>

### What unites the members

These are the traits the family holds in common. Individual members vary, so treat this as the shared starting point, not a specification for any one script.

| Shared feature | Across the Brahmic family |
| --- | --- |
| Origin | all descend from the ancient Brahmi script |
| Script type | almost all are [abugidas](../language-terms/writing-systems-and-scripts/abugida.md): each consonant carries an inherent vowel, generally /a/ |
| Vowel marks | dependent vowels ([matras](../language-terms/writing-systems-and-scripts/matra.md)) attach to a consonant to change its inherent vowel |
| [Virama](../language-terms/writing-systems-and-scripts/virama.md) | a virama (halant) suppresses the inherent vowel |
| [Conjuncts](../language-terms/writing-systems-and-scripts/conjunct.md) | consonant clusters can combine into conjunct forms |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | with minor historical exceptions, left to right |
| Rendering | [complex text layout](complex-text-layout.md): real shaping, mark positioning, and sometimes reordering, not simple glyph placement |

### Members

The Brahmic family is large and this glossary doesn't cover every member; here are some to be aware of, spanning the South Asian and Southeast Asian branches, with a page linked where one exists. The Example column shows each linked script's own name, and the last column notes how each member departs from the shared pattern (verified per script, not assumed from the family). Select a linked term to navigate to its glossary page.

| Script | Languages | Example | Distinctive in the family |
| --- | --- | --- | --- |
| [Devanagari](devanagari.md) | Hindi, Marathi, Sanskrit, Nepali | देवनागरी | hangs its symbols from a continuous headline stroke ([shirorekha](../language-terms/writing-systems-and-scripts/shirorekha.md)) |
| [Bengali-Assamese](bengali-assamese.md) | Bengali, Assamese | বাংলা লিপি | also written along a headline; its own conjunct forms |
| [Tamil](tamil-script.md) | Tamil | தமிழ் அரிச்சுவடி | sits on a [baseline](../design-terms/typography/baseline.md); very few conjuncts |
| Telugu | Telugu | | rounded southern forms; vowel marks mostly above the consonant |
| Kannada | Kannada | | rounded southern forms, closely related to Telugu |
| Malayalam | Malayalam | | rounded southern forms; historically rich in conjuncts |
| Gujarati | Gujarati | | like Devanagari, but without the headline stroke |
| Gurmukhi | Punjabi | | written along a headline |
| Odia | Odia | | rounded, curved tops |
| Sinhala | Sinhala | | rounded forms |
| [Syloti Nagri](syloti-nagri.md) | Sylheti | ꠍꠤꠟꠐꠤ ꠘꠣꠉꠞꠤ | small consonant set; a hasanta forms conjuncts |
| [Thai](thai-script.md) | Thai | อักษรไทย | no spaces between words, needing [word segmentation](../programming-terms/text-for-digital-products-and-the-web/segmentation.md); some vowel marks sit to the left |
| Lao, Khmer, Myanmar | Lao, Khmer, Burmese | | Southeast Asian branch; Khmer stacks subscript consonants |
| [Tibetan](tibetan-script.md) | Tibetan, Dzongkha | བོད་ཡིག | [stacks](../language-terms/writing-systems-and-scripts/stacking-script.md) consonants vertically; a [tsheg](../language-terms/writing-systems-and-scripts/tsheg.md) marks syllables |

### Why it matters in design systems

Treat this entry as a map of the family, not a playbook for any one member: for that, follow the link to the specific script. The value of knowing the family is that it tells you what transfers and what does not.

What transfers is the mental model and the infrastructure. Because the members share the abugida structure, a [virama](../language-terms/writing-systems-and-scripts/virama.md) that suppresses the inherent vowel,<sup>4</sup> [conjunct](../language-terms/writing-systems-and-scripts/conjunct.md) forms for consonant clusters,<sup>5</sup> and a predominantly left-to-right direction,<sup>6</sup> supporting one Brahmic script teaches you much of what the others need: real [text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md), [OpenType](opentype.md) rules, mark positioning, and sometimes [reordering](../programming-terms/text-for-digital-products-and-the-web/reordering.md), rather than simple glyph placement. If your stack handles one member well, it is closer to handling the rest.

What does not transfer is the detail, and this is the trap: the members diverge enough that "Brahmic support" is not one deliverable. As the Members table shows, Devanagari's headline and matra reordering, Tamil's baseline and sparse conjuncts, Thai's spaceless words, and Tibetan's vertical stacking are all different problems. So verify each member against its own rules and a real word, not by assuming it behaves like a sibling, and bound your choices by the member's [orthography](../language-terms/writing-systems-and-scripts/orthography.md) as well as the script. Where the glossary is silent, a rule left undocumented is an open question, not a settled "no".

### In practice

* **Cover the specific member, not "Brahmic" in general:** confirm the [font](font.md) ships the glyphs AND the shaping rules for the exact script you need, not just a related one. The [Noto](noto-fonts.md) project covers the family with free, open-licensed families per script, and reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Reuse the infrastructure, but re-test each member:** if you already support one Brahmic script, you likely have the [complex text layout](complex-text-layout.md) pieces in place, but test the new member with a real word, because conjuncts, reordering, and mark placement differ from script to script.
* **Verify per script, not by family:** the shared structure is a starting point, not a guarantee; confirm each member's rules against its own page and a fluent reader rather than generalizing from Devanagari.
* **If a rule is not documented, you may be the source:** for an under-resourced member the conventions may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Abugida](../language-terms/writing-systems-and-scripts/abugida.md) · [Baseline](../design-terms/typography/baseline.md) · [Bengali-Assamese](bengali-assamese.md) · [CLDR](cldr.md) · [Complex text layout](complex-text-layout.md) · [Conjunct](../language-terms/writing-systems-and-scripts/conjunct.md) · [Devanagari](devanagari.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [Language](../language-terms/linguistics/language.md) · [Locale](locale.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Matra](../language-terms/writing-systems-and-scripts/matra.md) · [Noto fonts](noto-fonts.md) · [OpenType](opentype.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Reordering](../programming-terms/text-for-digital-products-and-the-web/reordering.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Segmentation](../programming-terms/text-for-digital-products-and-the-web/segmentation.md) · [Shirorekha](../language-terms/writing-systems-and-scripts/shirorekha.md) · [Stacking script](../language-terms/writing-systems-and-scripts/stacking-script.md) · [Syloti Nagri](syloti-nagri.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Tamil](tamil-script.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Thai script](thai-script.md) · [Tibetan](tibetan-script.md) · [Tsheg](../language-terms/writing-systems-and-scripts/tsheg.md) · [Unicode](unicode.md) · [Virama](../language-terms/writing-systems-and-scripts/virama.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Design tools: [Noto (Google Fonts)](https://fonts.google.com/noto)
* Foundations: [The Unicode Standard, Chapter 12: South Asia-I](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/)

### Sources

1. Most of the scripts of South Asia are derived from the ancient Brahmi script - The Unicode Standard, Version 16.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/)
2. They are all abugidas in which most symbols stand for a consonant plus an inherent vowel - The Unicode Standard, Version 16.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/)
3. Implementations should not assume that they work just as Devanagari does - The Unicode Standard, Version 16.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/)
4. Absence of the inherent vowel is frequently marked with a special sign, denoted by the Sanskrit word virama - The Unicode Standard, Version 16.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/)
5. A consonant cluster is depicted with a conjunct glyph if such a glyph is available in the current font - The Unicode Standard, Version 16.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/)
6. With minor historical exceptions, they are written from left to right - The Unicode Standard, Version 16.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/)
