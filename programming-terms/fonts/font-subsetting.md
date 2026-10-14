---
term: Font subsetting
slug: font-subsetting
aliases:
  - subsetting
level: advanced
depth: core
summary: >-
  Font subsetting is the practice of making a smaller copy of a font file by
  keeping only the shapes and instructions needed for the characters a product
  expects to use.
related:
  - font-coverage
  - fallback-font
  - variable-font
  - font
status: voice-passed
version_added: 0.1
updated: 2026-10-13T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: unicode-range (MDN)
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/unicode-range
    type: code
  - title: Incremental Font Transfer (W3C)
    url: https://www.w3.org/TR/IFT/
    type: authority
license: CC-BY-4.0
tags:
  - typography
---

# Font subsetting

## Definition

Font subsetting is the practice of making a smaller copy of a font file by keeping only the shapes and instructions needed for the characters a product expects to use.<sup>1</sup>

Font subsetting is something done to a [font](font.md), the file that holds the shapes software uses to show text.<sup>2</sup>

A subset is a smaller part taken from a whole set. A font holds one or more shapes for each character it covers, together with instructions for combining and placing those shapes. The smaller copy is called a subset font, or just a subset.

### Why it matters in design systems

A font is a file, and a file has to be downloaded before a page can use it. A font that covers many scripts can be a large file, and a page written in one language uses only a small part of it. Subsetting removes the rest so the page appears sooner. It is a sensible thing to do. It is also done out of the designer's sight, in the step that prepares a product for release, or by the service that hosts the fonts. Google Fonts, one such service, uses the slicing described below extensively.<sup>3</sup>

That is why it belongs in this glossary. Subsetting changes a font's [coverage](font-coverage.md), the set of characters it has shapes for, and the font you chose and tested is no longer the font your readers receive.

There are two common ways to do it.

| Way                | How it works                                                                                                                                                             | Who decides what a reader gets   |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------- |
| Cut it once        | One smaller file is made in advance from a list of characters. Everything not on the list is removed.                                                                    | Whoever wrote the list.          |
| Cut it into slices | The font is split into several files, each labelled with the characters it holds. The browser downloads a slice only when the page uses a character from it.<sup>4</sup> | The text on the page, each time. |

On the web, the label on a slice is written in CSS, the language that sets how web pages look, with a setting called `unicode-range`. A browser is not allowed to use a slice for any character outside its label.<sup>5</sup>

Both ways carry the same two risks, and neither risk produces an error message.

**The first risk is text nobody listed.** A list of characters is a prediction about what people will write, and people write their names. Suppose a subset kept only the letters English uses. Vietnamese is also written in Latin script, and in the phrase Tiếng Việt ("Vietnamese") the letters ế and ệ are not on that list. The software takes those two letters from some other font, called a [fallback font](fallback-font.md), and the rest from yours, so one word is shown in two fonts.<sup>6</sup> For a script that was left out entirely, such as the Ethiopic in ሰላም ("selam", "peace"), the whole word goes to a fallback font, or to empty boxes, called [tofu](tofu.md), when the device has no font for it. The full font may have held every one of those shapes. The file that was shipped does not.

**The second risk is losing the instructions.** Many scripts need more than one shape per character. In Arabic script, the letters kāf ك, tāʾ ت and bāʾ ب connect when they form the word كتب, and the font holds the instructions that make them connect. A subsetting tool has settings for which of these instructions are kept and which are dropped.<sup>7</sup> Slicing has its own version of the problem, because instructions that link a character in one slice to a character in another can be lost.<sup>8</sup> A working group at W3C, the body that sets web standards, studied slicing and gives an example from the scripts of India. When one font covers two of those scripts and is sliced by script, the characters the two scripts share are taken from only one slice, and the text becomes unreadable.<sup>9</sup> Every character still appears. The word is wrong.

Both failures are invisible to the team that caused them, because the team's own text was on the list. So the questions are worth asking before the font is shipped:

