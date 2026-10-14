---
term: Faux italic
slug: faux-italic
aliases:
  - fake italic
  - synthetic oblique
  - faux oblique
level: intermediate
depth: deep
summary: >-
  Faux italic is an imitation of italic text that software makes by slanting the
  shapes of a regular font, because it has no italic font to use.
related:
  - faux-bold
  - typeface
  - variable-font
status: voice-passed
version_added: 0.1
updated: 2026-10-13T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: font-style (MDN)
    url: >-
      https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/font-style
    type: code
  - title: Using b and i elements (W3C Internationalization)
    url: https://www.w3.org/International/questions/qa-b-and-i-tags
    type: authority
license: CC-BY-4.0
tags:
  - typography
---

# Faux italic

## Definition

Faux italic is an imitation of italic text that software makes by slanting the shapes of a regular font, because it has no italic font to use.<sup>1</sup>

"Faux" is French for false, and the same thing is called fake italic or synthetic oblique. The software leans each upright shape to one side, and no type designer is involved.<sup>2</sup> Its partner, [faux bold](faux-bold.md), is made by thickening the shapes instead of leaning them.

### Why it matters in design systems

In an English sentence, a slanted word carries a message. It can mean stress, the title of a book, or a phrase borrowed from another language.<sup>3</sup> Readers of English learn this so early that italic feels like a basic part of text, something every [font](font.md) and every language must have.

It is neither. Start with the font. In Latin type, a real italic is usually not the regular letters leaning over. It is a second set of shapes, closer to handwriting, that the type designer drew.<sup>4</sup> When the font with those shapes is missing, software can lean the regular shapes over and present the result as italic.<sup>5</sup> The slant is there. The different shapes are not, and the result is of lower quality than a font designed for the purpose.<sup>6</sup>

Then the language. Italic belongs to particular [scripts](../../language-terms/writing-systems-and-scripts/script.md), the sets of symbols that languages are written with. Many scripts have no tradition of mixing a handwriting-like form into upright text at all.<sup>7</sup> Here is what the web's font standard says, case by case:

| Script or languages          | What happens when italic is asked for                                                                                                                                           |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Latin                        | If the font family has a real italic, it is used. If it does not, the regular letters are slanted, and the standard says a real italic is always the better choice.<sup>8</sup> |
| Cyrillic                     | The italic forms are very different in shape from the upright ones, so slanting the upright letters produces shapes that italic Cyrillic does not use.<sup>9</sup>              |
| Chinese, Japanese and Korean | Fonts almost always have no italic. Anything slanted on screen was made by the software.<sup>10</sup>                                                                           |
| Arabic                       | A font that holds several scripts sometimes leaves Arabic out of its italic. The standard's own example switches the faked slant off for Arabic.<sup>11</sup>                   |

For a script with no italic tradition, a slant is not a weaker version of something the reader expects. It is something software did to the text, and for Chinese, Japanese and Korean it can make the text harder to read or even change what it says.<sup>12</sup>

A design system usually writes the English habit down as a rule. A [token](../../design-terms/design-token.md) named "emphasis" with the value "italic" assumes a script that has italics and a font that has an italic file. A token is a named design decision that tools and code share. Keep the name, because emphasis is a real need in every language, and let the value change with the script. Japanese text, for example, may mark emphasis with small dots beside each character,<sup>13</sup> and set a title inside corner brackets.<sup>14</sup> Which treatment suits a language is a question for people who read it, and the token is the place to record their answer.

### Common mistake

Thinking italic and slanted are the same thing. Type has two words for leaning text. Italic is the redrawn, handwriting-like style, and oblique is the regular shapes sloped.<sup>15</sup> A faux italic is always an oblique, whatever the menu calls it. This matters when choosing a typeface, the design that a family of fonts shares: some families have a real italic, some have a drawn oblique, and some have neither. A browser, and some design tools, will still show an "italic" for a family with neither, made by the software, and nothing on screen says so. Check the list of font files, not the preview.

