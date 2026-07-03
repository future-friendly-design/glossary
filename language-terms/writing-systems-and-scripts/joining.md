---
term: Joining
slug: joining
aliases:
  - cursive joining
  - joining forms
  - contextual forms
level: intermediate
depth: deep
summary: >-
  Joining is a script rule that defines the behaviour where the symbols of a
  script may connect and change shape based on their position in a word.
related:
  - arabic-script
  - text-shaping
  - complex-text-layout
  - ligature
  - script-rules
status: voice-passed
version_added: 0.1
updated: 2026-06-22T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: ArabicShaping.txt (Unicode Character Database)
    url: https://www.unicode.org/Public/UCD/latest/ucd/ArabicShaping.txt
    type: code
  - title: Internationalization (W3C)
    url: https://www.w3.org/International/
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
  - shaping-layout
---

# Joining

## Definition

Joining is a script rule that defines the behaviour where the symbols of a script may connect and change shape based on their position in a word.

For example, the Arabic letters kāf ك, tāʾ ت and bāʾ ب each have their own standalone shape, but in the word كتب they connect, flowing together instead of standing apart.

Like all script rules, joining applies to any [language](../linguistics/language.md) using the [script](script.md) in its [writing system](writing-system.md).

While this glossary doesn't cover every script, here are some to be aware of that have a joining script rule. You can select a linked term to navigate to its glossary page.

| Script                                                     | Languages                            | How joining works here                                                              | Example |
| ---------------------------------------------------------- | ------------------------------------ | ----------------------------------------------------------------------------------- | ------- |
| [Arabic](../../terms/arabic-script.md)                     | Arabic, Persian, Urdu                | Letters connect cursively, each taking an initial, medial, final, or isolated form. | كتب     |
| [Mongolian (traditional)](../../terms/mongolian-script.md) | Mongolian                            | Cursive and joining like Arabic, but written vertically, top to bottom.             |         |
| Syriac                                                     | Syriac (a form of Aramaic)           | Cursive joining with the same four positional forms.                                |         |
| N'Ko                                                       | Manding languages (Bambara, Maninka) | Cursive joining with positional forms; a 20th-century script for these languages.   |         |
| Adlam                                                      | Fula (Fulani)                        | Cursive joining with positional forms; a modern script created for Fula.            |         |

### Why it matters in design systems

In a script with a joining script rule, each [symbol](symbol.md) is not one fixed shape.

The shape of a symbol changes depending on **where it sits in the word** and **which neighbouring symbols it connects to**. Depending on the symbol, it can take up to four shapes:

* **isolated** - When the symbol stands **alone**, not joined to anything.
* **initial** - When the symbol is at the **start** of a word, connecting to the symbol after it.
* **medial** - When the symbol is in the **middle** of a word, connecting to a symbol on both sides.
* **final** - When the symbol is at the **end** of a word, connecting to the symbol before it.

Not every symbol takes all four. Some join on one side only, so they appear just in the isolated and final shapes.

As you can imagine, supporting a language whose writing system has a joining script rule influences multiple parts of the design system across typography, design, and development.

In typography, the [typeface](../../terms/typeface.md) must include [glyphs](../../terms/glyph.md) for all positional forms of the script's symbols. In design, [tracking](../../design-terms/typography/tracking.md) and [letter-spacing](../../terms/letter-spacing.md) must stay at zero for these scripts, because adding space between symbols breaks the joins.<sup>1</sup>

Design tooling needs to support shaping; otherwise the tool will display the [characters](../../terms/character.md) but not join them, leaving the script's symbols as separate shapes a reader cannot follow.

In development, the text-rendering layer (the browser, OS, or app's text engine) needs to support shaping, so the right form of each symbol appears when text is displayed in a language written in a joining script.

* [Text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) is the step that turns stored characters into properly positioned glyphs.
* [OpenType](../../terms/opentype.md) is a widely supported standard for formatting [font](../../terms/font.md) data for digital typography, with features for supporting script rules like joining automatically. OpenType selects the positional forms of glyphs with the `isol`, `init`, `medi`, and `fina` features.<sup>2</sup>

A quick thing to keep in mind: joining is just one of a script's rules. A script usually has several, and they all apply to every language that uses the script. So check the other [script rules](script-rules.md) too, not only this page. After that, look at the [orthography](orthography.md) for each language you support. Orthography is the language-specific layer: how that one language uses the script, like its spelling and punctuation.

### Common mistake

Treating joining as an optional styling choice. A [ligature](../../terms/ligature.md), like the fi pair you see in English text, is a typographic refinement you can switch on or off.<sup>3</sup> Joining is not like that: it is required shaping. Skip it, with a tool or font that cannot shape, and the text does not just look plainer, it becomes unreadable. So when joined text renders broken, what it needs is shaping, not a font's ligature setting.

### In practice

* **Test the tool with a real word, not a glyph table:** type a connected word and confirm the symbols join and pick up their positional forms, not just that the characters appear. Tool support varies, so test early, not at handoff.
* **Confirm positional-form coverage before you commit a typeface:** the font has to ship the joining forms and the features that select them, not just the base symbols. See [font coverage](../../terms/font-coverage.md).

***

### Related terms and mentions

[Arabic script](../../terms/arabic-script.md) · [Character](../../terms/character.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Font](../../terms/font.md) · [Font coverage](../../terms/font-coverage.md) · [Glyph](../../terms/glyph.md) · [Language](../linguistics/language.md) · [Letter spacing](../../terms/letter-spacing.md) · [Ligature](../../terms/ligature.md) · [OpenType](../../terms/opentype.md) · [Orthography](orthography.md) · [Script](script.md) · [Script rules](script-rules.md) · [Symbol](symbol.md) · [Text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Tracking](../../design-terms/typography/tracking.md) · [Typeface](../../terms/typeface.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [ArabicShaping.txt (Unicode Character Database)](https://www.unicode.org/Public/UCD/latest/ucd/ArabicShaping.txt)
* Foundations: [Internationalization (W3C)](https://www.w3.org/International/)

### Sources

1. Some written languages should have no letter spacing applied; languages that use the Arabic script "expect connected letters to remain visually connected", and applying letter spacing "may lead to the text looking broken" - letter-spacing (MDN) [https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing)
2. The shaping engine determines each letter's contextual form (isolated, initial, medial, final) from the characters before and after it, and OpenType selects them with the `isol`, `init`, `medi`, and `fina` features - Developing OpenType Fonts for Arabic Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/arabic](https://learn.microsoft.com/en-us/typography/script-development/arabic)
3. Common and discretionary ligatures, such as fi, are optional and can be switched on or off through the CSS `font-variant-ligatures` property and the OpenType `liga` and `dlig` features - font-variant-ligatures (MDN) [https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-ligatures](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-ligatures)
