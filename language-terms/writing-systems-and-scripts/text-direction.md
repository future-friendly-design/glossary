---
term: Text direction
slug: text-direction
aliases:
  - writing direction
  - base direction
  - directionality
level: foundational
depth: deep
summary: Text direction is a script rule that defines the intended direction of reading and writing the symbols in the script, such as left to right, right to left, or top to bottom.
related:
  - bidirectional-text
  - complex-text-layout
  - left-to-right
  - right-to-left
  - tategaki
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: dir (MDN HTML global attribute)
    url: https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir
    type: code
  - title: Structural markup and right-to-left text in HTML (W3C)
    url: https://www.w3.org/International/questions/qa-html-dir
    type: authority
  - title: Bidirectionality and RTL (Material Design 3)
    url: https://m3.material.io/foundations/layout/bidirectionality-rtl
    type: resource
license: CC-BY-4.0
tags:
  - writing-systems-scripts
  - shaping-layout
---

# Text direction

## Definition

Text direction is a script rule that defines the intended direction of reading and writing the symbols in the script, such as left to right, right to left, or top to bottom.

For example, the [Latin script](../../terms/latin-script.md) runs [left to right](../../terms/left-to-right.md), the [Arabic](../../terms/arabic-script.md) and [Hebrew](../../terms/hebrew-script.md) scripts run [right to left](../../terms/right-to-left.md), and Japanese can be set top to bottom in vertical columns.

Like all script rules, text direction applies to any [language](../linguistics/language.md) using the [script](script.md) in its [writing system](writing-system.md).

While this glossary doesn't cover every script, here are some of the scripts to explore, organized by text direction. You can select a linked term to navigate to its glossary page.

| Direction | How it runs | Example scripts |
| --- | --- | --- |
| [Left to right](../../terms/left-to-right.md) (LTR) | Horizontal, starting at the left edge; lines stack down the page. | [Latin script](../../terms/latin-script.md), [Greek script](../../terms/greek-script.md), [Cyrillic](../../terms/cyrillic.md), [Devanagari](../../terms/devanagari.md) |
| [Right to left](../../terms/right-to-left.md) (RTL) | Horizontal, starting at the right edge; lines stack down the page. | [Arabic script](../../terms/arabic-script.md), [Hebrew script](../../terms/hebrew-script.md), Thaana, Syriac, N'Ko, Adlam |
| Top to bottom | Stacked in vertical columns. CJK usually runs horizontally but can be set vertically, its columns advancing right to left ([tategaki](../../terms/tategaki.md)); traditional Mongolian is written vertically, its columns advancing left to right. | [CJK](../../terms/cjk.md), [Mongolian script (traditional)](../../terms/mongolian-script.md) |

### Why it matters in design systems

A script's text direction reaches across the design system: typography and font styling, text and icon layers, component and page layouts, and code and functional systems. For multi-language design systems, adding support for a new language with the same text direction is a much smaller scope of work than adding one with a different text direction.

If you suspect your design system will support languages with more than one text direction at any point in the future, there are a few things you can do now to prevent rework later.

#### Typography and font styling

For typography and font styling, it's generally a good idea to choose a typeface that explicitly supports the script you are working in, so its script rules, like text direction, are handled by the font. For example, a typeface built specifically for the Latin script won't have the glyphs required to support Arabic symbols, and vice versa.

Once you have script-specific typefaces, font styling also has to account for how spacing changes with direction. In a horizontal script the space between lines runs vertically (line height); set the same text top to bottom and that line spacing runs horizontally instead, as the gap between columns. So the axis your spacing applies to flips with the direction.

#### Text and icon layers

Looking at text layers, the spacing around the bounding box holding the text changes with each text direction, as does the alignment of the text within it. By default, text in a left-to-right direction aligns left, and text in a right-to-left direction aligns right.

Icons that communicate direction, like arrows and chevrons, need to be considered alongside the text direction and re-oriented to match it: mirrored between left to right and right to left, or rotated for vertical text, so their meaning holds. The position of an icon next to its text label may also need to move.

For example, an arrow communicating the next step in a user onboarding flow appears to the right of the label in a left-to-right direction, pointing right: `Save and continue →`. Translate the label to a right-to-left language and the arrow has to flip to ← and move to the other side of the label; leave it as → and it now points backward, reading as "go back" instead of "continue."

So mirror icons whose direction tracks reading order, but leave icons whose direction is a fixed convention, like a media player's play and pause buttons ⏯️, which keep the same orientation in every text direction.<sup>1</sup>

#### Components, patterns, and page layouts

Zooming out from individual elements to components, patterns, and whole pages, text direction sets the reading flow, which in turn influences where key interface elements sit across a layout: navigation, forms, buttons, and icons.

When naming design system components, patterns, and design elements, prefer logical names like `icon-start` or `padding-end` over physical names like `icon-left` and `padding-right`, so a component follows the reading direction instead of being pinned to one side.

Zoom out further to the content itself, and a single line can hold more than one direction at once, known as [bidirectional text](../../terms/bidirectional-text.md). For example, an Arabic sentence (RTL) that mentions an English brand name or a number (LTR).

Separately, one language may use more than one writing system, or a single script that can be written in more than one direction. For example, traditional Mongolian is written vertically (top to bottom), but can also be set left to right.

