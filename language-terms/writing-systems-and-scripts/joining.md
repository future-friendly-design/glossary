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

Joining is a script rule that defines the behaviour where the symbols of a script may connect and change shape based on their position in a word.&#x20;

For example, the Arabic letters kāf ك, tāʾ ت and bāʾ ب each have their own standalone shape, but in the word كتب they connect into one cursive run.&#x20;

Like all script rules, joining applies to any language using the script in its writing system.&#x20;

While this glossary doesn't cover every script, here are some to be aware of that have a joining script rule. You can select a linked term to navigate to its glossary page.&#x20;

| Script                                                     | Languages                            | How joining works here                                                              | Example |
| ---------------------------------------------------------- | ------------------------------------ | ----------------------------------------------------------------------------------- | ------- |
| [Arabic](../../terms/arabic-script.md)                     | Arabic, Persian, Urdu                | Letters connect cursively, each taking an initial, medial, final, or isolated form. | كتب |
| [Mongolian (traditional)](../../terms/mongolian-script.md) | Mongolian                            | Cursive and joining like Arabic, but written vertically, top to bottom.             |         |
| Syriac                                                     | Syriac (a form of Aramaic)           | Cursive joining with the same four positional forms.                                |         |
| N'Ko                                                       | Manding languages (Bambara, Maninka) | Cursive joining with positional forms; a 20th-century script for these languages.   |         |
| Adlam                                                      | Fula (Fulani)                        | Cursive joining with positional forms; a modern script created for Fula.            |         |

### Why it matters in design systems

In a script with a joining script rule, each symbol is not one fixed shape.&#x20;

The shape of a symbol changes depending on **where it sits in the word** and **which neighbouring symbols it connects to**. Depending on the symbol, it can take up to four shapes:

* **isolated** - When the symbol stands **alone**, not joined to anything.
* **initial** - When the symbol is at the **start** of a joined run, connecting to the symbol after it.
* **medial** - When the symbol is in the **middle** of a joined run, connecting to a symbol on both sides.
* **final** - When the symbol is at the **end** of a joined run, connecting to the symbol before it.

Not every symbol takes all four. Some join on one side only, so they appear just in the isolated and final shapes.

As you can imagine, supporting a language whose writing system has a joining script rule influences multiple parts of the design system across typography, design, and development.&#x20;

In typography, the typeface must include glyphs for all positional forms of the script's symbols. In design, tracking and letter-spacing must stay at zero for these scripts, because adding space between symbols breaks the joins.<sup>1</sup>&#x20;

Design tooling needs to support shaping; otherwise the tool will display the characters but not join them, leaving the script's symbols as separate shapes a reader cannot follow.&#x20;

In development, the text-rendering layer (the browser, OS, or app's text engine) needs to support shaping, so the right form of each symbol appears when text is displayed in a language written in a joining script.&#x20;

* Text shaping is the step that turns stored characters into properly positioned glyphs.&#x20;
* [OpenType](../../terms/opentype.md) is a widely supported standard for formatting font data for digital typography, with features for supporting script rules like joining automatically. OpenType selects the positional forms of glyphs with the `isol`, `init`, `medi`, and `fina` features.<sup>2</sup>&#x20;

A quick thing to keep in mind: joining is just one of a script's rules. A script usually has several, and they all apply to every language that uses the script. So check the other [script rules](script-rules.md) too, not only this page. After that, look at the [orthography](orthography.md) for each language you support. Orthography is the language-specific layer: how that one language uses the script, like its spelling and punctuation.

### Common mistake

Treating joining like a [ligature](../../terms/ligature.md). A ligature fuses two specific symbols into one glyph for one fixed combination, the way an `f` and an `i` can merge into a single `fi` shape. Joining is different: it is the systematic reshaping of symbols as they connect along a whole word, not a one-off fusion. Mixing the two up sends you looking for the wrong fix, a ligature setting, when the text actually needs shaping.

### In practice

* **Test the tool with a real word, not a glyph table:** type a connected word and confirm the symbols join and pick up their positional forms, not just that the characters appear. Tool support varies, so test early, not at handoff.
* **Confirm positional-form coverage before you commit a typeface:** the font has to ship the joining forms and the features that select them, not just the base symbols. See [font coverage](../../terms/font-coverage.md).

***

### Related terms and mentions

[Arabic script](../../terms/arabic-script.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Font](../../terms/font.md) · [Font coverage](../../terms/font-coverage.md) · [Glyph](../../terms/glyph.md) · [Ligature](../../terms/ligature.md) · [Script rules](script-rules.md) · [Text shaping](../../terms/text-shaping.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [ArabicShaping.txt (Unicode Character Database)](https://www.unicode.org/Public/UCD/latest/ucd/ArabicShaping.txt)
* Foundations: [Internationalization (W3C)](https://www.w3.org/International/)

### Sources

1. Some written languages should have no letter spacing applied; languages that use the Arabic script "expect connected letters to remain visually connected", and applying letter spacing "may lead to the text looking broken" - letter-spacing (MDN) [https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing)
2. The shaping engine determines each letter's contextual form (isolated, initial, medial, final) from the characters before and after it, and OpenType selects them with the `isol`, `init`, `medi`, and `fina` features - Developing OpenType Fonts for Arabic Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/arabic](https://learn.microsoft.com/en-us/typography/script-development/arabic)
