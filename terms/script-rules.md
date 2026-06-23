---
term: Script rules
slug: script-rules
aliases:
  - script behaviors
  - script-specific behavior
level: foundational
depth: deep
summary: >-
  Script rules are the behaviors a script imposes on its own signs and marks,
  such as direction and joining, independent of any language.
related:
  - script
  - complex-text-layout
  - text-direction
  - joining
  - reordering
  - stacking-script
status: voice-passed
version_added: 0.1
updated: 2026-06-22T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Internationalization (W3C)
    url: https://www.w3.org/International/
    type: authority
  - title: The Unicode Standard (latest version)
    url: https://www.unicode.org/versions/latest/
    type: code
license: CC-BY-4.0
tags:
  - writing-systems-scripts
  - shaping-layout
---

# Script rules

## Definition

Script rules are the behaviors a script imposes on its own signs and marks, such as direction and joining, independent of any language. TEST

## Why it matters

A script is not a passive set of shapes you place in a row. Each script carries behaviors that a design tool, a font, and a layout engine all have to handle, and those behaviors hold no matter which language you write with the script. There are six common ones:

* **Direction**: which way the script runs, such as left-to-right or right-to-left. See [text direction](text-direction.md).
* **Joining**: whether signs connect and change shape based on their position in a word. See [joining](joining.md).
* **Combination**: how [marks](combining-mark.md) attach to signs and how signs cluster or fuse, as in a [conjunct](conjunct.md).
* **Ordering**: when the order signs are stored in differs from the order they are displayed in. See [reordering](reordering.md).
* **Stacking and positioning**: how signs pile into blocks or stack, as in a [stacking script](stacking-script.md).
* **Breaking**: how the script marks word and line boundaries, which is not always a space. See [segmentation](segmentation.md).

These belong to the script itself, which is why they are separate from orthography, the spelling rules of a single language.

## Example

The Arabic script runs right to left, joins its letters into cursive forms that change by position, and places short vowel marks above and below the letters. A designer prototyping an Arabic interface has to account for all three behaviors before any Arabic-language spelling rules enter the picture, because they are properties of the script, not the language.

## Common mistake

Treating script rules and orthography as the same thing. Script rules belong to the script and hold for every language written in it. Orthography belongs to one language. The Latin script runs left to right whether you write English or Vietnamese, so direction is a script rule. The spelling, capitalization, and diacritic conventions change between those two languages, so those are orthography. Switch the language and the orthography changes while the script rules stay put.

## In practice

This is a checklist for bringing a script to life in a design tool. Take your focus script and walk the six behaviors: does it run right to left, do its letters join, do marks stack on the signs, does anything reorder, does it form blocks, and how does it break into words. The answers tell you what your tool and fonts must support before you build. Many tools display the characters of a script but do not apply its rules, so a prototype can look correct in a glyph table and still render wrong in a real sentence. Test with a real word, not a single letter.

## Related terms

[Script](../language-terms/writing-systems-and-scripts/script.md) · [Complex text layout](complex-text-layout.md) · [Text direction](text-direction.md) · [Joining](joining.md) · [Reordering](reordering.md) · [Stacking script](stacking-script.md)

## Further reading

* Foundations: [Internationalization (W3C)](https://www.w3.org/International/)
* Code & specs: [The Unicode Standard (latest version)](https://www.unicode.org/versions/latest/)
