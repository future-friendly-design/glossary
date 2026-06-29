---
term: Text direction
slug: text-direction
aliases:
  - writing direction
  - base direction
  - directionality
level: foundational
depth: deep
summary: >-
  Text direction is the way a script runs across the page, such as left to
  right, right to left, or top to bottom.
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

| Direction                                           | How it runs                                                                                                                                                                                                                                        | Example scripts                                                                                                                                                        |
| --------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Left to right](../../terms/left-to-right.md) (LTR) | Horizontal, starting at the left edge; lines stack down the page.                                                                                                                                                                                  | [Latin script](../../terms/latin-script.md), [Greek script](../../terms/greek-script.md), [Cyrillic](../../terms/cyrillic.md), [Devanagari](../../terms/devanagari.md) |
| [Right to left](../../terms/right-to-left.md) (RTL) | Horizontal, starting at the right edge; lines stack down the page.                                                                                                                                                                                 | [Arabic script](../../terms/arabic-script.md), [Hebrew script](../../terms/hebrew-script.md), Thaana, Syriac, N'Ko, Adlam                                              |
| Top to bottom                                       | Stacked in vertical columns. CJK usually runs horizontally but can be set vertically, its columns advancing right to left ([tategaki](../../terms/tategaki.md)); traditional Mongolian is written vertically, its columns advancing left to right. | [CJK](../../terms/cjk.md), [Mongolian script (traditional)](../../terms/mongolian-script.md)                                                                           |

### Why it matters in design systems

A script's text direction impacts the design system across typography and font styling, text layer and icon position, component and page layouts, code and functional systems. For multi-language design systems, adding support for a new language with the same text direction is a much smaller scope of work than adding support for languages with a different text direction.&#x20;

If you suspect your design system will support languages with more than one text direction at any point in the future, there are a few things you can do now to prevent rework later.&#x20;

#### Typography and font styling

For typography and font styling, its generally a good idea to choose a typeface that explicitly supports the script you are working in to ensure its script rules, like text direction, are supported by the font package. For example, a typeface built for specifically for Latin scripts wont have the glyphs required to support Arabic symbols and vice versa.

Once you have script specific typefaces, you'll also need to ensure that font styling for each language you are supporting considers the differences in vertical and horizontal spacing requirements. For example, vertical spacing needs for scripts running right to left (RTL) or left to right(LTR) are different than scripts running top to bottom.&#x20;

#### Text and icon layers

Looking at text layers, the spacing assigned to the bounding box or div holding the text will be different for each text direction. As will the alignment of the text within its bounding box. For example,   scripts with a left to right text direction will be left aligned, and scripts with right to left text direction will be right aligned.&#x20;

Icons with symbols that communicate direction, like arrows and chevrons, need to be considered along side the text direction, sometimes requiring rotation of the symbol to ensure the meaning is maintained. The position of icons next to text labels also may need to be changed.&#x20;

For example, an arrow intended to communicate the next step in a user onboarding flow would appear on the right side of the label in a left-to-right text direction with the arrow symbol pointing right `Save and continue →` . Translate the label to a right-to-left language and the arrow has to flip to ← and move to the other side of the label; leave it as → and it now points backward, reading as "go back" instead of "continue."

For icons communicating direction it makes sense to mirror between RTL and LTR text directions. For icons that are decorative or have a univesral symbol direction they do not need to change, like the shapes used for the play and pause buttons of a music player ⏯️.

#### Components, patterns, and page layouts

Zooming out of individual design elements to look at components, patterns or page elements, the text direction determines reading flow and which influences placement of key interface elements across an entire layout including navigation, forms, buttons, and icons.&#x20;

When naming design system components, patters, and design elements, consider logical naming `icon-start` or `padding-end` instead of physicals names like `icon-left` and `padding-right` .&#x20;

If we zoom out further to consider content and context, consider that the same script can sit in more than one text direction depending on context, known as bidirectional text. For example, an Arabic sentence (RTL) that mentions an English brand name (LTR).&#x20;

