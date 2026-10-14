---
term: Faux bold
slug: faux-bold
aliases:
  - fake bold
  - synthetic bold
level: intermediate
depth: deep
summary: Faux bold is an imitation of bold text that software makes by thickening the shapes of a regular font, because it has no bold font to use.
related:
  - faux-italic
  - font-weight
  - variable-font
status: voice-passed
version_added: 0.1
updated: 2026-10-13
contributors:
  - sam-gordashko
further_reading:
  - title: font-synthesis (MDN)
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/font-synthesis
    type: code
  - title: Using b and i elements (W3C Internationalization)
    url: https://www.w3.org/International/questions/qa-b-and-i-tags
    type: authority
license: CC-BY-4.0
tags:
  - typography
---

# Faux bold

## Definition

Faux bold is an imitation of bold text that software makes by thickening the shapes of a regular font, because it has no bold font to use.<sup>1</sup>

"Faux" is French for false, and the same thing is called fake bold or synthetic bold. A real bold is a separate [font](font.md) that a type designer drew. Faux bold is not drawn by anyone: the software takes each regular shape and draws a thin extra outline around it.<sup>2</sup> Its partner, [faux italic](faux-italic.md), is made by leaning the shapes over instead of thickening them.

### Why it matters in design systems

Press the bold button and the text gets heavier. It feels like one action with one result. What happens next depends on which font files are there to use:

| What is asked for | What the software has | What the reader gets |
| ----------------- | --------------------- | -------------------- |
| Bold | A bold font in the same family | Real bold, the shapes a type designer drew for that weight |
| Bold | Only the regular font | Faux bold: the regular shapes, thickened by the software<sup>3</sup> |
| Bold, with faking switched off | Only the regular font | The regular font, with no bold at all<sup>4</sup> |

The second row is the one nobody chooses. Nothing announces it, and at a glance the text does look bolder. The web's font specification calls it a fallback, better than nothing but below the quality of a font designed for the purpose.<sup>5</sup> A fallback is what software uses when the thing it wanted is missing.

In English text the cost is appearance: the faked bold looks heavier and rougher than a drawn one. In other scripts the cost can be the text itself. A [script](../../language-terms/writing-systems-and-scripts/script.md) is a set of symbols used to write one or more languages, and bold does not suit every script's shapes equally. Fonts for Chinese, Japanese and Korean often have no bold at all, and faking one can make the text harder to read or even change what it says.<sup>6</sup> Japanese authors may avoid both bold and italic, because characters such as 漢字 are too complicated to look good at small sizes with those effects.<sup>7</sup>

That points at an assumption worth noticing. Bold as the way to mark something important is a habit of some writing traditions, and it is not the preferred one everywhere.<sup>8</sup> East Asian documents traditionally mark emphasis with small dots or other symbols placed beside each character.<sup>9</sup>

A design system usually writes this assumption down without meaning to. A [token](../../design-terms/design-token.md) called "strong" with the value "bold" says two things at once: that every font the product uses has a bold, and that bold is how every script shows importance. A token is a named design decision that tools and code share. For a product in one language with one font family, both may be true. For a product in several scripts, check the first and ask the second. Name the token for what it means, such as strong or emphasis, and let its value differ by script: a real bold where the font family has one and the script uses it, and a different treatment where it does not.

### Common mistake

Checking bold only in the brand font. Most products show each script in a different font, because a font has shapes only for the scripts it was drawn for, and the font that steps in is chosen character by character.<sup>10</sup> The brand family may have six weights. The font that appears for Thai or Arabic text may have one. So the same "bold" style gives real bold in one language and faux bold in the next, on the same screen, and a review done in English never sees it.

### In practice

* **Supply a real bold for every script you ship.** List the fonts the product uses for each script, and check each one has the weights your styles ask for. A [variable font](../../design-terms/typography/variable-font.md), one file that holds a range of weights, is a real bold as well: the weights were drawn by the designer, and the web does not count them as faked.<sup>11</sup>
* **Switch faking off where it does harm.** On the web, this is set in CSS, the code that styles web pages: `font-synthesis-weight: none` tells the browser not to fake bold.<sup>12</sup> It can be set for one language only, so Arabic text, for example, never gets a faked style.<sup>13</sup> Remember what the third row of the table shows: the text then appears in the regular font, so the emphasis needs another way to be seen.
* **Look for it at a large size.** Set one word in the bold style, as large as the screen allows, beside the same word in a font you know has a real bold. Side by side, the difference between drawn and faked is much easier to see than it is in running text. Do this once for each script, in the browser and in each design tool your team uses.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Character](../text-in-software/character.md) · [CJK](../../language-terms/writing-systems-and-scripts/cjk.md) · [Design token](../../design-terms/design-token.md) · [Fallback font](fallback-font.md) · [Faux italic](faux-italic.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Font weight](../../design-terms/typography/font-weight.md) · [Han characters script](../../language-terms/writing-systems-and-scripts/han-characters.md) · [Language](../../language-terms/linguistics/language.md) · [Legibility](../../design-terms/typography/legibility.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Thai script](../../language-terms/writing-systems-and-scripts/thai-script.md) · [Typeface](../../design-terms/typography/typeface.md) · [Variable font](../../design-terms/typography/variable-font.md) · [Fonts](../../design-terms/fonts/)

