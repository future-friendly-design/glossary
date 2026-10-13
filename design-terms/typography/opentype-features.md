---
term: OpenType features
slug: opentype-features
aliases:
  - font features
  - feature tags
level: intermediate
depth: deep
summary: OpenType features are named groups of instructions inside a font file, each one telling software how to swap or place the font's shapes for one purpose.
related:
  - opentype
  - gsub
  - gpos
  - ligature
status: voice-passed
version_added: 0.1
updated: 2026-10-13
contributors:
  - sam-gordashko
further_reading:
  - title: OpenType fonts guide (MDN)
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Fonts/OpenType_fonts
    type: code
  - title: Use OpenType features (Figma Learn)
    url: https://help.figma.com/hc/en-us/articles/4913951097367-Use-OpenType-features
    type: design-tool
  - title: Feature Tags (Microsoft OpenType specification)
    url: https://learn.microsoft.com/en-us/typography/opentype/spec/featuretags
    type: authority
license: CC-BY-4.0
tags:
  - shaping-layout
---

# OpenType features

## Definition

OpenType features are named groups of instructions inside a font file, each one telling software how to swap or place the font's shapes for one purpose.<sup>1</sup>

The shapes are called [glyphs](../../programming-terms/text-for-digital-products-and-the-web/glyph.md), and [OpenType](opentype.md) is the font file format most fonts use today. Each feature has a short name of four letters, called a tag, such as `liga` or `smcp`.<sup>2</sup> Some features are needed for a [script](../../language-terms/writing-systems-and-scripts/script.md) to be written correctly, and others are style choices left to the designer.<sup>3</sup>

### Why it matters in design systems

Open the type settings in a design tool and you will find a list of switches with names like Ligatures, Small Caps and Stylistic Sets. Each switch turns one feature on or off. The list makes features look like a menu of extras, something to explore when a heading needs more personality.

Some of them are extras. Others are the reason a word in Arabic or Devanagari can be read at all, and those never appear in the menu. The difference between the kinds is the thing to learn:

| Kind of feature | Example | Tag | Who switches it on |
| --------------- | ------- | --- | ------------------ |
| Required by a script | The Arabic letters kāf ك, tāʾ ت and bāʾ ب take their connected forms in the word كتب | `init`, `medi`, `fina` | The software, every time. Tools are advised not to offer a switch.<sup>4</sup> |
| Required by a script | The Devanagari letters for "ka" and "ssa", with the vowel-removing mark between them, merge into क्ष | `akhn` | The software, every time. Tools are advised not to offer a switch.<sup>5</sup> |
| On to begin with | `f` and `i` are drawn as one "fi" shape, a standard [ligature](../../programming-terms/text-for-digital-products-and-the-web/ligature.md) | `liga` | The software, but you can switch it off.<sup>6</sup> |
| On to begin with | [Kerning](kerning.md): the gap between two particular letters is adjusted, so "T" and "o" sit closer in "To" | `kern` | The software, in most horizontal text, and you can switch it off.<sup>7</sup> |
| Optional | [Small caps](small-caps.md): lowercase letters are drawn as small capital letters | `smcp` | You. It starts off.<sup>8</sup> |
| Optional | Tabular figures: every digit takes the same width, so numbers line up in a column | `tnum` | You. It starts off.<sup>9</sup> |
| Optional | Stylistic sets: groups of alternative letter designs the font maker has drawn | `ss01` to `ss20` | You. They start off.<sup>10</sup> |

A feature is only an instruction. The font holds it, and the software that draws the text decides when to follow it.<sup>11</sup> For the required kind, that decision takes knowledge the font does not have. Nothing in the Arabic `init` feature says where a word begins, so the software has to work that out and then apply the feature to the right letter.<sup>12</sup> This software is called a [shaping engine](../../programming-terms/text-for-digital-products-and-the-web/shaping-engine.md), and it runs inside every browser, operating system and design tool.

Inside the font, a feature points to instructions kept in two places. [GSUB](../../programming-terms/text-for-digital-products-and-the-web/gsub.md) lists the shapes to swap, and [GPOS](../../programming-terms/text-for-digital-products-and-the-web/gpos.md) lists where to place them.<sup>13</sup> Those two entries explain how the swapping and placing work, and the ligature entry covers its three kinds in full, so none of that is repeated here.

Designers meet features in two places. In a design tool they are the switches described above. In Figma, they are on the Details tab of the Type menu, and a feature the font does not have is greyed out.<sup>14</sup> On the web they are set in CSS, the code that styles web pages, and CSS offers two routes. One is a set of settings with plain names, such as `font-variant-numeric: tabular-nums` for tabular figures.<sup>15</sup> The other is `font-feature-settings`, which takes raw tags like `"tnum"` and is meant for the rare feature that has no plain-named setting.<sup>16</sup>

