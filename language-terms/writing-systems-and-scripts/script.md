---
term: Script
slug: script
aliases: []
level: foundational
depth: deep
summary: >-
  A script is the set of visual symbols, marks, and rules used to write one or
  more languages.
related:
  - alphabet
  - abugida
  - abjad
  - syllabary
  - logographic
  - featural-alphabet
  - brahmic-scripts
  - font-coverage
  - writing-system
  - script-typeface
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: 'Unicode Glossary: Script'
    url: https://www.unicode.org/glossary/#script
    type: authority
  - title: 'Material Design 3: Bidirectionality (RTL)'
    url: https://m3.material.io/foundations/layout/bidirectionality-rtl
    type: resource
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Script

{% hint style="info" %}
This is the writing-systems sense of "script." For the type-design classification, see [Script (typeface)](../../terms/script-typeface.md); the computing sense (a program) is out of scope in this glossary. A script applied to one language with its spelling and punctuation rules is a [writing system](writing-system.md).
{% endhint %}

## Definition

A script is the set of visual [symbols](symbol.md), [marks](mark.md), and [rules](script-rules.md) used to write one or more languages.

When a community sets rules on how a script can be used to write their specific language it becomes an [orthography](orthography.md).

The combination of script and orthography is also known as the [writing system](writing-system.md) of a language.

Scripts are classified by what each symbol represents: [alphabets](alphabet.md), [abjads](abjad.md), [abugidas](abugida.md) (also called [alphasyllabaries](alphasyllabary.md)), [syllabaries](syllabary.md), [logographic](logographic.md) (more precisely, [logosyllabary](logosyllabary.md)), [ideographic](ideographic.md), [featural](featural-alphabet.md), and [pictographic](pictographic.md) systems. They are often grouped into families like [Brahmic scripts](../../terms/brahmic-scripts.md) and [CJK](../../terms/cjk.md) to help us understand the common properties across related scripts.

The same greeting in four scripts:

| Script               | Looks like | Direction                 | What makes it different         |
| -------------------- | :--------: | ------------------------- | ------------------------------- |
| Latin (alphabet)     |    Hello   | Left to right             | Mostly one shape per letter     |
| Arabic (abjad)       |    مرحبا   | Right to left             | Letters join into cursive forms |
| Devanagari (abugida) |   नमस्ते   | Left to right             | Marks reorder and stack         |
| Han (logographic)    |     你好     | Left to right or vertical | Thousands of characters         |

### Why it matters in design systems

The goal is to zoom out and realize the script is a part of the larger writing system you need to consider when working with text within a design system. This is especially important when you need to support multiple languages.

Script, language, and writing system are not the same thing. Requirements for a design system to support multiple languages are often thought of as language = script, for example, "We have already purchased this font for the website for English which is a Latin script, so adding French language support should be fast and easy because they use the same alphabet!"

While it's true that the script will drive the font design decisions for what typefaces you can use in a project, implementing a language in a design system by only thinking about its script is a recipe for poor user experience.

If the script defines the [typeface](../../terms/typeface.md) choices, the script rules will help you decide the [text direction](text-direction.md) it runs in, and the [shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) and input it requires which influence layout behaviour of components and patterns within your system.

Many of the other typography and font styling decisions are influenced by the language-specific application of the script within the writing system, so looking at the orthography is just as important.

You may discover that a language has more than one writing system, and instead of assuming by location, your site may need to provide a setting to enable a user to choose between different scripts!

#### Examples

English, French, Vietnamese, and Turkish are all written with the same script (Latin)<sup>1</sup> but are different languages. While you could use a typeface that has font coverage for all four, looking at each language's writing system would tell you that the quotation marks used for English are different from French.<sup>2</sup>\
\
Serbian can be written in both Cyrillic and Latin scripts.<sup>3</sup> They both share a script rule of left to right text direction, meaning the layout of the design system does not have to change when a user changes between the two script options.

