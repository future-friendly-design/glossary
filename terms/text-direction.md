---
term: Text direction
slug: text-direction
aliases: [writing direction, base direction, directionality]
tags: [writing-systems-scripts, shaping-layout]
level: foundational
depth: deep
summary: Text direction is the way a script runs across the page, such as left to right, right to left, or top to bottom.
related: [bidirectional-text, complex-text-layout, left-to-right, right-to-left, tategaki]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "dir (MDN HTML global attribute)"
    url: https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir
    type: code
  - title: "Structural markup and right-to-left text in HTML (W3C)"
    url: https://www.w3.org/International/questions/qa-html-dir
    type: authority
  - title: "Bidirectionality and RTL (Material Design 3)"
    url: https://m3.material.io/foundations/layout/bidirectionality-rtl
    type: resource
license: CC-BY-4.0
---

# Text direction

## Definition

Text direction is the way a script runs across the page, such as left to right, right to left, or top to bottom.

For example, the [Latin script](latin-script.md) runs [left to right](left-to-right.md), the [Arabic](arabic-script.md) and [Hebrew](hebrew-script.md) scripts run [right to left](right-to-left.md), and Japanese can be set top to bottom in vertical columns.

Like all script rules, text direction applies to any [language](../language-terms/linguistics/language.md) using the [script](../language-terms/writing-systems-and-scripts/script.md) in its [writing system](../language-terms/writing-systems-and-scripts/writing-system.md).

While this glossary doesn't cover every script, here are the directions text can run, with example scripts for each. You can select a linked term to navigate to its glossary page.

| Direction | How it runs | Example scripts |
| --- | --- | --- |
| [Left to right](left-to-right.md) (LTR) | Horizontal, starting at the left edge; lines stack down the page. | [Latin script](latin-script.md), [Greek script](greek-script.md), [Cyrillic](cyrillic.md), [Devanagari](devanagari.md) |
| [Right to left](right-to-left.md) (RTL) | Horizontal, starting at the right edge; lines stack down the page. | [Arabic script](arabic-script.md), [Hebrew script](hebrew-script.md), Thaana, Syriac, N'Ko, Adlam |
| Top to bottom | Stacked in vertical columns. CJK usually runs horizontally but can be set vertically, its columns advancing right to left ([tategaki](tategaki.md)); traditional Mongolian is written vertically, its columns advancing left to right. | [CJK](cjk.md), [Mongolian script (traditional)](mongolian-script.md) |

### Why it matters in design systems

Most scripts run left to right; a smaller set, the [Arabic](arabic-script.md) and [Hebrew](hebrew-script.md) scripts along with Thaana, Syriac, N'Ko, and Adlam, run right to left. A script has a default direction, but the direction of a whole paragraph or element is a separate setting, called its base direction, and you have to set it on purpose. The same script can sit in either base direction depending on context, so the script alone does not decide it. On the web you set base direction with the HTML `dir` attribute or the CSS `direction` property; a language or script declaration does not set it, so you must always declare it yourself.<sup>1</sup>

Base direction is also what makes mixed text come out right. When one line holds both directions, such as an Arabic sentence with an English brand name in it, the [Unicode Bidirectional Algorithm](bidirectional-text.md) uses the base direction to work out the visual order and to resolve neutral characters like spaces and punctuation.<sup>2</sup>

Direction is not only horizontal. Some scripts run top to bottom in vertical columns: Japanese, Chinese, and Korean can be set this way (the traditional Japanese mode is [tategaki](tategaki.md)), and traditional [Mongolian](mongolian-script.md) is written vertically. On the web this is the CSS `writing-mode` property, where `vertical-rl` sets the columns of [CJK](cjk.md) text to advance right to left and `vertical-lr` advances them left to right for Mongolian.<sup>3</sup>

So for a design system, no script rule reaches further than direction. Setting the base direction is only the first step; from there the change cascades across every level of the system: text alignment and where a line starts, a component's internal layout and the way its icons point, page-level reading flow, and document-level direction in code. The [script rules](../language-terms/writing-systems-and-scripts/script-rules.md) page maps that cross-level cascade in full. A layout that truly flips also needs logical CSS properties, such as `margin-inline` and `text-align: start`, so spacing and alignment follow the text instead of being pinned to one physical edge. That groundwork is what makes [complex text layout](complex-text-layout.md) possible.