Whichever route you use, a feature can only do something if the font has it. Ask for small caps from a font without them and the web shows the text as if you had not asked. No error appears.<sup>17</sup> That matters most in a product with several languages, where each script is usually shown in a different font and each font has its own list of features.

### Common mistake

Treating every feature as a style choice. A guideline that says "OpenType features: off", or a piece of software that skips features to save time, is thinking of the optional kind. Applied to everything, the same rule takes away the connected forms of Arabic and the merged consonants of Devanagari, and the text is no longer written correctly. The web guards against this: browsers must keep the required and on-to-begin-with features running, even when a page sets nothing.<sup>18</sup> Software that draws its own text, such as a chart, a game or an export to an image, has no such rule to follow. So write the guideline by kind: optional features are yours to choose, and required features are not on the table.

### In practice

* **Reach for the plain-named setting first.** The CSS rules ask authors to use the `font-variant` properties wherever they can and to keep `font-feature-settings` for special cases.<sup>19</sup> There is a practical reason as well. Each time you change one raw tag, you have to write out the whole list of tags again, so a feature set somewhere else is easy to drop without noticing.<sup>20</sup>
* **Check the feature in every font, not only the brand font.** A design token is a named design decision that tools and code share. A token for tabular figures works in the font it was tested with. In the font that steps in for another script it may do nothing, and nothing warns you. Test the tables and prices in each language you ship.
* **Know which scripts a feature is for.** Small caps exist for scripts that have capital and lowercase letters, such as Latin, Greek, Cyrillic and Armenian.<sup>21</sup> Arabic, Devanagari and Chinese writing have no capital letters, so a "small caps" label style has nothing to do there. Give such a style a second treatment for those scripts, and decide it on purpose.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Armenian script](../../language-terms/writing-systems-and-scripts/armenian-script.md) · [Conjunct](../../language-terms/writing-systems-and-scripts/conjunct.md) · [Cyrillic script](../../language-terms/writing-systems-and-scripts/cyrillic.md) · [Devanagari script](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Fallback font](../../programming-terms/text-for-digital-products-and-the-web/fallback-font.md) · [Figure styles](../../programming-terms/text-for-digital-products-and-the-web/figure-styles.md) · [Font](../../programming-terms/text-for-digital-products-and-the-web/font.md) · [Glyph](../../programming-terms/text-for-digital-products-and-the-web/glyph.md) · [GPOS](../../programming-terms/text-for-digital-products-and-the-web/gpos.md) · [Greek script](../../language-terms/writing-systems-and-scripts/greek-script.md) · [GSUB](../../programming-terms/text-for-digital-products-and-the-web/gsub.md) · [Joining](../../language-terms/writing-systems-and-scripts/joining.md) · [Kerning](kerning.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Ligature](../../programming-terms/text-for-digital-products-and-the-web/ligature.md) · [Mark](../../language-terms/writing-systems-and-scripts/mark.md) · [OpenType](opentype.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Shaping engine](../../programming-terms/text-for-digital-products-and-the-web/shaping-engine.md) · [Small caps](small-caps.md) · [Text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Virama](../../language-terms/writing-systems-and-scripts/virama.md) · [Fonts](../fonts/)

### Further reading

