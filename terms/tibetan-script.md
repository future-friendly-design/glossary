---
term: Tibetan script
slug: tibetan-script
aliases:
  - tibetan
level: intermediate
depth: core
summary: The Tibetan script is used to write Tibetan, Dzongkha, and other languages of the Himalayas.
related:
  - abugida
  - brahmic-scripts
  - stacking-script
  - tsheg
  - complex-text-layout
status: voice-passed
version_added: 0.1
updated: 2026-07-06
contributors:
  - sam-gordashko
further_reading:
  - title: Tibetan Text Layout Requirements (W3C)
    url: https://www.w3.org/TR/tibt-lreq/
    type: code
  - title: Noto Sans Tibetan (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Tibetan
    type: design-tool
  - title: 'Unicode Tibetan code chart (U+0F00)'
    url: https://www.unicode.org/charts/PDF/U0F00.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Tibetan script

## Definition

The Tibetan [script](../language-terms/writing-systems-and-scripts/script.md) is used to write Tibetan, Dzongkha, and other languages of the Himalayas.<sup>1</sup> It is a [Brahmic](brahmic-scripts.md) [abugida](../language-terms/writing-systems-and-scripts/abugida.md) of thirty consonants, each carrying an inherent vowel that vowel marks can change.<sup>2</sup>

For example, the Tibetan script's own name for itself, བོད་ཡིག ("Bod yig", "Tibetan writing"), places a dot called a tsheg between its two syllables, བོད and ཡིག, because Tibetan marks syllable boundaries with the tsheg rather than spacing between words.

{% hint style="info" %}
This glossary doesn't cover every Tibetan script property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Tibetan script profile

These properties of the Tibetan script apply to any language that uses it in its [writing system](../language-terms/writing-systems-and-scripts/writing-system.md). Beyond the [script rules](../language-terms/writing-systems-and-scripts/script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

| Property | Tibetan script |
| --- | --- |
| [Autonym](autonym.md) | བོད་ཡིག |
| Languages | Tibetan, Dzongkha, and others |
| Letter case | None (no uppercase and lowercase) |
| [Marks](../language-terms/writing-systems-and-scripts/mark.md) | Four vowel marks placed above and below the consonant, and subjoined consonant forms that build a stack |
| Numerals | Tibetan digits ༠ to ༩ (alongside common ASCII digits) |
| Script type | [Abugida](../language-terms/writing-systems-and-scripts/abugida.md) |
| [Symbols](../language-terms/writing-systems-and-scripts/symbol.md) | Thirty consonants carrying an inherent vowel, plus vowel marks |

### Tibetan script rules and digital use considerations

If your design system supports languages that use the Tibetan script, here are some considerations to keep in mind:

| Rule or feature | How it works in the Tibetan script | Design systems |
| --- | --- | --- |
| [Bidirectional text](../language-terms/writing-systems-and-scripts/bidirectional-text.md) | The script runs left to right, but a line can still become bidirectional when right-to-left content (an Arabic or Hebrew name, for example) is embedded in it | Then the embedded right-to-left run needs the Unicode bidirectional algorithm to reorder correctly; isolate embedded content whose direction you do not control, so it cannot disturb the surrounding text<sup>3</sup> |
| [Complex text layout](complex-text-layout.md) | Yes, shaping required | Handled by the font's [OpenType](opentype.md) rules and applied at render time by the platform's [text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md); see the OpenType and Text shaping rows below for what your font needs to support, and note that line breaking keys on the tsheg rather than spaces (see Tsheg below). Get it wrong and the text renders or wraps incorrectly, not just unstyled |
| [Hanging baseline](../language-terms/writing-systems-and-scripts/hanging-baseline.md) | Tibetan uses a hanging baseline: the symbols align along a top line rather than sitting on a bottom baseline<sup>4</sup> | Align Tibetan to its top line, not a Latin bottom baseline; when Tibetan is mixed with text at other sizes, the letter-heads should align to the same height, so do not baseline-align it to Latin by eye |
| [OpenType](opentype.md) | The font must include the specific [OpenType features](opentype-features.md) for building the vertical consonant stacks from subjoined (and superscript) forms and for positioning the vowel marks above and below the stack, beyond plain glyph substitution | A font can cover the characters and still leave these features out, so confirm it actually ships them, not just the base glyphs<sup>5</sup>. See the Text shaping row below |
| [Stacking](../language-terms/writing-systems-and-scripts/stacking-script.md) | Consonant clusters are built as vertical stacks: subjoined consonants pile below a root consonant, and a superscript consonant can sit above it<sup>6</sup> | A stack can be several symbols tall, so [line height](line-height.md) has to clear the tallest stacks and you cannot break a line mid-stack |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | [Left to right](../language-terms/writing-systems-and-scripts/left-to-right.md)<sup>7</sup> | Left-aligned text as the default |
| [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) | Shaping happens at render time: the platform's [shaping engine](shaping-engine.md) reads the font's OpenType features (see OpenType above) and builds the consonant stacks and positions the vowel marks for correct display | A correct font is necessary but not sufficient: a tool or pipeline that places glyphs without shaping renders the script wrong even with a fully-featured font. Test in the actual design tools your team uses, not just the browser |
| [Tsheg](../language-terms/writing-systems-and-scripts/tsheg.md) | A dot (the tsheg) marks syllable boundaries; Tibetan spaces syllables rather than words, so line breaking keys on the tsheg rather than on whitespace<sup>8</sup> | Break on the tsheg and its syllable units, not on spaces or characters, since search and truncation key on the same units<sup>9</sup> |
| [Unicode](unicode.md) block | Tibetan, [U+0F00 to U+0FFF](https://www.unicode.org/charts/PDF/U0F00.pdf) | No special handling beyond ensuring [font coverage](font-coverage.md) of the block, including the subjoined and superscript stack forms |

### In practice

* **Cover the script before you commit a typeface:** confirm the font ships the Tibetan glyphs AND the [shaping rules](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) that build the stacks and position the marks, not just the base consonants. [Noto Sans Tibetan](https://fonts.google.com/noto/specimen/Noto+Sans+Tibetan) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Give the line room and test real stacks:** because a stack can be several consonants tall, set line height from real stacked text, not from a single row of base symbols, and confirm the stacks build rather than sitting side by side. Tool support for [complex text layout](complex-text-layout.md) varies, so test early.
* **Break on the tsheg, not on spaces or characters:** line breaking, search, and truncation key on the tsheg and its syllable units, so do not split Tibetan on spaces or mid-stack. Pull the conventions from [locale](locale.md) data that Unicode's [CLDR](cldr.md) publishes.
* **If a rule above is not documented, you may be the source:** for an under-resourced language the conventions may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Abugida](../language-terms/writing-systems-and-scripts/abugida.md) · [Autonym](autonym.md) · [Baseline](../design-terms/typography/baseline.md) · [Bidirectional text](../language-terms/writing-systems-and-scripts/bidirectional-text.md) · [Brahmic scripts](brahmic-scripts.md) · [CLDR](cldr.md) · [Complex text layout](complex-text-layout.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [Hanging baseline](../language-terms/writing-systems-and-scripts/hanging-baseline.md) · [Language](../language-terms/linguistics/language.md) · [Left-to-right](../language-terms/writing-systems-and-scripts/left-to-right.md) · [Line height](line-height.md) · [Locale](locale.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Noto fonts](noto-fonts.md) · [OpenType](opentype.md) · [OpenType features](opentype-features.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Segmentation](../programming-terms/text-for-digital-products-and-the-web/segmentation.md) · [Shaping engine](shaping-engine.md) · [Stacking script](../language-terms/writing-systems-and-scripts/stacking-script.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Tsheg](../language-terms/writing-systems-and-scripts/tsheg.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Code & specs: [Tibetan Text Layout Requirements (W3C)](https://www.w3.org/TR/tibt-lreq/)
* Design tools: [Noto Sans Tibetan (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Tibetan)
* Foundations: [Unicode Tibetan code chart (U+0F00)](https://www.unicode.org/charts/PDF/U0F00.pdf)

### Sources

1. The Tibetan script is used for writing Tibetan in several countries and regions throughout the Himalayas, and is also used in Bhutan to write Dzongkha - The Unicode Standard, Version 17.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/)
2. The Tibetan script has 30 consonants, each represented by a discrete written character, and vowel marks are applied to indicate vowels other than the inherent one - The Unicode Standard, Version 17.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/)
3. This annex describes specifications for the positioning of characters in text containing characters flowing from right to left, such as Arabic or Hebrew - Unicode Standard Annex #9: Unicode Bidirectional Algorithm [https://www.unicode.org/reports/tr9/](https://www.unicode.org/reports/tr9/)
4. Tibetan uses a hanging baseline, which tends to fall between the ascender and x-height of Latin text - Tibetan (r12a script notes) [https://r12a.github.io/scripts/tibt/bo.html](https://r12a.github.io/scripts/tibt/bo.html)
5. Tibetan fonts build consonant stacks with above-base and below-base substitutions (the 'abvs' and 'blws' features) and position the vowel marks with above- and below-base mark positioning ('abvm' and 'blwm'), which the shaping engine applies when the text is rendered - Creating and Supporting OpenType Fonts for Tibetan Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/tibetan](https://learn.microsoft.com/en-us/typography/script-development/tibetan)
6. A base or root consonant can be written singly or have other consonants added above or below it to make a vertically stacked letter - The Unicode Standard, Version 17.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/)
7. Tibetan text runs left to right in horizontal lines - Tibetan Text Layout Requirements (W3C) [https://www.w3.org/TR/tibt-lreq/](https://www.w3.org/TR/tibt-lreq/)
8. The primary line-break character in Tibetan is the interword tsheg (U+0F0B), which separates syllables; whitespace can appear in Tibetan text, but lines break after the tsheg rather than at spaces - The Unicode Standard, Version 17.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-13/)
9. Tibetan words comprise units called tsheg-bar, basically phonological syllables, separated by the tsheg, and it is these units that line breaking operates on - Tibetan Text Layout Requirements (W3C) [https://www.w3.org/TR/tibt-lreq/](https://www.w3.org/TR/tibt-lreq/)
