---
term: Shirorekha
slug: shirorekha
aliases:
  - headline
  - head stroke
  - matra line
level: intermediate
depth: core
summary: >-
  The shirorekha is a horizontal stroke at the top of the letters in Devanagari
  and related scripts that joins the letters of a word into one connected line.
related:
  - conjunct
  - matra
  - reph
  - script-rules
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Developing OpenType Fonts for Devanagari Script (Microsoft)
    url: https://learn.microsoft.com/en-us/typography/script-development/devanagari
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
  - shaping-layout
---

# Shirorekha

## Definition

The shirorekha is a horizontal stroke at the top of a series of symbols in Devanagari and related scripts that joins the letters of a word into one connected line. Its considered part of the shape of the letterform, not a separate mark.&#x20;

For example, in this Devanagari script example  `नमस्ते`, the unbroken line across the top of the word is the shirorekha.

### Why it matters in design systems

In scripts such as [Devanagari](devanagari.md) and [Bengali](bengali-assamese.md), most letters hang from this top line instead of sitting on a baseline the way [Latin](latin-script.md) does.<sup>1</sup> The line is part of the shapes of the letters themselves, not a separate [mark](../language-terms/writing-systems-and-scripts/mark.md) added on top; neighbouring letters are drawn so it runs unbroken from one to the next, and that join is what visually ties the letters of a word together.<sup>2</sup> Which scripts carry it, and that it joins across a word, are [script rules](../language-terms/writing-systems-and-scripts/script-rules.md): they hold for every language written in the script.

For a font, the headline has to join continuously across a whole word, including where consonants form [conjuncts](conjunct.md) or half-forms, or the word looks broken. It is sometimes called the matra line, which is not the same as a [matra](../language-terms/writing-systems-and-scripts/matra.md) vowel mark.

For a design system, the catch is alignment. Because these scripts hang from a top line, their hanging baseline is not the baseline Latin sits on, so mixing Devanagari with Latin on one line, or setting line-height tokens, has to account for the hanging baseline rather than Latin assumptions.<sup>1</sup> Covering the letters in the font is necessary but not sufficient; the headline still has to join and align correctly.

***

### Related terms and mentions

[Bengali-Assamese](bengali-assamese.md) · [Conjunct](conjunct.md) · [Devanagari](devanagari.md) · [Latin script](latin-script.md) · [Matra](../language-terms/writing-systems-and-scripts/matra.md) · [Reph](reph.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Foundations: [Developing OpenType Fonts for Devanagari Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/devanagari)

### Sources

1. Indic scripts that have a hanging baseline (such as Hindi, Bengali, Gujarati, Marathi, and Punjabi) take the hanging baseline as the top alignment point, unlike scripts that sit on a lower baseline - Indic Layout Requirements (W3C) [https://www.w3.org/TR/ilreq/](https://www.w3.org/TR/ilreq/)
2. Unicode calls this top stroke the headstroke; it instructs that the editorial character U+A8FB DEVANAGARI HEADSTROKE "should be designed so that it does not connect to the headstroke of the letters beside it", which confirms that the headstrokes of ordinary letters do connect across a word - The Unicode Standard, Version 16.0, Chapter 12 (South Asia-I) [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/)