* Code & specs: [OpenType fonts guide (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Fonts/OpenType_fonts)
* Design tools: [Use OpenType features (Figma Learn)](https://help.figma.com/hc/en-us/articles/4913951097367-Use-OpenType-features)
* Foundations: [Feature Tags (Microsoft OpenType specification)](https://learn.microsoft.com/en-us/typography/opentype/spec/featuretags)

### Sources

1. "Features provide information about how to use the glyphs in a font to layout text for a script or language" - Feature Tags, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/featuretags](https://learn.microsoft.com/en-us/typography/opentype/spec/featuretags)
2. "By convention, registered feature tags use four lowercase letters" - Feature Tags, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/featuretags](https://learn.microsoft.com/en-us/typography/opentype/spec/featuretags)
3. "Many features expose optional capabilities that authors and typographers can choose to use at their discretion; for example, small cap forms, or kerning. But many other features are used to activate capabilities that are required for correct display of text; for example, required ligatures for Arabic script, or positioning of mark glyphs" - OpenType specification overview (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/overview](https://learn.microsoft.com/en-us/typography/opentype/spec/overview)
4. 'init': "this feature triggers substitutions that are required for correct display of cursively-connecting scripts", and "UI suggestion: Control of the feature should not generally be exposed to the user" - Registered features, f-j, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/features_fj](https://learn.microsoft.com/en-us/typography/opentype/spec/features_fj)
5. 'akhn': "the sequence Ka, Halant, Ssa should always produce the ligature Kssa", and "UI suggestion: Control of the feature should not generally be exposed to the user" - Registered features, a-e, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/features_ae](https://learn.microsoft.com/en-us/typography/opentype/spec/features_ae)
6. 'liga': "UI suggestion: This feature serves a critical function in some contexts and should be active by default" - Registered features, k-o, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/features_ko](https://learn.microsoft.com/en-us/typography/opentype/spec/features_ko)
7. 'kern': "In most horizontal text layout, this feature should be active by default", and "when activated by default for a text run, it should be possible for users to disable it for that run" - Registered features, k-o, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/features_ko](https://learn.microsoft.com/en-us/typography/opentype/spec/features_ko)
8. 'smcp': "This feature turns glyphs for lowercase characters into small capitals", and "UI suggestion: This feature should be off by default" - Registered features, p-t, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/features_pt](https://learn.microsoft.com/en-us/typography/opentype/spec/features_pt)
9. 'tnum': "Replaces figure glyphs set on proportional widths with corresponding glyphs set on uniform (tabular) widths", and "UI suggestion: This feature should be off by default" - Registered features, p-t, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/features_pt](https://learn.microsoft.com/en-us/typography/opentype/spec/features_pt)
10. 'ss01' to 'ss20': "Selects typographic alternatives for a set of glyphs", and "UI suggestion: These features should be off by default" - Registered features, p-t, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/features_pt](https://learn.microsoft.com/en-us/typography/opentype/spec/features_pt)
11. "In all cases, the text-processing client is responsible for applying, combining, and arbitrating among features and rendering the result" - Feature Tags, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/featuretags](https://learn.microsoft.com/en-us/typography/opentype/spec/featuretags)
12. "the function of the 'init' feature is to provide initial glyph forms. Nothing in the feature’s lookup tables indicates when or where to apply this feature during text processing" - Feature Tags, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/featuretags](https://learn.microsoft.com/en-us/typography/opentype/spec/featuretags)
13. "All OpenType Layout features define data for glyph substitution, glyph positioning, or both" - Feature Tags, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/featuretags](https://learn.microsoft.com/en-us/typography/opentype/spec/featuretags)
14. "Click to open the Type menu and select the Details tab", and "If a font doesn't support a specific OpenType feature, it will be greyed out in the menu" - Use OpenType features (Figma Learn) [https://help.figma.com/hc/en-us/articles/4913951097367-Use-OpenType-features](https://help.figma.com/hc/en-us/articles/4913951097367-Use-OpenType-features)
15. "tabular-nums Enables display of tabular numerals (OpenType feature: tnum)" - CSS Fonts Module Level 3, W3C Recommendation, 6.7 Numerical formatting: the font-variant-numeric property [https://www.w3.org/TR/css-fonts-3/](https://www.w3.org/TR/css-fonts-3/)
16. "It is intended as a way of providing access to font features that are not widely used but are needed for a particular use case" - CSS Fonts Module Level 3, W3C Recommendation, 6.10 Low-level font feature settings control: the font-feature-settings property [https://www.w3.org/TR/css-fonts-3/](https://www.w3.org/TR/css-fonts-3/)
17. "When a font lacks support for a given underlying font feature, text is simply rendered as if that font feature was not enabled" - CSS Fonts Module Level 3, W3C Recommendation, 7.2 Feature precedence [https://www.w3.org/TR/css-fonts-3/](https://www.w3.org/TR/css-fonts-3/)
18. "For OpenType fonts, user agents must enable the default features defined in the OpenType documentation for a given script and writing mode" - CSS Fonts Module Level 3, W3C Recommendation, 7.1 Default features [https://www.w3.org/TR/css-fonts-3/](https://www.w3.org/TR/css-fonts-3/)
19. "Authors should generally use ‘font-variant’ and its related subproperties whenever possible and only use this property for special cases" - CSS Fonts Module Level 3, W3C Recommendation, 6.10 Low-level font feature settings control: the font-feature-settings property [https://www.w3.org/TR/css-fonts-3/](https://www.w3.org/TR/css-fonts-3/)
20. "every time you want to change one of the individual features, you have to redefine the entire string" - OpenType fonts guide, MDN [https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Fonts/OpenType_fonts](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Fonts/OpenType_fonts)
21. 'smcp': "Script/language sensitivity: Used for bicameral scripts (i.e. those with case differences), such as Latin, Greek, Cyrillic, and Armenian" - Registered features, p-t, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/features_pt](https://learn.microsoft.com/en-us/typography/opentype/spec/features_pt)
