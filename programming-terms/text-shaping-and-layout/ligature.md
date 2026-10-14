---
term: Ligature
slug: ligature
aliases: []
level: foundational
depth: deep
summary: >-
  A ligature is a single glyph, a shape in a font, that stands for two or more
  characters at once.
related:
  - glyph
  - gsub
  - opentype-features
  - conjunct
status: voice-passed
version_added: 0.1
updated: 2026-10-13T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: font-variant-ligatures (MDN)
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-ligatures
    type: code
  - title: Use OpenType features (Figma Learn)
    url: >-
      https://help.figma.com/hc/en-us/articles/4913951097367-Use-OpenType-features
    type: design-tool
  - title: 'Unicode Glossary: Ligature'
    url: https://www.unicode.org/glossary/#ligature
    type: authority
license: CC-BY-4.0
tags:
  - shaping-layout
---

# Ligature

## Definition

A ligature is a single [glyph](../text-for-digital-products-and-the-web/glyph.md), a shape in a font, that stands for two or more characters at once.<sup>1</sup>

Ligatures are one of the results of [text shaping](text-shaping.md), the step in which software works out which of a font's shapes to draw for a piece of text, and where each shape goes: software called a [shaping engine](shaping-engine.md) swaps the separate shapes for the single one.<sup>2</sup>

Some ligatures are a style choice, while others are part of how a [script](../../language-terms/writing-systems-and-scripts/script.md) is written, and a word looks wrong without them. For example, the Arabic letters lam (ل) and alef (ا) are written together as one shape: لا.<sup>3</sup>

### Why it matters in design systems

Type "fi" in many fonts and look closely. The two letters are drawn as one merged shape: you typed two characters, and the software drew one glyph from the [font](../text-for-digital-products-and-the-web/font.md). That glyph is a ligature.<sup>4</sup>

In English this is an improvement, not a need, and nothing breaks if the two letters are drawn apart.<sup>5</sup>

That is not true everywhere. The Latin script has only a few ligatures in use today, and other scripts use many.<sup>6</sup> In some of them a ligature is not an improvement. It is the correct way to write.

There are three kinds you will meet most often, and the difference between them is the thing to learn:

| Kind                                           | Example                                                 | To begin with | Can you switch it off?                                                                                      |
| ---------------------------------------------- | ------------------------------------------------------- | ------------- | ----------------------------------------------------------------------------------------------------------- |
| Required                                       | The Arabic letters lam (ل) and alef (ا) are drawn as لا | On            | Not with the normal controls. The script needs it, and tools are advised not to offer a switch.<sup>7</sup> |
| Standard                                       | `f` and `i` are drawn as one "fi" glyph                 | On            | Yes.<sup>8</sup>                                                                                            |
| Discretionary, which means left to your choice | `c` and `t` are drawn as one merged "ct" glyph          | Off           | Yes. You switch it on for a special effect.<sup>9</sup>                                                     |

Devanagari has ligatures too. When consonants meet with no vowel between them they can merge, so the consonants क and ष become क्ष. That merged shape is called a [conjunct](../../language-terms/writing-systems-and-scripts/conjunct.md), a ligature of two or more consonants.<sup>10</sup>

It helps to keep three levels apart:

* **The script** sets whether a ligature is expected. Arabic expects lam and alef to merge into one shape, in almost every style of the script.<sup>11</sup>
* **The font** has to contain the ligature: the merged glyph, and an instruction that says when to use it.<sup>12</sup>
* **The software** that draws the text has to follow that instruction.<sup>13</sup> This software is called a shaping engine.

A ligature changes what is drawn, not what is stored: the text still holds two characters, and they can be drawn as two glyphs or as one.<sup>14</sup>

The three kinds have short names, which you may see in design tools and in code: `rlig` for required, `liga` for standard and `dlig` for discretionary. Each one is a named group of instructions in the font, and these groups are called [OpenType features](../../design-terms/typography/opentype-features.md), after [OpenType](../../design-terms/typography/opentype.md), the most widely used font format.<sup>15</sup>