### In practice

* **Decide what should happen when the italic is missing.** On the web, this is set in CSS, the code that styles web pages, with a setting called `font-synthesis-style`. The value `none` forbids the faked slant, so the text stays upright.<sup>16</sup> The value `oblique-only` allows it when a style asks for oblique but not when it asks for italic.<sup>17</sup> Either one makes a missing font visible instead of hiding it.
* **Switch the slant off by language, not for the whole product.** The setting can be applied to one language, so Latin text can still fall back on the faked slant while Arabic or Japanese text never leans. Then give those languages their own emphasis style, or the emphasis disappears.
* **Mark the meaning, not the look.** Ask writers and developers to mark a phrase as emphasis, a title or a foreign term, and not simply as italic. A translator or a style for another script can then give each of the three its own treatment. If all three were marked only as italic, they can no longer be told apart.<sup>18</sup>

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [CJK](../../language-terms/writing-systems-and-scripts/cjk.md) · [Cyrillic script](../../language-terms/writing-systems-and-scripts/cyrillic.md) · [Design token](../../design-terms/design-token.md) · [Faux bold](faux-bold.md) · [Font](font.md) · [Language](../../language-terms/linguistics/language.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Legibility](../../design-terms/typography/legibility.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Script (typeface)](../../design-terms/typography/script-typeface.md) · [Typeface](typeface.md) · [Variable font](variable-font.md) · [Font terms](./)

### Further reading

