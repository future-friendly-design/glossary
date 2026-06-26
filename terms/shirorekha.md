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
  The shirorekha is the horizontal headline that runs along the top of letters
  in Devanagari and related scripts.
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

The shirorekha is the horizontal headline that runs along the top of letters in Devanagari and related scripts.

For example, in Devanagari `नमस्ते`, the unbroken line across the top of the word is the shirorekha.

### Why it matters in design systems

In scripts such as [Devanagari](devanagari.md) and [Bengali](bengali-assamese.md), most letters hang from this top line instead of sitting on a baseline the way [Latin](latin-script.md) does. The line is what visually ties the letters of a word together, and which scripts hang from it is a [script rule](../language-terms/writing-systems-and-scripts/script-rules.md): it holds for every language written in the script.<sup>1</sup>

For a font, the headline has to join continuously across a whole word, including where consonants form [conjuncts](conjunct.md) or half-forms, or the word looks broken. It is sometimes called the matra line, which is not the same as a [matra](../language-terms/writing-systems-and-scripts/matra.md) vowel mark.

For a design system, the catch is alignment. Because these scripts hang from a top line, their hanging baseline is not the baseline Latin sits on, so mixing Devanagari with Latin on one line, or setting line-height tokens, has to account for the hanging baseline rather than Latin assumptions.<sup>1</sup> Covering the letters in the font is necessary but not sufficient; the headline still has to join and align correctly.

***

### Related terms and mentions

[Bengali-Assamese](bengali-assamese.md) · [Conjunct](conjunct.md) · [Devanagari](devanagari.md) · [Latin script](latin-script.md) · [Matra](../language-terms/writing-systems-and-scripts/matra.md) · [Reph](reph.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Foundations: [Developing OpenType Fonts for Devanagari Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/devanagari)

### Sources

1. Indic scripts that have a hanging baseline (such as Hindi, Bengali, Gujarati, Marathi, and Punjabi) take the hanging baseline as the top alignment point, unlike scripts that sit on a lower baseline - Indic Layout Requirements (W3C) [https://www.w3.org/TR/ilreq/](https://www.w3.org/TR/ilreq/)