Direction is just one of a script's script rules, so check the others a script you support might have, such as [joining](../language-terms/writing-systems-and-scripts/joining.md) and [stacking](../language-terms/writing-systems-and-scripts/stacking-script.md). And on top of the script rules, each language that uses the script has its own [orthography](../language-terms/writing-systems-and-scripts/orthography.md), the spelling and punctuation conventions that can add further requirements.

### Common mistake

Assuming the page's language or locale sets the text direction. It does not. A `lang="ar"` declaration, even one carrying a script subtag such as `-Arab`, has no effect on how the text is ordered, and the browser will not infer direction from the content either. Leave the base direction unset and right-to-left text can lay out left to right and align to the wrong edge. Direction is a decision you make on purpose, with the `dir` attribute or the CSS `direction` property, not something the language carries for you.

### In practice

* **Set base direction explicitly, do not rely on the language:** use the HTML `dir` attribute (or `dir="auto"` for content whose direction you do not know) or the CSS `direction` property. A `lang` attribute, even with a script subtag, does not set direction. The mixed-direction case is [bidirectional text](bidirectional-text.md).
* **Build layouts with logical CSS properties:** properties like `margin-inline` and `text-align: start` follow the text's direction instead of being pinned to the left or right edge, so one layout flips correctly between left to right and right to left.<sup>4</sup>
* **Test every direction you support with real content:** include a right-to-left paragraph with an embedded left-to-right run such as a brand name or a URL, and if you support vertical text, test the whole component in `writing-mode: vertical-rl`, not just the body copy. Confirm right-to-left and vertical behaviour with readers of those languages.

***

### Related terms and mentions

[Arabic script](arabic-script.md) · [Bidirectional text](bidirectional-text.md) · [CJK](cjk.md) · [Complex text layout](complex-text-layout.md) · [Cyrillic](cyrillic.md) · [Devanagari](devanagari.md) · [Greek script](greek-script.md) · [Hebrew script](hebrew-script.md) · [Joining](../language-terms/writing-systems-and-scripts/joining.md) · [Language](../language-terms/linguistics/language.md) · [Latin script](latin-script.md) · [Left-to-right](left-to-right.md) · [Mongolian script (traditional)](mongolian-script.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Right-to-left](right-to-left.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Stacking script](../language-terms/writing-systems-and-scripts/stacking-script.md) · [Tategaki](tategaki.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Code & specs: [dir (MDN HTML global attribute)](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)
* Foundations: [Structural markup and right-to-left text in HTML (W3C)](https://www.w3.org/International/questions/qa-html-dir)
* Resource library: [Bidirectionality and RTL (Material Design 3)](https://m3.material.io/foundations/layout/bidirectionality-rtl)

### Sources

1. Most scripts are left to right, while Adlam, Arabic, Hebrew, N'Ko, Syriac, and Thaana are right to left; a language declaration does not set directionality, "even if the language declaration has a script subtag", so the base direction must be declared with the `dir` attribute - Structural markup and right-to-left text in HTML (W3C) [https://www.w3.org/International/questions/qa-html-dir](https://www.w3.org/International/questions/qa-html-dir)
2. The Unicode Bidirectional Algorithm reorders text for display from the prevailing base direction, which also resolves neutral characters such as spaces and punctuation - Unicode Bidirectional Algorithm basics (W3C) [https://www.w3.org/International/articles/inline-bidi-markup/uba-basics](https://www.w3.org/International/articles/inline-bidi-markup/uba-basics)
3. Vertical text is set with the CSS `writing-mode` property: `vertical-rl` lays out lines top to bottom with columns advancing right to left, and `vertical-lr` advances columns left to right; Chinese, Japanese, Korean, and Mongolian are written vertically - writing-mode (MDN) [https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode)
4. Logical properties such as `margin-inline` and `text-align: start` are direction-relative, so a layout built with them adapts when the writing direction changes instead of being pinned to a physical side - CSS logical properties and values (MDN) [https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical_properties_and_values](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical_properties_and_values)
