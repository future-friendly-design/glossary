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

The shirorekha is a horizontal stroke at the top of a series of symbols in Devanagari and related scripts that joins the letters of a word into one connected line. It's considered part of the shape of the letterform, not a separate mark.

For example, in Devanagari `नमस्ते`, the unbroken line across the top of the word is the shirorekha.

While this glossary doesn't cover every script, here are the scripts that use a shirorekha. The linked ones have a page in the glossary.

| Script                                              | Languages                        | How the shirorekha works here                                                                            |
| --------------------------------------------------- | -------------------------------- | -------------------------------------------------------------------------------------------------------- |
| [Devanagari](../../terms/devanagari.md)             | Hindi, Marathi, Nepali, Sanskrit | Most letters hang from a continuous shirorekha that runs unbroken across the word.<sup>1</sup>           |
| [Bengali-Assamese](../../terms/bengali-assamese.md) | Bengali, Assamese                | A top bar joins the letters along the top, and the script's hanging baseline is based on it.<sup>2</sup> |
| Gurmukhi                                            | Punjabi                          | Letters are joined at the top bar; a few letters leave a gap but still join on either side.<sup>3</sup>  |

### Why it matters in design systems

In scripts such as [Devanagari](../../terms/devanagari.md) and [Bengali](../../terms/bengali-assamese.md), most letters hang from the shirorekha, the line along the top, instead of sitting on a [baseline](../../terms/baseline.md) the way [Latin](../../terms/latin-script.md) does.<sup>4</sup> The shirorekha is part of the shapes of the letters themselves, not a separate [mark](mark.md) added on top; neighbouring letters are drawn so it runs unbroken from one to the next, and that join is what visually ties the letters of a word together.<sup>1</sup> Which scripts carry a shirorekha, and that it joins across a word, are [script rules](script-rules.md): they hold for every language written in the script.

A script with a shirorekha influences several design system decisions including spacing, alignment, and font coverage.

[Letter-spacing](../../terms/letter-spacing.md), the [tracking](../../terms/tracking.md) you might add to Latin headings or labels, should not be applied character by character to a script with a shirorekha.

* It inserts a gap between each unit, the gap lands on the seam where the shirorekha joins, and the top line breaks so the word looks split.<sup>5</sup>
* It is the same reason connected scripts like [Arabic](../../terms/arabic-script.md) reject letter-spacing.<sup>6</sup>
* A tracking token that is safe, even useful, on Latin cannot be applied once across the board; letter-spacing has to be scoped by script.

Letters hanging from the shirorekha at the top means the design system has to account for the text alignment as a [hanging baseline](../../terms/hanging-baseline.md) which is different from the baseline Latin sits on.

* Script rules may also define marks that stack above and below the shirorekha.
* This means if you have a fixed value as your [line-height](../../terms/line-height.md) that works for Latin script using languages, it may need to be adjusted to ensure scripts with shirorekha don't appear clipped or cut off.

In digital design and programming, ensuring you have chosen a font with coverage for the specific script with the shirorekha is important.

* The shirorekha has to join continuously across a whole word, including where consonants form [conjuncts](../../terms/conjunct.md) or half-forms, or the word looks broken.<sup>1</sup> (It is sometimes called the matra line, which is not the same as a [matra](matra.md) vowel mark.)
* A font that covers every letter can still render the join wrong if it doesn't have coverage for letters with shirorekha; the connection and the alignment both have to be right.

A quick thing to keep in mind: the shirorekha is just one of a script's rules. A script usually has several, and they all apply to every language that uses the script. So check the other [script rules](script-rules.md) too, not only this page. After that, look at the [orthography](orthography.md) for each language you support. Orthography is the language-specific layer: how that one language uses the script, like its spelling and punctuation.

***

### Related terms and mentions

[Arabic script](../../terms/arabic-script.md) · [Baseline](../../terms/baseline.md) · [Bengali-Assamese](../../terms/bengali-assamese.md) · [Conjunct](../../terms/conjunct.md) · [Devanagari](../../terms/devanagari.md) · [Hanging baseline](../../terms/hanging-baseline.md) · [Latin script](../../terms/latin-script.md) · [Letter spacing](../../terms/letter-spacing.md) · [Line height](../../terms/line-height.md) · [Mark](mark.md) · [Matra](matra.md) · [Orthography](orthography.md) · [Reph](reph.md) · [Script rules](script-rules.md) · [Tracking](../../terms/tracking.md) · [Writing systems & scripts](./)

### Further reading

* Foundations: [Developing OpenType Fonts for Devanagari Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/devanagari)

### Sources

1. Unicode calls this top stroke the headstroke; it instructs that the editorial character U+A8FB DEVANAGARI HEADSTROKE "should be designed so that it does not connect to the headstroke of the letters beside it", which indicates that the headstrokes of ordinary letters do connect across a word - The Unicode Standard, Version 16.0, Chapter 12 (South Asia-I) [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/)
2. Bengali has a "top bar that joins the letters", and its hanging baseline is based on that top bar - Bengali/Bangla Orthography Notes, r12a (W3C i18n) [https://r12a.github.io/scripts/beng/bn.html](https://r12a.github.io/scripts/beng/bn.html)
3. "Within a Gurmukhi word, spacing glyphs are joined together at the top bar (shirorekha)", though "some letters create a gap in the line (while still joining at either side)" - Gurmukhi/Punjabi Orthography Notes, r12a (W3C i18n) [https://r12a.github.io/scripts/guru/pa.html](https://r12a.github.io/scripts/guru/pa.html)
4. Indic scripts that have a hanging baseline (such as Hindi, Bengali, Gujarati, Marathi, and Punjabi) take the hanging baseline as the top alignment point, unlike scripts that sit on a lower baseline - Indic Layout Requirements (W3C) [https://www.w3.org/TR/ilreq/](https://www.w3.org/TR/ilreq/)
5. Letter spacing inserted between the orthographic syllables of an Indic word breaks the top line; ILREQ shows a museum name plate where "the top bar is broken in letter spacing and the space letter is added between orthographic syllable", and notes that for Indic languages the space "needs to be introduced after each syllable" rather than between every character - Indic Layout Requirements (W3C), section 6 [https://www.w3.org/TR/ilreq/](https://www.w3.org/TR/ilreq/)
6. Some written languages should have no letter spacing applied; languages that use the Arabic script "expect connected letters to remain visually connected", and applying letter spacing "may lead to the text looking broken" - letter-spacing (MDN) [https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing)