### Further reading

* Code & specs: [font-synthesis (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/font-synthesis)
* Foundations: [Using b and i elements (W3C Internationalization)](https://www.w3.org/International/questions/qa-b-and-i-tags)

### Sources

1. "bold faces are often synthesized by user agents for faces that lack actual bold faces" - CSS Fonts Module Level 3, W3C Recommendation, 3.2 Font weight: the font-weight property [https://www.w3.org/TR/css-fonts-3/#font-weight-prop](https://www.w3.org/TR/css-fonts-3/#font-weight-prop)
2. "synthesize a bold face by drawing a thin stroke around each glyph" - CSS Fonts Module Level 4, W3C Working Draft, 2.8 Controlling synthetic faces [https://www.w3.org/TR/css-fonts-4/#font-synthesis-intro](https://www.w3.org/TR/css-fonts-4/#font-synthesis-intro)
3. "This property controls whether user agents are allowed to synthesize bold or oblique font faces when a font family lacks bold or italic faces" - CSS Fonts Module Level 3, W3C Recommendation, 3.8 Controlling synthetic faces: the font-synthesis property [https://www.w3.org/TR/css-fonts-3/#font-synthesis-prop](https://www.w3.org/TR/css-fonts-3/#font-synthesis-prop)
4. "If ‘weight’ is not specified, user agents must not synthesize bold faces" - CSS Fonts Module Level 3, W3C Recommendation, 3.8 Controlling synthetic faces: the font-synthesis property [https://www.w3.org/TR/css-fonts-3/#font-synthesis-prop](https://www.w3.org/TR/css-fonts-3/#font-synthesis-prop)
5. "Synthesis is a fallback strategy because the end result, while perhaps better than nothing at all, does not meet the level of quality of a face designed for the purpose" - CSS Fonts Module Level 4, W3C Working Draft, 2.8 Controlling synthetic faces [https://www.w3.org/TR/css-fonts-4/#font-synthesis-intro](https://www.w3.org/TR/css-fonts-4/#font-synthesis-intro)
6. "Fonts used for Chinese, Japanese, Korean and other logographic scripts tend not to include these variants and synthesizing them might impede the legibility or change the meaning of the text" - font-synthesis, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/font-synthesis](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/font-synthesis)
7. "Japanese authors may want to avoid both italicization and bolding, since their characters are too complicated to look good in small sizes with these effects" - Using b and i elements, W3C Internationalization [https://www.w3.org/International/questions/qa-b-and-i-tags](https://www.w3.org/International/questions/qa-b-and-i-tags)
8. "You should also bear in mind that bold and italic may not be the preferred style for content in certain languages" - Using b and i elements, W3C Internationalization [https://www.w3.org/International/questions/qa-b-and-i-tags](https://www.w3.org/International/questions/qa-b-and-i-tags)
9. "East Asian documents traditionally use small symbols next to each glyph to emphasize a run of text" - CSS Text Decoration Module Level 3, W3C Candidate Recommendation Draft, 3 Emphasis Marks [https://www.w3.org/TR/css-text-decor-3/#emphasis-marks](https://www.w3.org/TR/css-text-decor-3/#emphasis-marks)
10. "For each character in the run a font family is chosen and a particular font face is selected containing a glyph for that character" - CSS Fonts Module Level 3, W3C Recommendation, 5 Font Matching Algorithm [https://www.w3.org/TR/css-fonts-3/#font-matching-algorithm](https://www.w3.org/TR/css-fonts-3/#font-matching-algorithm)
11. "Variable fonts, where the font designer has provided one or more axes of variation do not count as font synthesis and their use is not affected by the font-synthesis property" - CSS Fonts Module Level 4, W3C Working Draft, 2.8 Controlling synthetic faces [https://www.w3.org/TR/css-fonts-4/#font-synthesis-intro](https://www.w3.org/TR/css-fonts-4/#font-synthesis-intro)
12. font-synthesis-weight: "none Synthesis of bold faces is not allowed" - CSS Fonts Module Level 4, W3C Working Draft, 2.8.1 Controlling synthesized bold: The font-synthesis-weight property [https://www.w3.org/TR/css-fonts-4/#font-synthesis-weight](https://www.w3.org/TR/css-fonts-4/#font-synthesis-weight)
13. "using the :lang() pseudo-class, you can disable the browser from synthesizing bold and oblique characters for a language, in this case Arabic" - font-synthesis, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/font-synthesis](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/font-synthesis)
