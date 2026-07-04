---
term: Noto fonts
slug: noto-fonts
aliases: [Google Noto, No Tofu]
tags: [reference-sources]
level: intermediate
depth: core
summary: "Noto is Google's open-licensed font superfamily built to cover as many of the world's writing systems as possible so that no character renders as a blank box."
related: [tofu, font, font-coverage, fallback-font, font-subsetting, unicode]
status: voice-passed
version_added: 0.1
updated: 2026-07-04
contributors: [sam-gordashko]
further_reading:
  - title: "SIL Open Font License"
    url: https://openfontlicense.org/
    type: code
  - title: "Noto Fonts (project site)"
    url: https://notofonts.github.io/
    type: authority
license: CC-BY-4.0
---

# Noto fonts

## Definition

Noto is Google's open-licensed font superfamily built to cover as many of the world's writing systems as possible so that no character renders as a blank box.<sup>1</sup>

### Why it matters in design systems

A common assumption is that "the font supports my languages" is a solved problem once you pick a typeface. For most commercial fonts it is not: coverage runs out at the edge of the scripts they were drawn for, and the gaps show up as [tofu](tofu.md), the empty boxes a renderer draws when no available [font](font.md) has a [glyph](glyph.md) for a character. Noto exists to close those gaps. Its name is short for "no tofu", Google's aim being that users see no missing-glyph boxes;<sup>2</sup> the project spans more than 1,000 languages and over 150 writing systems, released as sans, serif, mono, and other styles.<sup>3</sup> That breadth is why it is the usual recommendation for under-resourced scripts: Noto often has coverage where no commercial font exists at all.

For a design system, Noto earns its place in three concrete decisions. First, [font-coverage](font-coverage.md): it is a dependable primary or [fallback-font](fallback-font.md) for multilingual interfaces, so the character a designer forgot about still draws instead of breaking the layout. Second, performance: the full family is enormous, so you never ship all of it. You [subset](font-subsetting.md) it to the scripts and characters a product actually uses, letting a browser download only the slices a page needs. Third, licensing: Noto is released under the [SIL Open Font License](https://openfontlicense.org/), which permits use, modification, and bundling in commercial products, so it is safe to embed rather than merely link to.<sup>4</sup>

The limit to keep in view: broad coverage is necessary but not sufficient. A script needs correct shaping (joining, reordering, conjuncts), not just the code points, and Noto's per-script quality varies because each script is built and maintained separately. Confirm the specific scripts you ship, rather than trusting "Noto covers everything" as a blanket claim.

### Example(s)

A page that sets `font-family: "Noto Sans", "Noto Sans Devanagari", "Noto Sans JP", sans-serif` can render Latin, Devanagari (`नमस्ते`), and Japanese text (`こんにちは`) in a consistent style, with each script drawn by its matching Noto family instead of falling back to tofu.

For an under-resourced script, Noto is often the only ready-made option: the Noto family for a newly encoded script may be the first freely available, embeddable font a language community has, which is why it is the common starting point for digitizing that script.

***

### Related terms and mentions

[Character](character.md) · [Code point](code-point.md) · [Conjunct](../language-terms/writing-systems-and-scripts/conjunct.md) · [Devanagari](devanagari.md) · [Fallback font](fallback-font.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Font subsetting](font-subsetting.md) · [Glyph](glyph.md) · [Joining](../language-terms/writing-systems-and-scripts/joining.md) · [Language](../language-terms/linguistics/language.md) · [Reference sources](reference-sources.md) · [Reordering](../programming-terms/text-for-digital-products-and-the-web/reordering.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [SIL](sil.md) · [Tofu](tofu.md) · [Typeface](typeface.md) · [Unicode](unicode.md)

### Further reading

- Code & specs: [SIL Open Font License](https://openfontlicense.org/)
- Foundations: [Noto Fonts (project site)](https://notofonts.github.io/)

### Sources

1. "Noto is a collection of high-quality fonts with multiple weights and widths in sans, serif, mono, and other styles" - Noto Fonts project site [https://notofonts.github.io/](https://notofonts.github.io/)
2. "The name Noto is to convey Google's goal that users see 'no more tofu.'" - Noto fonts FAQ (the Noto project) [https://github.com/notofonts/noto-fonts/blob/master/FAQ.md](https://github.com/notofonts/noto-fonts/blob/master/FAQ.md)
3. "in more than 1,000 languages and over 150 writing systems" - Noto Fonts project site [https://notofonts.github.io/](https://notofonts.github.io/)
4. "All Noto fonts (in the `fonts/` directory) are licensed under the SIL Open Font License" - notofonts.github.io repository README [https://github.com/notofonts/notofonts.github.io](https://github.com/notofonts/notofonts.github.io)
