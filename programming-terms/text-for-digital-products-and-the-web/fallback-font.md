---
term: Fallback font
slug: fallback-font
aliases: [font stack, font fallback]
tags: [typography]
level: intermediate
depth: deep
summary: A fallback font is a font that software uses in place of the one you chose, either because your font is not available or because it holds no shape for a character in the text.
related: [font-coverage, font-subsetting, font]
status: voice-passed
version_added: 0.1
updated: 2026-10-13
contributors: [sam-gordashko]
further_reading:
  - title: "font-family (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/font-family
    type: code
  - title: CSS Fonts Module Level 3 (W3C)
    url: https://www.w3.org/TR/css-fonts-3/
    type: authority
license: CC-BY-4.0
---

# Fallback font

## Definition

A fallback font is a font that software uses in place of the one you chose, either because your font is not available or because it holds no shape for a character in the text.<sup>1</sup>

A [font](font.md) is a file of drawn shapes, and it only has shapes for the characters its makers drew. The set of characters a font has shapes for is its [font coverage](font-coverage.md), and no font covers everything. So a product does not name one font. It names a list of fonts in order of preference, often called a font stack, and every font after the first one is a fallback.

### Why it matters in design systems

Look closely at a line of text that mixes two scripts, such as an English sentence with a name from another script in the middle of it. Often the name looks a little heavier than the words around it, or a little larger, or it sits slightly higher on the line. It is being shown in a different font.

This page is probably doing it right now. The Amharic word ሰላም ("selam", "peace") is written in [Ethiopic script](../../language-terms/writing-systems-and-scripts/ethiopic-script.md). Unless the font this page uses for English also covers Ethiopic, some other font on your device is supplying those three shapes, and nobody who made this page chose it.

Here is how that other font gets found. The software goes through the text one character at a time, and for each character it works down these steps until one of them succeeds.<sup>2</sup>

| Step | What the software tries                                           | Who chose the result                                                              |
| ---- | ----------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| 1    | The first font in your list.                                      | You.                                                                              |
| 2    | Each later font in your list, in order.<sup>3</sup>               | You.                                                                              |
| 3    | Any font on the device that has a shape for the character.<sup>4</sup> | The browser and the device. The result can differ from one to the next.<sup>5</sup> |
| 4    | Nothing has it, so a placeholder is shown.<sup>6</sup>            | Nobody.                                                                           |

These are the steps a web browser follows. They come from CSS, the language that sets how web pages look, where the list is written with a property called `font-family`. The placeholder in step 4 is usually an empty box, nicknamed [tofu](../../design-terms/typography/tofu.md).

Because the search runs for each character and not for each word or paragraph, a single line can be drawn from two or three fonts, and so can a single word. That has consequences you can see.

Two fonts set to the same size do not look the same size.<sup>7</sup> The fallback can look bigger, smaller, bolder or lighter than its neighbours even though every setting is identical. Fonts made for different scripts also need different amounts of room above and below the line.<sup>8</sup> And when one line uses more than one font, CSS does not say how tall that text should be, so the spacing you set as a [line height](../../design-terms/typography/line-height.md) may not hold and may not match between browsers.<sup>9</sup> The result is that mixed-script text shifts: lines sit further apart where the fallback appears, and a button that fitted its label in one language no longer fits it in another.

There is a second way to meet a fallback. A font that has to be downloaded is not there in the first moment a page appears, so the page may be drawn in a fallback first and then redrawn when your font arrives. If the two fonts have different proportions, the whole layout moves in front of the reader. The closer the fallback's proportions are to your font's, the smaller that movement is.<sup>10</sup>

### Common mistake

Judging the fallback on your own screen. Step 3 depends on which fonts a device has, and a designer's computer usually has far more fonts than a customer's phone, including ones installed for work. Text that looks fine to you may be shown in a different font on the next device, or as boxes on a third. Never having seen a problem tells you about your own machine and very little about anyone else's.

### In practice

* **Name a font for every script you support.** Put it in the list on purpose, so that step 3 is rarely reached. In a design system this means the font family value is a list, not one name: for example `font-family: "Noto Sans", "Noto Sans Ethiopic", sans-serif`. The [Noto fonts](../../design-terms/typography/noto-fonts.md) are a free collection with a family for most scripts.
* **End the list with a generic name.** Names such as `sans-serif` mean "any font of this general kind", and adding one as the last item is the recommended safety net.<sup>11</sup> It is not a design choice, though. What a generic name gives you can change with the character, the language of the text and the person's own settings.<sup>12</sup>
* **Choose fallbacks that sit well beside the main font.** Compare them in a real mixed-script line, at the sizes you use. Look at weight, apparent size and the height of the line, and adjust the fallback, not the main font.
* **Check that the fallback is correct, not only present.** A font can hold every character of a script and still lack the instructions that script needs for connecting or stacking its shapes. [Font coverage](font-coverage.md) explains how to test for that.
* **Look at it on other devices.** Borrow a phone on a different system and open the same screen. It is the only way to see what step 3 does to your design.