And an important note: one language may support multiple writing systems with more than one script, or a single script that can be written in more than one writing direction. For example, Mongolian is traditionally written vertically, but can also be written LTR.&#x20;

Be sure to consider the language-specific requirements, known as the orthography, in addition to script rules like text direction. You may discover that a language has more than one writing system, and instead of assuming by location, your site may need to provide a setting to enable a user to choose between different scripts!

This is where the functional side of the design system introduces complex text layout requirements to be aware of.&#x20;

#### Code and functional systems

In code, a language or script declaration only controls the text direction according to the script rules. Developers need to manually the property for base direction, which assigns the direction of the text element within its div (bounding box) which makes bidirectional text possible.&#x20;

On the web you set base direction with the HTML `dir` attribute or the CSS `direction` property.&#x20;

Base direction is what makes mixed text (like an English brand name in an Arabic sentence) come out right. When one line holds both RTL and LTR text directions the [Unicode Bidirectional Algorithm](../../terms/bidirectional-text.md) uses the base direction to work out the visual order and to resolve neutral characters like spaces and punctuation.<sup>2</sup>

Direction is not only horizontal. Some scripts run top to bottom in vertical columns: Japanese, Chinese, and Korean can be set this way (the traditional Japanese mode is [tategaki](../../terms/tategaki.md)), and traditional [Mongolian](../../terms/mongolian-script.md) is written vertically. On the web this is the CSS `writing-mode` property, where `vertical-rl` sets the columns of [CJK](../../terms/cjk.md) text to advance right to left and `vertical-lr` advances them left to right for Mongolian.<sup>3</sup>

### Common mistake

Direction is just one of a script's [script rules](script-rules.md), and the same cross-level cascade applies to each of them, so check the others a script you support might have, such as [joining](joining.md) and [stacking](stacking-script.md). And on top of the script rules, each language that uses the script has its own [orthography](orthography.md), the spelling and punctuation conventions that can add further requirements.

You may discover that a language has more than one writing system, and instead of assuming by location, your site may need to provide a setting to enable a user to choose between different scripts!

Assuming the page's language or locale sets the text direction. It does not. A `lang="ar"` declaration, even one carrying a script subtag such as `-Arab`, has no effect on how the text is ordered, and the browser will not infer direction from the content either. Leave the base direction unset and right-to-left text can lay out left to right and align to the wrong edge. Direction is a decision you make on purpose, with the `dir` attribute or the CSS `direction` property, not something the language carries for you.

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

1. Most scripts are left to right, while Adlam, Arabic, Hebrew, N'Ko, Syriac, and Thaana are right to left; a language declaration does not set directionality, "even if the language declaration has a script subtag", so the base direction must be declared with the `dir` attribute - Structural markup and right-to-left text in HTML (W3C) [https://www.w3.org/International/questions/qa-html-dir](https://www.w3.org/International/questions/qa-html-dir)
2. The Unicode Bidirectional Algorithm reorders text for display from the prevailing base direction, which also resolves neutral characters such as spaces and punctuation - Unicode Bidirectional Algorithm basics (W3C) [https://www.w3.org/International/articles/inline-bidi-markup/uba-basics](https://www.w3.org/International/articles/inline-bidi-markup/uba-basics)
3. Vertical text is set with the CSS `writing-mode` property: `vertical-rl` lays out lines top to bottom with columns advancing right to left, and `vertical-lr` advances columns left to right; Chinese, Japanese, Korean, and Mongolian are written vertically - writing-mode (MDN) [https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode)
4. In right-to-left layouts, directional UI icons such as back and forward are mirrored, while some elements such as charts can keep their left-to-right orientation - Bidirectionality and RTL (Material Design 3) [https://m3.material.io/foundations/layout/bidirectionality-rtl](https://m3.material.io/foundations/layout/bidirectionality-rtl)
5. Logical properties such as `margin-inline` and `text-align: start` are direction-relative, so a layout built with them adapts when the writing direction changes instead of being pinned to a physical side - CSS logical properties and values (MDN) [https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical\_properties\_and\_values](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical_properties_and_values)