Be sure to consider the language-specific requirements, known as the [orthography](orthography.md), on top of script rules like text direction. You may discover that a language has more than one writing system, so rather than assuming the script by location, your site may need to offer a setting that lets a user choose between them. This is where the functional side of the system takes on [complex text layout](../../terms/complex-text-layout.md) requirements.

#### Code and functional systems

In code, declaring the language or script does not set the text direction. A `lang="ar"` attribute, even one carrying a script subtag such as `-Arab`, has no effect on how the text is ordered, and the browser will not infer direction from the content. A script gives its characters an inherent direction, but the base direction of an element, the setting that makes bidirectional text resolve correctly, is something a developer declares on purpose. Leave it unset and right-to-left text can lay out left to right and align to the wrong edge.<sup>2</sup>

On the web you set base direction with the HTML `dir` attribute or the CSS `direction` property.

Base direction is what makes mixed text (like an English brand name in an Arabic sentence) come out right. When one line holds both right-to-left and left-to-right text, the Unicode Bidirectional Algorithm uses the base direction to work out the visual order and to resolve neutral characters like spaces and punctuation.<sup>3</sup>

Direction is not only horizontal. Some scripts run top to bottom in vertical columns: Japanese, Chinese, and Korean can be set this way (the traditional Japanese mode is [tategaki](../../terms/tategaki.md)), and traditional [Mongolian](../../terms/mongolian-script.md) is written vertically. On the web this is the CSS `writing-mode` property, where `vertical-rl` sets the columns of [CJK](../../terms/cjk.md) text to advance right to left and `vertical-lr` advances them left to right for Mongolian.<sup>4</sup>

Direction is just one of a script's [script rules](script-rules.md), and the same cross-level cascade applies to each of them, so check the others a script you support might have, such as [joining](joining.md) and [stacking](stacking-script.md). And on top of the script rules, each language that uses the script has its own orthography, the spelling and punctuation conventions that can add further requirements.

### In practice

* **Set base direction explicitly, do not rely on the language:** use the HTML `dir` attribute (or `dir="auto"` for content whose direction you do not know) or the CSS `direction` property. A `lang` attribute, even with a script subtag, does not set direction. The mixed-direction case is [bidirectional text](../../terms/bidirectional-text.md).
* **Build layouts with logical CSS properties:** properties like `margin-inline` and `text-align: start` follow the text's direction instead of being pinned to the left or right edge, so one layout flips correctly between left to right and right to left.<sup>5</sup>
* **Test every direction you support with real content:** include a right-to-left paragraph with an embedded left-to-right run such as a brand name or a URL, and if you support vertical text, test the whole component in `writing-mode: vertical-rl`, not just the body copy. Confirm right-to-left and vertical behaviour with readers of those languages.

***

### Related terms and mentions

[Arabic script](../../terms/arabic-script.md) · [Bidirectional text](../../terms/bidirectional-text.md) · [CJK](../../terms/cjk.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Cyrillic](../../terms/cyrillic.md) · [Devanagari](../../terms/devanagari.md) · [Greek script](../../terms/greek-script.md) · [Hebrew script](../../terms/hebrew-script.md) · [Joining](joining.md) · [Language](../linguistics/language.md) · [Latin script](../../terms/latin-script.md) · [Left-to-right](../../terms/left-to-right.md) · [Mongolian script (traditional)](../../terms/mongolian-script.md) · [Orthography](orthography.md) · [Right-to-left](../../terms/right-to-left.md) · [Script](script.md) · [Script rules](script-rules.md) · [Stacking script](stacking-script.md) · [Tategaki](../../terms/tategaki.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [dir (MDN HTML global attribute)](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)
* Foundations: [Structural markup and right-to-left text in HTML (W3C)](https://www.w3.org/International/questions/qa-html-dir)
* Resource library: [Bidirectionality and RTL (Material Design 3)](https://m3.material.io/foundations/layout/bidirectionality-rtl)

### Sources

1. In right-to-left layouts, directional UI icons such as back and forward are mirrored, while some elements such as charts can keep their left-to-right orientation - Bidirectionality and RTL (Material Design 3) [https://m3.material.io/foundations/layout/bidirectionality-rtl](https://m3.material.io/foundations/layout/bidirectionality-rtl)
2. Most scripts are left to right, while Adlam, Arabic, Hebrew, N'Ko, Syriac, and Thaana are right to left; a language declaration does not set directionality, "even if the language declaration has a script subtag", so the base direction must be declared with the `dir` attribute - Structural markup and right-to-left text in HTML (W3C) [https://www.w3.org/International/questions/qa-html-dir](https://www.w3.org/International/questions/qa-html-dir)
3. The Unicode Bidirectional Algorithm reorders text for display from the prevailing base direction, which also resolves neutral characters such as spaces and punctuation - Unicode Bidirectional Algorithm basics (W3C) [https://www.w3.org/International/articles/inline-bidi-markup/uba-basics](https://www.w3.org/International/articles/inline-bidi-markup/uba-basics)
4. Vertical text is set with the CSS `writing-mode` property: `vertical-rl` lays out lines top to bottom with columns advancing right to left, and `vertical-lr` advances columns left to right; Chinese, Japanese, Korean, and Mongolian are written vertically - writing-mode (MDN) [https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode)
5. Logical properties such as `margin-inline` and `text-align: start` are direction-relative, so a layout built with them adapts when the writing direction changes instead of being pinned to a physical side - CSS logical properties and values (MDN) [https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical_properties_and_values](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical_properties_and_values)