***

### Related terms and mentions

[Character](../text-in-software/character.md) · [Ethiopic script](../../language-terms/writing-systems-and-scripts/ethiopic-script.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Font subsetting](font-subsetting.md) · [Glyph](glyph.md) · [Language](../../language-terms/linguistics/language.md) · [Line height](../../design-terms/typography/line-height.md) · [Noto fonts](../../design-terms/typography/noto-fonts.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Tofu](../../design-terms/typography/tofu.md) · [Fonts](../../design-terms/fonts/)

### Further reading

* Code & specs: [font-family (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family)
* Foundations: [CSS Fonts Module Level 3 (W3C)](https://www.w3.org/TR/css-fonts-3/)

### Sources

1. "If no matching face exists or the matched face does not contain a glyph for the character to be rendered, the next family name is selected and the previous three steps repeated" - CSS Fonts Module Level 3, W3C Recommendation, section 5.2 [https://www.w3.org/TR/css-fonts-3/](https://www.w3.org/TR/css-fonts-3/)
2. "For each character in the run a font family is chosen and a particular font face is selected containing a glyph for that character" - CSS Fonts Module Level 3, W3C Recommendation, section 5 [https://www.w3.org/TR/css-fonts-3/](https://www.w3.org/TR/css-fonts-3/)
3. "font selection is done one character at a time, so that if an available font does not have a glyph for a needed character, the latter fonts are tried" - font-family, MDN Web Docs [https://developer.mozilla.org/en-US/docs/Web/CSS/font-family](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family)
4. "If there are no more font families to be evaluated and no matching face has been found, then the user agent performs a system font fallback procedure to find the best match for the character to be rendered" - CSS Fonts Module Level 3, W3C Recommendation, section 5.2 [https://www.w3.org/TR/css-fonts-3/](https://www.w3.org/TR/css-fonts-3/)
5. "The result of this procedure may vary across user agents" - CSS Fonts Module Level 3, W3C Recommendation, section 5.2 [https://www.w3.org/TR/css-fonts-3/](https://www.w3.org/TR/css-fonts-3/)
6. "If a particular character cannot be displayed using any font, the user agent should indicate by some means that a character is not being displayed" - CSS Fonts Module Level 3, W3C Recommendation, section 5.2 [https://www.w3.org/TR/css-fonts-3/](https://www.w3.org/TR/css-fonts-3/)
7. "For any given font size, the apparent size and legibility of text varies across fonts" - CSS Fonts Module Level 3, W3C Recommendation, section 3.6 [https://www.w3.org/TR/css-fonts-3/](https://www.w3.org/TR/css-fonts-3/)
8. "different scripts prefer different line metrics. Noto tries to provide suitable line metrics for each script rather than forcing all scripts to fit one" - Noto fonts FAQ (the Noto project) [https://github.com/notofonts/noto-fonts/blob/main/FAQ.md](https://github.com/notofonts/noto-fonts/blob/main/FAQ.md)
9. "If more than one font is used (this could happen when glyphs are found in different fonts), the height of the content area is not defined by this specification" - CSS 2, W3C Recommendation, section 10.6.1 [https://www.w3.org/TR/CSS2/visudet.html](https://www.w3.org/TR/CSS2/visudet.html)
10. "Authors are advised to use fallback fonts in their font lists that closely match the metrics of the downloadable fonts to avoid large page reflows where possible" - CSS Fonts Module Level 3, W3C Recommendation, section 4.8 [https://www.w3.org/TR/css-fonts-3/](https://www.w3.org/TR/css-fonts-3/)
11. "Authors are encouraged to append a generic font family as a last alternative for improved robustness" - CSS Fonts Module Level 3, W3C Recommendation, section 3.1 [https://www.w3.org/TR/css-fonts-3/](https://www.w3.org/TR/css-fonts-3/)
12. "the generics may be composite faces (with different typefaces based on such things as the Unicode range of the character, the language of the containing element, user preferences and system settings, among others)" - CSS Fonts Module Level 3, W3C Recommendation, section 3.1.1 [https://www.w3.org/TR/css-fonts-3/](https://www.w3.org/TR/css-fonts-3/)