A ligature is also not the same as [joining](../../language-terms/writing-systems-and-scripts/joining.md). In Arabic, most letters connect to their neighbours, but each letter keeps a glyph of its own. In a ligature, two or more glyphs are replaced by one.<sup>16</sup>

### Common mistake

Treating ligatures as one switch. A type guideline that says "ligatures off" is usually thinking of English, where a ligature is a style choice. The same word also covers the lam and alef of Arabic, which is not a style choice at all. Write the rule by kind instead: standard and discretionary ligatures are yours to choose, and required ligatures are not yours to switch off. CSS, the code that styles web pages, already separates the two: its strongest setting, `font-variant-ligatures: none`, leaves required ligatures in place.<sup>17</sup>

### In practice

* **Find the control before you write the rule.** On the web it is the CSS property `font-variant-ligatures`, where the value `common-ligatures` covers the standard kind.<sup>18</sup> In Figma, the Details tab of the Type menu lists Ligatures and Rare Ligatures under Letterforms.<sup>19</sup> Rare Ligatures is Figma's name for the discretionary kind.<sup>20</sup> Make the same choice in both places, so the design and the built product match.
* **Expect letter spacing to remove them.** When [letter spacing](../../design-terms/typography/letter-spacing.md) is anything other than zero, the CSS rules tell browsers not to use optional ligatures, because a merged pair cannot be spaced evenly with the letters around it.<sup>21</sup> So a heading set with wide letter spacing loses its "fi" ligature, and that is the intended result. Required ligatures are kept.
* **Test required ligatures with a real word.** Put a word that contains lam and alef into each tool and each font your team uses, and you should see the one merged glyph: لا. If you see anything else, either the font lacks the ligature or the tool is not shaping the text. Ask someone who reads the script to check, because a missing ligature is easy to overlook when you do not.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Character](../text-in-software/character.md) · [Complex text layout](complex-text-layout.md) · [Conjunct](../../language-terms/writing-systems-and-scripts/conjunct.md) · [Devanagari script](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Font](../text-for-digital-products-and-the-web/font.md) · [Glyph](../text-for-digital-products-and-the-web/glyph.md) · [GSUB](gsub.md) · [Joining](../../language-terms/writing-systems-and-scripts/joining.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Letter spacing](../../design-terms/typography/letter-spacing.md) · [Mark](../../language-terms/writing-systems-and-scripts/mark.md) · [OpenType](../../design-terms/typography/opentype.md) · [OpenType features](../../design-terms/typography/opentype-features.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Shaping engine](shaping-engine.md) · [Text shaping](text-shaping.md) · [Text shaping & layout terms](./)

### Further reading

