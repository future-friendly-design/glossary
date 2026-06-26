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
  The shirorekha is a horizontal stroke at the top of a series of symbols in
  Devanagari and related scripts that joins the letters of a word into one
  connected line.
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

The shirorekha is a horizontal stroke at the top of a series of symbols in Devanagari and related scripts that joins the letters of a word into one connected line. It's considered part of the shape of the letterform, not a separate mark.&#x20;

For example, in this Devanagari script example  `नमस्ते`, the unbroken line across the top of the word is the shirorekha.

### Why it matters in design systems

In scripts such as [Devanagari](devanagari.md) and [Bengali](bengali-assamese.md), most letters hang from the shirorekha, the line along the top, instead of sitting on a [baseline](baseline.md) the way [Latin](latin-script.md) does.<sup>1</sup> The shirorekha is part of the shapes of the letters themselves, not a separate [mark](../language-terms/writing-systems-and-scripts/mark.md) added on top; neighbouring letters are drawn so it runs unbroken from one to the next, and that join is what visually ties the letters of a word together.<sup>2</sup> Which scripts carry a shirorekha, and that it joins across a word, are [script rules](../language-terms/writing-systems-and-scripts/script-rules.md): they hold for every language written in the script.

That one property reaches several design-system decisions. The first is spacing. [Letter-spacing](letter-spacing.md), the [tracking](tracking.md) you might add to Latin headings or labels, has to be turned off for a script with a shirorekha: it inserts a gap between each unit, the gap lands on the seam where the shirorekha joins, and the top line breaks so the word looks split.<sup>3</sup> It is the same reason connected scripts like [Arabic](arabic-script.md) reject letter-spacing.<sup>4</sup> A tracking token that is safe, even useful, on Latin cannot be applied once across the board; letter-spacing has to be scoped by script.

The second is alignment. Because these scripts hang from the shirorekha, its hanging baseline is not the baseline Latin sits on, so mixing Devanagari with Latin on one line, or setting [line-height](line-height.md) tokens, has to account for the hanging baseline rather than Latin assumptions.<sup>1</sup> Marks stack above and below the shirorekha too, so a line-height tuned to Latin can clip them.

The third is that covering the script is necessary, not sufficient. For the font, the shirorekha still has to join continuously across a whole word, including where consonants form [conjuncts](conjunct.md) or half-forms, or the word looks broken.<sup>2</sup> (It is sometimes called the matra line, which is not the same as a [matra](../language-terms/writing-systems-and-scripts/matra.md) vowel mark.) A font that covers every letter can still render the join wrong; the connection and the alignment both have to be right.

A quick thing to keep in mind: the shirorekha is just one of a script's rules. A script usually has several, and they all apply to every language that uses the script. So check the other [script rules](../language-terms/writing-systems-and-scripts/script-rules.md) too, not only this page. After that, look at the [orthography](../language-terms/writing-systems-and-scripts/orthography.md) for each language you support. Orthography is the language-specific layer: how that one language uses the script, like its spelling and punctuation.

***

### Related terms and mentions

[Arabic script](arabic-script.md) · [Baseline](baseline.md) · [Bengali-Assamese](bengali-assamese.md) · [Conjunct](conjunct.md) · [Devanagari](devanagari.md) · [Latin script](latin-script.md) · [Letter spacing](letter-spacing.md) · [Line height](line-height.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Matra](../language-terms/writing-systems-and-scripts/matra.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Reph](reph.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Tracking](tracking.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Foundations: [Developing OpenType Fonts for Devanagari Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/devanagari)

### Sources

1. Indic scripts that have a hanging baseline (such as Hindi, Bengali, Gujarati, Marathi, and Punjabi) take the hanging baseline as the top alignment point, unlike scripts that sit on a lower baseline - Indic Layout Requirements (W3C) [https://www.w3.org/TR/ilreq/](https://www.w3.org/TR/ilreq/)
2. Unicode calls this top stroke the headstroke; it instructs that the editorial character U+A8FB DEVANAGARI HEADSTROKE "should be designed so that it does not connect to the headstroke of the letters beside it", which confirms that the headstrokes of ordinary letters do connect across a word - The Unicode Standard, Version 16.0, Chapter 12 (South Asia-I) [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/)
3. Letter spacing inserted between the orthographic syllables of an Indic word breaks the top line; ILREQ shows a museum name plate where "the top bar is broken in letter spacing and the space letter is added between orthographic syllable", and notes that for Indic languages the space "needs to be introduced after each syllable" rather than between every character - Indic Layout Requirements (W3C), section 6 [https://www.w3.org/TR/ilreq/](https://www.w3.org/TR/ilreq/)
4. Some written languages should have no letter spacing applied; languages that use the Arabic script "expect connected letters to remain visually connected", and applying letter spacing "may lead to the text looking broken" - letter-spacing (MDN) [https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing)