Punjabi is one language written in two scripts: Gurmukhi in India, which runs left to right, and Shahmukhi, an Arabic-based script used in Pakistan, which runs right to left.<sup>4</sup> This would require a layout change based on which script was selected. While you could infer which script to load based on the location of the person using a website, providing a setting to choose between the two would be an ideal user experience.

### Common mistake

A product team decides to support a new language for their website, adds the content translations, picks a font with coverage for that language, and ships. But this approach is problematic, even if the new language uses the same script.

Languages that share a script can still have different orthography rules. French and English both use the Latin script, but French uses different quotation mark characters. These are not translation problems. They are orthography requirements, and a design system that does not account for them will produce incorrect text within their interface even when the font and the translation are both correct.

When the new language uses a different script, the scope of work is larger. The script drives decisions that sit below the translation layer and can even impact more than typography, things like component layout, icon orientation, input behaviour, focus order, etc. These are architectural decisions. Discovering them after components are built and strings are translated is significantly more expensive than planning for them at the start.

### In practice

* **Do not assume Latin defaults:** spacing, capitalization, line breaking, and input all vary by script. What looks correct in English is not evidence the script is rendering correctly.
* **Check the script before committing to a font or layout:** which script a language uses is not always obvious, and some languages use more than one. Verify the script before selecting typefaces or making layout decisions. See [script rules](script-rules.md) for the properties each script defines.
* **Treat script selection as an architectural decision, not a typography one:** text direction, shaping requirements, and UI mirroring all follow from the script. These decisions affect components and layout, not just fonts. They are significantly cheaper to plan for at the start than to retrofit later.

***

### Related terms and mentions

[Abjad](abjad.md) · [Abugida](abugida.md) · [Alphabet](alphabet.md) · [Alphasyllabary](alphasyllabary.md) · [Arabic script](arabic-script.md) · [Bidirectional text](bidirectional-text.md) · [Brahmic scripts](../../terms/brahmic-scripts.md) · [CJK](../../terms/cjk.md) · [Conjunct](conjunct.md) · [Cyrillic](cyrillic.md) · [Devanagari](../../terms/devanagari.md) · [Featural script](featural-alphabet.md) · [Font](../../terms/font.md) · [Font coverage](../../terms/font-coverage.md) · [Glyph](../../terms/glyph.md) · [Ideographic](ideographic.md) · [Input method editor (IME)](../../terms/input-method-editor.md) · [Keyboard layout](../../terms/keyboard-layout.md) · [Latin script](latin-script.md) · [Line height](../../terms/line-height.md) · [Logographic](logographic.md) · [Logosyllabary](logosyllabary.md) · [Mark](mark.md) · [Orthography](orthography.md) · [Pictographic](pictographic.md) · [Reordering](../../programming-terms/text-for-digital-products-and-the-web/reordering.md) · [Script (typeface)](../../terms/script-typeface.md) · [Script rules](script-rules.md) · [Segmentation](../../programming-terms/text-for-digital-products-and-the-web/segmentation.md) · [Shaping engine](../../terms/shaping-engine.md) · [Stacking script](stacking-script.md) · [Syllabary](syllabary.md) · [Symbol](symbol.md) · [Text direction](text-direction.md) · [Text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](../../terms/typeface.md) · [Typography](../../terms/typography.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Foundations: [Unicode Glossary: Script](https://www.unicode.org/glossary/#script)
* Resource library: [Material Design 3: Bidirectionality (RTL)](https://m3.material.io/foundations/layout/bidirectionality-rtl)

### Sources

1. A script serves multiple languages - Unicode Glossary: Script [https://www.unicode.org/glossary/#script](https://www.unicode.org/glossary/#script)
2. French and English use different quotation marks - W3C: Quote marks [https://www.w3.org/Style/2013/quote-marks](https://www.w3.org/Style/2013/quote-marks)
3. Serbian script names - Unicode CLDR [https://cldr.unicode.org/translation/displaynames/script-names](https://cldr.unicode.org/translation/displaynames/script-names)
4. Punjabi scripts (Gurmukhi and Shahmukhi) - W3C i18n [https://r12a.github.io/scripts/guru/pa.html](https://r12a.github.io/scripts/guru/pa.html)
