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

### Why it matters in design systems

In a joining script, a letter is not one fixed shape. It takes a different form depending on where it sits and what it connects to, usually one of four: initial, medial, final, or isolated.<sup>1</sup>

To a [font](../../terms/font.md), that means the right form has to be chosen during [shaping](../../terms/text-shaping.md), the step that turns stored characters into the positioned [glyphs](../../terms/glyph.md) you see. The font must contain those positional forms, and OpenType selects them with the `isol`, `init`, `medi`, and `fina` features.<sup>1</sup>

To a design tool, joining is the single most important behaviour to confirm when you prototype an [Arabic](../../terms/arabic-script.md) interface, because many tools display the characters but never shape them, which leaves the letters as separate, disconnected shapes a reader cannot follow.

So a font that contains Arabic characters is necessary but not sufficient: without the positional forms and the shaping logic to pick them, the text still renders broken. Joining is a property of the script, so it applies across every language written in that script, such as Arabic, Persian, and Urdu.

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