* Code & specs: [font-variant-ligatures (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-ligatures)
* Design tools: [Use OpenType features (Figma Learn)](https://help.figma.com/hc/en-us/articles/4913951097367-Use-OpenType-features)
* Foundations: [Unicode Glossary: Ligature](https://www.unicode.org/glossary/#ligature)

### Sources

1. "A glyph representing a combination of two or more characters" - Unicode Glossary: Ligature [https://www.unicode.org/glossary/#ligature](https://www.unicode.org/glossary/#ligature)
2. "correctly shaping a text run in any script may still involve Unicode normalization, ligature substitutions, mark positioning, kerning, and applying other font features" - Script-specific shaping, HarfBuzz Manual [https://harfbuzz.github.io/script-specific-shaping.html](https://harfbuzz.github.io/script-specific-shaping.html)
3. "When supported by the style of the font, lam-alef ligatures are considered obligatory" - The Unicode Standard, Version 18.0, Chapter 9: Middle East-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-9/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-9/)
4. "it is common for the "f, i" letter sequence to appear in print as the single ligature glyph" - Why do I need a shaping engine?, HarfBuzz Manual [https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)
5. "While ligatures like "ﬁ" are optional typographic refinements, some languages require certain substitutions to be made in order to display text correctly" - Why do I need a shaping engine?, HarfBuzz Manual [https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)
6. "In the Latin script, there are only a few in modern use, such as the ligatures between “f” and “i” or “f” and “l”. Other scripts make use of many ligatures, depending on the font and style" - Unicode Glossary: Ligature [https://www.unicode.org/glossary/#ligature](https://www.unicode.org/glossary/#ligature)
7. "This feature is used for ligatures that are required for correct display of a script"; its UI suggestion is "Control of this feature should not generally be exposed to the user" - Registered features, p-t: 'rlig', OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/features\_pt](https://learn.microsoft.com/en-us/typography/opentype/spec/features_pt)
8. "This feature covers the ligatures which the designer/manufacturer judges should be used in normal conditions"; its UI suggestion is that it "should be active by default" - Registered features, k-o: 'liga', OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/features\_ko](https://learn.microsoft.com/en-us/typography/opentype/spec/features_ko)
9. "This feature covers those ligatures which may be used for special effect, at the user’s preference"; its UI suggestion is "This feature should be off by default" - Registered features, a-e: 'dlig', OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/features\_ae](https://learn.microsoft.com/en-us/typography/opentype/spec/features_ae)
10. "Consonant conjuncts (aka 'conjuncts') - Ligatures of two or more consonants" - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
11. "The lam-alef type of ligatures are extremely common in the Arabic script. These ligatures occur in almost all font designs, except for a few modern styles" - The Unicode Standard, Version 18.0, Chapter 9: Middle East-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-9/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-9/)
12. "it depends on the whether or not the font includes an "ﬁ" glyph and on the level of ligature application you wish to perform" - Why do I need a shaping engine?, HarfBuzz Manual [https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)
13. "The GSUB table provides a way to describe such substitutions, enabling applications to apply such substitutions during text layout and rendering to achieve desired results" - GSUB: Glyph Substitution Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gsub](https://learn.microsoft.com/en-us/typography/opentype/spec/gsub)
14. "Sequences such as “fi” may be displayed with two independent glyphs or with a ligature glyph" - The Unicode Standard, Version 18.0, Chapter 2: General Structure [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-2/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-2/)
15. "There are several font formats that a program might encounter, each of which has a set of standard text-shaping rules. The dominant format is OpenType" - What is HarfBuzz?, HarfBuzz Manual [https://harfbuzz.github.io/what-is-harfbuzz.html](https://harfbuzz.github.io/what-is-harfbuzz.html)
16. "When a string of glyphs can be replaced with a single ligature glyph, the first glyph is substituted with the ligature" - GSUB: Glyph Substitution Table, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/gsub](https://learn.microsoft.com/en-us/typography/opentype/spec/gsub)
17. "Required ligatures, needed for correctly rendering complex scripts, are not affected by the settings above, including ‘none’" - CSS Fonts Module Level 3, W3C Recommendation, 6.4 Ligatures: the font-variant-ligatures property [https://www.w3.org/TR/css-fonts-3/#font-variant-ligatures-prop](https://www.w3.org/TR/css-fonts-3/#font-variant-ligatures-prop)
18. "These values control the most common ligatures, like for fi, ffi, th, or similar. They correspond to the OpenType values liga and clig" - font-variant-ligatures (MDN) [https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-ligatures](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-ligatures)
19. The Details tab of the Type menu lists Ligatures and Rare Ligatures under Letterforms - Use OpenType features (Figma Learn) [https://help.figma.com/hc/en-us/articles/4913951097367-Use-OpenType-features](https://help.figma.com/hc/en-us/articles/4913951097367-Use-OpenType-features)
20. "(As an example, "discretionary ligatures" became "rare ligatures.")" - An ode to OpenType: Fall in love with the secret world of fonts, Figma blog (Marcin Wichary, 2019) [https://www.figma.com/blog/opentype-font-features/](https://www.figma.com/blog/opentype-font-features/)
21. "When the effective spacing between two characters is not zero (due to either justification or a non-zero value of letter-spacing), user agents should not apply optional ligatures, i.e. those that are not defined as required for fundamentally correct glyph shaping" - CSS Text Module Level 3, W3C, Tracking: the letter-spacing property [https://www.w3.org/TR/css-text-3/#letter-spacing-property](https://www.w3.org/TR/css-text-3/#letter-spacing-property)