* **What was the subset built from?** It should be built from the scripts and languages the product supports, including text people type in. It should never be built from the words that happen to be in the product today.
* **Were the instructions for each script kept?** Ask for a real word in each supported script to be checked after subsetting, by someone who reads it.
* **What happens to a character outside the subset?** There should be a named fallback font for each script, chosen on purpose.
* **Is it tested again when the release process changes?** A subset is made by a setting, and a setting can change without anyone looking at the text.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Character](../text-in-software/character.md) · [Ethiopic script](../../language-terms/writing-systems-and-scripts/ethiopic-script.md) · [Fallback font](fallback-font.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [GPOS](gpos.md) · [GSUB](gsub.md) · [Joining](../../language-terms/writing-systems-and-scripts/joining.md) · [Language](../../language-terms/linguistics/language.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Text shaping](../text-shaping-and-layout/text-shaping.md) · [Tofu](tofu.md) · [Variable font](variable-font.md) · [Font terms](./)

### Further reading

* Code & specs: [unicode-range (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/unicode-range)
* Foundations: [Incremental Font Transfer (W3C)](https://www.w3.org/TR/IFT/)

### Sources

1. "A font subset is a modified version of a font file" "that contains only the data needed to render a subset of: the code points, layout features, and design-variation space" - Incremental Font Transfer, W3C Candidate Recommendation Draft, section 3.1 [https://www.w3.org/TR/IFT/#font-subset-dfn](https://www.w3.org/TR/IFT/#font-subset-dfn)
2. "A font subsetter produces a font subset from an input font based on a desired font subset definition" - Incremental Font Transfer, W3C Candidate Recommendation Draft, section 7.1 [https://www.w3.org/TR/IFT/#encoding-considerations](https://www.w3.org/TR/IFT/#encoding-considerations)
3. "For example, a font which supports Latin, Greek, and Cyrillic can be split into three subsets; typically only one will be downloaded. Google Fonts uses this approach extensively" - Progressive Font Enrichment: Evaluation Report, W3C Working Group Note, section 2.5 [https://www.w3.org/TR/PFE-evaluation/](https://www.w3.org/TR/PFE-evaluation/)
4. "If the page doesn't use any character in this range, the font is not downloaded; if it uses at least one, the whole font is downloaded" - unicode-range, MDN Web Docs [https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/unicode-range](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/unicode-range)
5. "User agents must not download or use the font for codepoints outside this set" - CSS Fonts Module Level 3, W3C Recommendation, section 4.5 [https://www.w3.org/TR/css-fonts-3/](https://www.w3.org/TR/css-fonts-3/)
6. "If no matching face exists or the matched face does not contain a glyph for the character to be rendered, the next family name is selected and the previous three steps repeated" - CSS Fonts Module Level 3, W3C Recommendation, section 5.2 [https://www.w3.org/TR/css-fonts-3/](https://www.w3.org/TR/css-fonts-3/)
7. "Specify (=), add to (+=) or exclude from (-=) the comma-separated set of OpenType layout feature tags that will be preserved" - subset, fontTools documentation [https://fonttools.readthedocs.io/en/latest/subset/index.html](https://fonttools.readthedocs.io/en/latest/subset/index.html)
8. "Unlike traditional font subsetting approaches Incremental Font Transfer retains the encoding of layout rules between segments" - Incremental Font Transfer, W3C Candidate Recommendation Draft, section 1 [https://www.w3.org/TR/IFT/](https://www.w3.org/TR/IFT/)
9. "the shared characters will be rendered from only one of the subsets based on the priority of the unicode range declarations. As a result syllable clustering and glyph shaping doesn't work correctly; the text doesn't just look less beautiful, it becomes unreadable" - Progressive Font Enrichment: Evaluation Report, W3C Working Group Note, section 2.8 [https://www.w3.org/TR/PFE-evaluation/#fail-subset](https://www.w3.org/TR/PFE-evaluation/#fail-subset)
