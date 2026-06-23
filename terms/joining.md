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
  Joining is the behavior in some scripts where signs connect and change shape
  based on their position in a word.
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
  - shaping-layout
---

# Joining

## Definition

Joining is the behavior in some scripts where signs connect and change shape based on their position in a word. TEST

## Why it matters

In a joining script, a letter is not one fixed shape. It takes a different form depending on where it sits and what it connects to, usually one of four: initial, medial, final, or isolated. The correct form is chosen during shaping, the step that turns stored characters into the positioned glyphs you see. Arabic is the clearest case, and joining is the single most important behavior to confirm when you prototype an Arabic-script interface, because a tool that does not join will leave the letters as separate, disconnected shapes that a reader cannot follow. Joining is a property of the script, so it applies across every language written in that script, such as Arabic, Persian, and Urdu.

## Also called

OpenType selects joining forms through the `init`, `medi`, `fina`, and `isol` features.

## Example

Write a short Arabic word whose letters all connect. Each letter takes its initial, medial, or final form so the word renders as one continuous cursive run rather than three separate shapes sitting side by side. Change one letter's neighbor and the connected form changes with it.

## Common mistake

Assuming that a font containing Arabic characters will display Arabic correctly. Without shaping, those characters appear in their isolated forms, unconnected, which reads as broken. Joining is also not the same as a [ligature](ligature.md). A ligature fuses two specific signs into one glyph for one combination. Joining is the systematic reshaping of letters as they connect along a whole word.

## In practice

When you choose a design tool for a joining script, check that it shapes the text, not just that it can show the characters. Type a real word and confirm the letters connect and pick up their positional forms. Support varies between tools, so this is worth testing early rather than discovering at handoff. On the font side, the typeface has to include the positional forms and the OpenType features that select them, so verify the font covers the script fully, not only its base letters.

## Related terms

[Arabic script](arabic-script.md) · [Text shaping](text-shaping.md) · [Complex text layout](complex-text-layout.md) · [Ligature](ligature.md) · [Script rules](script-rules.md)

## Further reading

* Code & specs: [The Unicode Standard (latest version)](https://www.unicode.org/versions/latest/)
* Foundations: [Internationalization (W3C)](https://www.w3.org/International/)
