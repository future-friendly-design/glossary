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
  Joining is the behaviour in some scripts where symbols connect and change
  shape based on their position in a word.
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

Joining is a script rules that defines the the behaviour where the symbols of a script may connect and change shape based on their position in a word.&#x20;

For example, the letters of an Arabic word are joined to each other, like this `EXAMPLE HERE`&#x20;

Like all script rules, joining applies to any language using the script in its writing system.&#x20;

While this glossary doesn't cover every script, here are some to be aware of that have a joining script rule. You can select a linked term to navigate to its glossary page.&#x20;

| Script                                                     | Languages                            | How joining works here                                                              | Example |
| ---------------------------------------------------------- | ------------------------------------ | ----------------------------------------------------------------------------------- | ------- |
| [Arabic](../../terms/arabic-script.md)                     | Arabic, Persian, Urdu                | Letters connect cursively, each taking an initial, medial, final, or isolated form. |         |
| [Mongolian (traditional)](../../terms/mongolian-script.md) | Mongolian                            | Cursive and joining like Arabic, but written vertically, top to bottom.             |         |
| Syriac                                                     | Syriac (a form of Aramaic)           | Cursive joining with the same four positional forms.                                |         |
| N'Ko                                                       | Manding languages (Bambara, Maninka) | Cursive joining with positional forms; a 20th-century script for these languages.   |         |
| Adlam                                                      | Fula (Fulani)                        | Cursive joining with positional forms; a modern script created for Fula.            |         |

### Why it matters in design systems

In a script with a joining script rule, each symbol is not one fixed shape.&#x20;

The shape of a symbol changes depending on **where it sits in the word** and **which neighbourbouring symbols it connects to**. Each symbol can appear as these shapes:

* **isolated** - When the symbols stands **alone**, it is not joined to anything.
* **initial** - When the symbol is positioned at the **start** of a joined run, connecting to the symbol after it.
* **medial** - When the symbol is positioned in the **middle** of a joined run, connecting to a symbol on both sides.&#x20;
* **final** - When the symbol is positioned at the **end**, of a joined run, connecting to the symbol before it.

As you can imagine, supporting a language whose writing system has a joining script rule influences multiple parts of the design system across typography, design, and development.&#x20;

In typography the typeface must have glyps for all positional forms of the scripts symbols. In design, font styles need to ensure properties like tracking and letter spacing have values that enable characters to join.&#x20;

Design tooling needs have the features that enable joining behaviour of characters, otherwise the tool will display the chatacters but not shape them for joining, which leaves the script symbols as separate shapes a reader can not follow.&#x20;

In development, the backend systems need to support text shaping so the right form of the symbol is displayed when the text string is translated into a language with a joining rule.&#x20;

* Text shaping is the step that turns stored characters into properly positioned glyphs.&#x20;
* OpenType is a widely supported standard for formatting font data for digital typography with features for supporting script rules like joining automatically. OpenType selects the positional forms of glyphs with the `isol`, `init`, `medi`, and `fina` features.&#x20;

A quick thing to keep in mind: joining is just one of a script's rules. A script usually has several, and they all apply to every language that uses the script. So check the other [script rules](script-rules.md) too, not only this page. After that, look at the [orthography](orthography.md) for each language you support. Orthography is the language-specific layer: how that one language uses the script, like its spelling and punctuation.

### Common mistake

Treating joining like a [ligature](../../terms/ligature.md). A ligature fuses two specific symbols into one glyph for one fixed combination, the way an `f` and an `i` can merge into a single `fi` shape. Joining is different: it is the systematic reshaping of letters as they connect along a whole word, not a one-off fusion. Mixing the two up sends you looking for the wrong fix, a ligature setting, when the text actually needs shaping.

### In practice

* **Test the tool with a real word, not a glyph table:** type a connected word and confirm the letters join and pick up their positional forms, not just that the characters appear. Tool support varies, so test early, not at handoff.
* **Confirm positional-form coverage before you commit a typeface:** the font has to ship the joining forms and the features that select them, not just the base letters. See [font coverage](../../terms/font-coverage.md).

***

### Related terms and mentions

[Arabic script](../../terms/arabic-script.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Font](../../terms/font.md) · [Font coverage](../../terms/font-coverage.md) · [Glyph](../../terms/glyph.md) · [Ligature](../../terms/ligature.md) · [Script rules](script-rules.md) · [Text shaping](../../terms/text-shaping.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [ArabicShaping.txt (Unicode Character Database)](https://www.unicode.org/Public/UCD/latest/ucd/ArabicShaping.txt)
* Foundations: [Internationalization (W3C)](https://www.w3.org/International/)

### Sources

1. The shaping engine determines each letter's contextual form (isolated, initial, medial, final) from the characters before and after it, and OpenType selects them with the `isol`, `init`, `medi`, and `fina` features - Developing OpenType Fonts for Arabic Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/arabic](https://learn.microsoft.com/en-us/typography/script-development/arabic)
