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
  - title: The Unicode Standard (latest version)
    url: https://www.unicode.org/versions/latest/
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

Joining is the behaviour in some scripts where symbols connect and change shape based on their position in a word.

For example, the letters of an Arabic word link into one continuous cursive run rather than sitting apart like printed Latin letters.

While this glossary doesn't cover every script, here are the scripts that use joining. The linked ones have a page in the glossary.<sup>2</sup>

| Script | Languages | How joining works here |
| --- | --- | --- |
| [Arabic](../../terms/arabic-script.md) | Arabic, Persian, Urdu | Letters connect cursively, each taking an initial, medial, final, or isolated form. |
| [Mongolian (traditional)](../../terms/mongolian-script.md) | Mongolian | Cursive and joining like Arabic, but written vertically, top to bottom. |
| Syriac | Syriac (a form of Aramaic) | Cursive joining with the same four positional forms. |
| N'Ko | Manding languages (Bambara, Maninka) | Cursive joining with positional forms; a 20th-century script for these languages. |
| Adlam | Fula (Fulani) | Cursive joining with positional forms; a modern script created for Fula. |

### Why it matters in design systems

In a joining script, a letter is not one fixed shape. It takes a different form depending on where it sits and what it connects to, usually one of four: initial, medial, final, or isolated.<sup>1</sup>

To a [font](../../terms/font.md), that means the right form has to be chosen during [shaping](../../terms/text-shaping.md), the step that turns stored characters into the positioned [glyphs](../../terms/glyph.md) you see. The font must contain those positional forms, and OpenType selects them with the `isol`, `init`, `medi`, and `fina` features.<sup>1</sup>

To a design tool, joining is the single most important behaviour to confirm when you prototype an [Arabic](../../terms/arabic-script.md) interface, because many tools display the characters but never shape them, which leaves the letters as separate, disconnected shapes a reader cannot follow.

So a font that contains Arabic characters is necessary but not sufficient: without the positional forms and the shaping logic to pick them, the text still renders broken. Joining is a property of the script, so it applies across every language written in that script, such as Arabic, Persian, and Urdu.

A quick thing to keep in mind: joining is just one of a script's rules. A script usually has several, and they all apply to every language that uses the script. So check the other [script rules](script-rules.md) too, not only this page. After that, look at the [orthography](orthography.md) for each language you support. Orthography is the language-specific layer: how that one language uses the script, like its spelling and punctuation.

### Example

Write a short Arabic word whose letters all connect. Each letter takes its initial, medial, or final form so the word renders as one continuous cursive run rather than three separate shapes sitting side by side. Change one letter's neighbour and the connected form changes with it.

### Common mistake

Assuming that a font containing Arabic characters will display Arabic correctly. Without shaping, those characters appear in their isolated forms, unconnected, which reads as broken. Joining is also not the same as a [ligature](../../terms/ligature.md). A ligature fuses two specific symbols into one glyph for one combination. Joining is the systematic reshaping of letters as they connect along a whole word.

### In practice

* **Test the tool with a real word, not a glyph table:** check that a design tool shapes the text, not just that it can show the characters. Type a real word and confirm the letters connect and pick up their positional forms. Support varies between tools, so test it early rather than discovering it at handoff.
* **Verify the font covers the script, not just the letters:** the typeface has to include the positional forms and the OpenType features that select them. A font missing those will leave joining text disconnected even though every base letter is present. See [font coverage](../../terms/font-coverage.md).

***

### Related terms and mentions

[Arabic script](../../terms/arabic-script.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Font](../../terms/font.md) · [Font coverage](../../terms/font-coverage.md) · [Glyph](../../terms/glyph.md) · [Ligature](../../terms/ligature.md) · [Script rules](script-rules.md) · [Text shaping](../../terms/text-shaping.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [The Unicode Standard (latest version)](https://www.unicode.org/versions/latest/)
* Foundations: [Internationalization (W3C)](https://www.w3.org/International/)

### Sources

1. The shaping engine determines each letter's contextual form (isolated, initial, medial, final) from the characters before and after it, and OpenType selects them with the `isol`, `init`, `medi`, and `fina` features - Developing OpenType Fonts for Arabic Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/arabic](https://learn.microsoft.com/en-us/typography/script-development/arabic)
2. Unicode defines the Joining_Type property for cursive scripts whose letters join and take positional shapes (isolated, initial, medial, final); the scripts it covers include Arabic, Syriac, N'Ko, Mandaic, Mongolian, Adlam, and Hanifi Rohingya - ArabicShaping.txt, Unicode Character Database [https://www.unicode.org/Public/UCD/latest/ucd/ArabicShaping.txt](https://www.unicode.org/Public/UCD/latest/ucd/ArabicShaping.txt)
