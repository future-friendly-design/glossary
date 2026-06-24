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
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Script

{% hint style="info" %}
This is the writing-systems sense of "script." For the type-design classification, see [Script (typeface)](../../terms/script-typeface.md); the computing sense (a program) is out of scope in this glossary. A script applied to one language with its spelling and punctuation rules is a [writing system](writing-system.md).
{% endhint %}

## Definition

A script is the set of visual [symbols](symbol.md), [marks](mark.md), and [rules](script-rules.md) used to write one or more languages.&#x20;

When a community sets rules on how a script can be used to write their specific language it becomes an [orthography](orthography.md).&#x20;

The combination of script and orthography is also known as the [writing system](writing-system.md) of a language.&#x20;

Scripts are classified by what each symbol represents: [alphabets](../../terms/alphabet.md), [abjads](../../terms/abjad.md), [abugidas](../../terms/abugida.md), [alphasyllabaries](../../terms/alphasyllabary.md), [syllabaries](../../terms/syllabary.md), [logographic](../../terms/logographic.md), [logosyllabary](../../terms/logosyllabary.md), [ideographic](../../terms/ideographic.md), [featural](../../terms/featural-alphabet.md), and [pictographic](../../terms/pictographic.md) systems. They are often grouped into families like [Brahmic scripts](../../terms/brahmic-scripts.md) and [CJK](../../terms/cjk.md) to help us understand the common properties across related scripts.&#x20;

### Why it matters in design systems

The goal is to zoom out and realize the script is a part of the larger writing system you need to consider when working with text within a design system. This is especially important when you need to support multiple languages.&#x20;

Script, language, and writing system are not the same thing. Requirements for a design system to support multiple languages are often thought of as language = script, for example, "We have already purchased this font for the website for english which is a latin script, so adding french language support should be fast and easy because they use the same alphabet!"&#x20;

While its true that the script will drive the font design decisions for what typefaces you can use in a project, implementing a language in a design system by only thinking about its script is a recipe for poor user experience.&#x20;

If the script defines the [typeface](../../terms/typeface.md) choices, the script rules will help you decide the [text direction](../../terms/text-direction.md) it runs in, and the [shaping](../../terms/text-shaping.md) and input it requires which influence layout behaviour of components and patterns within your system.&#x20;

Many of the other typography and font styling decisions are influenced by the language-specific application of the script within the writing system, so looking at the orthography is just as important.&#x20;

You may discover that a language has more than one writing system, and instead of assuming by location, your site may need to provide a setting to enable a user to choose between different scripts!



#### Examples

English, French, Vietnamese, and Turkish are all written with the same script (Latin) but are different languages. While you could use a typeface that has font coverage for all three, looking at each languages writing system would tell you that the quotation marks used for english are different than french.  \
\
Serbian can be written in both Cyrillic and Latin scripts.<sup>2</sup> They are Both share a script rule of left to right text direction, meaning the layout of the design system does not have to change when a user changes between the two script options.&#x20;

Punjabi is one language written in two scripts: Gurmukhi in India, which runs left to right, and Shahmukhi, an Arabic-based script used in Pakistan, which runs right to left. This would require a layout change based on which script was selected. While you infer which script to load based on the location of the person using a website, providing a setting to choose between the two would be an ideal user experience.&#x20;



### Common mistake

A product name team decides to support a new language for their website, adds the content translations, picks a font with coverage for that language, and ships. But this approach is problematic, even if the new language uses the same script.

Languages that share a script can still have different orthography rules. French and English both use the Latin script, but French uses different quotation mark characters. These are not translation problems. They are orthography requirements, and a design system that does not account for them will produce incorrect text within their interface even when the font and the translation are both correct.

When the new language uses a different script, the scope of work is larger. The script drives decisions that sit below the translation layer and can even impact more than typography, things like component layout, icon orientation, input behavior, focus order, etc. These are architectural decisions. Discovering them after components are built and strings are translated is significantly more expensive than planning for them at the start.

### In practice

* **Do not assume Latin defaults:** spacing, capitalization, line breaking, and input all vary by script. What looks correct in English is not evidence the script is rendering correctly.
*   **Check the script before committing to a font or layout.**

    Which script a language uses is not always obvious, and some languages use more than one. Verify the script before selecting typefaces or making layout decisions. See script rules for the properties each script defines.
*   **Treat script selection as an architectural decision, not a typography one.**

    Text direction, shaping requirements, and UI mirroring all follow from the script. These decisions affect components and layout, not just fonts. They are significantly cheaper to plan for at the start than to retrofit later.

***

### Related terms and mentions

[Abjad](../../terms/abjad.md) · [Abugida](../../terms/abugida.md) · [Alphabet](../../terms/alphabet.md) · [Alphasyllabary](../../terms/alphasyllabary.md) · [Arabic script](../../terms/arabic-script.md) · [Brahmic scripts](../../terms/brahmic-scripts.md) · [CJK](../../terms/cjk.md) · [Conjunct](../../terms/conjunct.md) · [Cyrillic](../../terms/cyrillic.md) · [Devanagari](../../terms/devanagari.md) · [Featural alphabet](../../terms/featural-alphabet.md) · [Font](../../terms/font.md) · [Font coverage](../../terms/font-coverage.md) · [Glyph](../../terms/glyph.md) · [Ideographic](../../terms/ideographic.md) · [Input method editor (IME)](../../terms/input-method-editor.md) · [Keyboard layout](../../terms/keyboard-layout.md) · [Latin script](../../terms/latin-script.md) · [Line height](../../terms/line-height.md) · [Logographic](../../terms/logographic.md) · [Logosyllabary](../../terms/logosyllabary.md) · [Mark](mark.md) · [Pictographic](../../terms/pictographic.md) · [Reordering](../../terms/reordering.md) · [Script (typeface)](../../terms/script-typeface.md) · [Script rules](script-rules.md) · [Segmentation](../../terms/segmentation.md) · [Shaping engine](../../terms/shaping-engine.md) · [Stacking script](../../terms/stacking-script.md) · [Syllabary](../../terms/syllabary.md) · [Symbol](symbol.md) · [Text direction](../../terms/text-direction.md) · [Text shaping](../../terms/text-shaping.md) · [Typeface](../../terms/typeface.md) · [Typography](../../terms/typography.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Foundations: [Unicode Glossary: Script](https://www.unicode.org/glossary/#script)

### Sources

1. A script serves multiple languages - Unicode Glossary: Script [https://www.unicode.org/glossary/#script](https://www.unicode.org/glossary/#script)
2. Serbian script names - Unicode CLDR [https://cldr.unicode.org/translation/displaynames/script-names](https://cldr.unicode.org/translation/displaynames/script-names)