* Code & specs: [font-style (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/font-style)
* Foundations: [Using b and i elements (W3C Internationalization)](https://www.w3.org/International/questions/qa-b-and-i-tags)

### Sources

1. "If no italic or oblique face is available, oblique faces can be synthesized by rendering non-obliqued faces with an artificial obliquing operation" - CSS Fonts Module Level 3, W3C Recommendation, 3.4 Font style: the font-style property [https://www.w3.org/TR/css-fonts-3/#font-style-prop](https://www.w3.org/TR/css-fonts-3/#font-style-prop)
2. "synthesize an oblique face by geometrical shearing of each glyph" - CSS Fonts Module Level 4, W3C Working Draft, 2.8 Controlling synthetic faces [https://www.w3.org/TR/css-fonts-4/#font-synthesis-intro](https://www.w3.org/TR/css-fonts-4/#font-synthesis-intro)
3. "An English document may use italicization for emphasis, document titles and idiomatic phrases in a foreign language" - Using b and i elements, W3C Internationalization [https://www.w3.org/International/questions/qa-b-and-i-tags](https://www.w3.org/International/questions/qa-b-and-i-tags)
4. "Italic font faces are generally cursive in nature, usually using less horizontal space than their unstyled counterparts, while oblique faces are usually just sloped versions of the regular face" - font-style, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/font-style](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/font-style)
5. "Oblique faces can be simulated by artificially sloping the glyphs of the regular face" - CSS Fonts Module Level 3, W3C Recommendation, 3.4 Font style: the font-style property [https://www.w3.org/TR/css-fonts-3/#font-style-prop](https://www.w3.org/TR/css-fonts-3/#font-style-prop)
6. "Synthesis is a fallback strategy because the end result, while perhaps better than nothing at all, does not meet the level of quality of a face designed for the purpose" - CSS Fonts Module Level 4, W3C Working Draft, 2.8 Controlling synthetic faces [https://www.w3.org/TR/css-fonts-4/#font-synthesis-intro](https://www.w3.org/TR/css-fonts-4/#font-synthesis-intro)
7. "Many scripts lack the tradition of mixing a cursive form within text rendered with a normal face" - CSS Fonts Module Level 3, W3C Recommendation, 3.4 Font style: the font-style property [https://www.w3.org/TR/css-fonts-3/#font-style-prop](https://www.w3.org/TR/css-fonts-3/#font-style-prop)
8. "It is always better to use an actual italic font rather than rely on a synthetic version" - CSS Fonts Module Level 3, W3C Recommendation, 3.4 Font style: the font-style property [https://www.w3.org/TR/css-fonts-3/#font-style-prop](https://www.w3.org/TR/css-fonts-3/#font-style-prop)
9. "synthesized approaches may not be suitable for scripts like Cyrillic, where italic forms are very different in shape" - CSS Fonts Module Level 3, W3C Recommendation, 3.4 Font style: the font-style property [https://www.w3.org/TR/css-fonts-3/#font-style-prop](https://www.w3.org/TR/css-fonts-3/#font-style-prop)
10. "Chinese, Japanese and Korean fonts almost always lack italic or oblique faces" - CSS Fonts Module Level 3, W3C Recommendation, 3.4 Font style: the font-style property [https://www.w3.org/TR/css-fonts-3/#font-style-prop](https://www.w3.org/TR/css-fonts-3/#font-style-prop)
11. "Fonts that support a mixture of scripts will sometimes omit specific scripts such as Arabic from the set of glyphs supported in the italic face", and, in 3.8, "The style rule below disables the use of synthetically obliqued Arabic" - CSS Fonts Module Level 3, W3C Recommendation, 3.4 Font style: the font-style property [https://www.w3.org/TR/css-fonts-3/#font-style-prop](https://www.w3.org/TR/css-fonts-3/#font-style-prop)
12. "Fonts used for Chinese, Japanese, Korean and other logographic scripts tend not to include these variants and synthesizing them might impede the legibility or change the meaning of the text" - font-synthesis, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/font-synthesis](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/font-synthesis)
13. "Emphasis dots (also known as bouten or side dots) are symbols placed alongside a run of ideographic character (cl-19) or hiragana (cl-15) characters to emphasize the text" - Requirements for Japanese Text Layout (JLREQ), W3C Working Group Note, 3.3.9 Composition of Emphasis Dots [https://www.w3.org/TR/jlreq/#composition\_of\_emphasis\_dots](https://www.w3.org/TR/jlreq/#composition_of_emphasis_dots)
14. "the Japanese person may find that the content communicates better if they use wakiten (boten marks) for emphasis, corner brackets for 『document names』" - Using b and i elements, W3C Internationalization [https://www.w3.org/International/questions/qa-b-and-i-tags](https://www.w3.org/International/questions/qa-b-and-i-tags)
15. "Italic forms are generally cursive in nature while oblique faces are typically sloped versions of the regular face" - CSS Fonts Module Level 3, W3C Recommendation, 3.4 Font style: the font-style property [https://www.w3.org/TR/css-fonts-3/#font-style-prop](https://www.w3.org/TR/css-fonts-3/#font-style-prop)
16. font-synthesis-style: "none Synthesis of oblique faces is not allowed" - CSS Fonts Module Level 4, W3C Working Draft, 2.8.2 Controlling synthesized oblique: The font-synthesis-style property [https://www.w3.org/TR/css-fonts-4/#font-synthesis-style](https://www.w3.org/TR/css-fonts-4/#font-synthesis-style)
17. font-synthesis-style: "oblique-only Synthesis of oblique faces is allowed, but they must not be used as fallback if italic is specified" - CSS Fonts Module Level 4, W3C Working Draft, 2.8.2 Controlling synthesized oblique: The font-synthesis-style property [https://www.w3.org/TR/css-fonts-4/#font-synthesis-style](https://www.w3.org/TR/css-fonts-4/#font-synthesis-style)
18. "If, however, you had used i without distinguishing the different semantics, you’d have to hunt through every page for relevant i tags and change them individually" - Using b and i elements, W3C Internationalization [https://www.w3.org/International/questions/qa-b-and-i-tags](https://www.w3.org/International/questions/qa-b-and-i-tags)
