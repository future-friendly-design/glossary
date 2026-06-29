---
term: Script rules
slug: script-rules
aliases:
  - script behaviors
  - script-specific behavior
level: foundational
depth: deep
summary: >-
  Script rules define the behaviour of individual visual elements of a script
  (its symbols, including marks), such as how they can be combined or which
  direction they run.
related:
  - script
  - complex-text-layout
  - text-direction
  - joining
  - reordering
  - stacking-script
status: voice-passed
version_added: 0.1
updated: 2026-06-22T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: CSS logical properties and values (MDN)
    url: >-
      https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical_properties_and_values
    type: code
  - title: Internationalization (W3C)
    url: https://www.w3.org/International/
    type: authority
  - title: Bidirectionality and RTL (Material Design 3)
    url: https://m3.material.io/foundations/layout/bidirectionality-rtl
    type: resource
license: CC-BY-4.0
tags:
  - writing-systems-scripts
  - shaping-layout
---

# Script rules

## Definition

Script rules define the behaviour of individual visual elements of a [script](script.md) (its [symbols](symbol.md), including [marks](mark.md)), such as how they can be combined or which direction they run. They determine positioning of symbols, layout and reading direction for any [language](../linguistics/language.md) using the script in its [writing system](writing-system.md).

On top of the script rules, each language adds its own rules for using the script, called its [orthography](orthography.md). So every written language has two sets of rules to consider: the script rules and its orthography.

While this glossary doesn't cover every script rule (or every script), here's a list of script rule terms you may want to explore:

| Script rule | What it does                                                                                             | Example                                                                                                                        | Learn more                                                                                                                                                                                 |
| ----------- | -------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Direction   | which way the script runs: left to right, right to left, or top to bottom                                | [Arabic](../../terms/arabic-script.md) runs right to left ←; Japanese [tategaki](../../terms/tategaki.md) runs top to bottom ↓ | [Text direction](text-direction.md), [Left-to-right](../../terms/left-to-right.md), [Right-to-left](../../terms/right-to-left.md), [Bidirectional text](../../terms/bidirectional-text.md) |
| Joining     | whether letters connect and change shape by their position in a word                                     | Arabic letters join: ب ح ث → بحث                                                                                               | [Joining](joining.md), [Text shaping](../../terms/text-shaping.md)                                                                                                                         |
| Combination | how [marks](../../programming-terms/combining-mark.md) attach to symbols and how symbols cluster or fuse | [Devanagari](../../terms/devanagari.md) conjuncts                                                                              | [Conjunct](../../terms/conjunct.md), [Mark](mark.md), [Combining mark](../../programming-terms/combining-mark.md)                                                                          |
| Ordering    | when the order symbols are stored in differs from the order they are displayed in                        | Indic [reph](reph.md)                                                                                                          | [Reordering](../../terms/reordering.md), [Reph](reph.md)                                                                                                                                   |
| Stacking    | how symbols pile into a vertical stack                                                                   | [Tibetan](../../terms/tibetan-script.md) stacks                                                                                | [Stacking script](stacking-script.md), [Conjunct](../../terms/conjunct.md)                                                                                                                 |
| Breaking    | how the script marks word and line boundaries, which is not always a space                               | [Thai](../../terms/thai-script.md) has no word spaces: ภาษาไทย ("Thai language") is written solid                              | [Segmentation](../../terms/segmentation.md), [Tsheg](../../terms/tsheg.md)                                                                                                                 |
| Baseline    | whether symbols hang from a top headline or sit on a baseline                                            | Devanagari and Bengali hang from a headline                                                                                    | [Shirorekha](shirorekha.md), [Hanging baseline](../../terms/hanging-baseline.md), [Baseline](../../terms/baseline.md)                                                                      |

### Why it matters in design systems

Script rules define several behaviours that influence design decisions that extend past typography and font styling. When a design system needs to support multiple languages, it is important to zoom out and look at the design elements and styling properties related to text in order to understand the full scope of system requirements.

A script rule can affect design system decisions at multiple levels:

1. Typography - Script rules determine which typefaces can be used, what glyph coverage is required, and what vertical space the script needs. These are system-level decisions made before any text is placed in a design.
2. Text layers - Script rules affect how text behaves once it is placed: alignment, line start position, glyph rendering, spacing, and how characters interact with their neighbours.
3. Design system components - Script rules can change the internal layout of components that contain text, including navigation, forms, buttons, and icons.
4. Page level patterns - Script rules can determine reading flow and the placement of key interface elements across an entire layout.
5. Code and functional systems - Script rules determine what the implementation needs to support: writing direction set at the document level, shaping engine requirements for complex scripts, and whether CSS properties are built to adapt to direction or are hardcoded to a physical side of the screen.

### Example

A design system supports English, French, and German. All three languages use the Latin script, which runs left to right. From a script rules perspective, the system requirements are the same across all three: the same text direction, the same joining behaviour, the same glyph rendering model. Adding French or German is primarily an orthography and translation concern, not a script rules concern.

The system then needs to expand to support Arabic. Arabic uses a different script with different rules. The direction rule alone changes requirements at every level: text alignment and line start position at the text layer, internal component layout and icon orientation at the component layer, navigation placement and reading flow at the page level, and document-level direction and logical CSS properties at the code layer.

This is where component naming becomes a problem. A button component with a prop named `icon-right` assumes a physical position. In a right-to-left layout, that icon now sits on the leading edge of the button, which is the opposite of the intended position. A component built with physical naming (`left`, `right`) requires overrides or separate definitions for each direction. A component built with logical naming (`icon-start`, `icon-end`) adapts automatically when direction changes at the document level.<sup>2</sup>

Arabic also has a joining rule: letters connect to their neighbours and change shape depending on their position in a word. This affects the code and functional systems to ensure glyph rendering is accurate and requires a shaping engine to produce correct output. A font that covers Arabic characters but lacks the correct [OpenType](../../terms/opentype.md) shaping tables will render the script incorrectly even if the direction is set right.<sup>1</sup>

Two script rules, direction and joining, and the scope of work to add a single language using a different script has expanded well beyond what adding both French and German required.

### Common mistake

Treating language support as a translation task. When a design system expands to a new language, the assumption is often that the work is limited to content: translate the strings, check the font, ship. This is true when the new language shares the same script and script rules as the existing ones. It is not true when the script is different.

A different script can change requirements at every level of the system. Icons that sit beside text or indicate direction are part of the text layout and need to be reconsidered. Component props and layer names that use physical positions (`icon-right`, `label-left`) assume a direction that may no longer apply. Page layouts built around a left-to-right reading flow may need to be mirrored. CSS properties hardcoded to physical sides of the screen cannot adapt without overrides or rewrites.

These are not translation problems. They are structural problems, and they are significantly more expensive to discover after the system is built than to plan for at the start.

### In practice

* **Audit component naming for physical assumptions before adding a new script. -** Props and layer names like `icon-left`, `button-right`, and `label-start` are design decisions, not just labels. Physical names (`left`, `right`) break when direction changes. Logical names (`start`, `end`) adapt automatically. Review component props, token names, and Figma layer names for physical positioning language before committing to a new script, not after.
* **Treat icons as part of the text layout, not separate from it. -** An icon that sits beside a text label, points in a direction, or indicates sequence is affected by script rules. A forward arrow that means "next" in a left-to-right layout points the wrong way in a right-to-left one. Document which icons in your system are directional and which are not, and define how each behaves when direction changes.<sup>3</sup> See [text direction](text-direction.md) and [bidirectional text](../../terms/bidirectional-text.md).
* **Test with real content in every script you support. -** A single English word in a component does not reveal script rule failures. Use real content in the actual scripts you are testing, at realistic lengths, including mixed-script content where a right-to-left paragraph contains a left-to-right product name or URL. Script rendering problems are often invisible until real content is in place.

***

### Related terms and mentions

[Arabic script](../../terms/arabic-script.md) · [Baseline](../../terms/baseline.md) · [Bidirectional text](../../terms/bidirectional-text.md) · [Combining mark](../../programming-terms/combining-mark.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Conjunct](../../terms/conjunct.md) · [Devanagari](../../terms/devanagari.md) · [Font](../../terms/font.md) · [Glyph](../../terms/glyph.md) · [Hanging baseline](../../terms/hanging-baseline.md) · [Joining](joining.md) · [Language](../linguistics/language.md) · [Left-to-right](../../terms/left-to-right.md) · [Line height](../../terms/line-height.md) · [Mark](mark.md) · [OpenType](../../terms/opentype.md) · [Orthography](orthography.md) · [Reordering](../../terms/reordering.md) · [Reph](reph.md) · [Right-to-left](../../terms/right-to-left.md) · [Script](script.md) · [Segmentation](../../terms/segmentation.md) · [Shirorekha](shirorekha.md) · [Stacking script](stacking-script.md) · [Symbol](symbol.md) · [Tategaki](../../terms/tategaki.md) · [Text direction](text-direction.md) · [Text shaping](../../terms/text-shaping.md) · [Thai script](../../terms/thai-script.md) · [Tibetan script](../../terms/tibetan-script.md) · [Tsheg](../../terms/tsheg.md) · [Typeface](../../terms/typeface.md) · [Typography](../../terms/typography.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [CSS logical properties and values (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical_properties_and_values)
* Foundations: [Internationalization (W3C)](https://www.w3.org/International/)
* Resource library: [Bidirectionality and RTL (Material Design 3)](https://m3.material.io/foundations/layout/bidirectionality-rtl)

### Sources

1. The Arabic script is written right to left and its letters take contextual joined forms (isolated, initial, medial, final); diacritic marks are positioned above and below the base letters - Developing OpenType Fonts for Arabic Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/arabic](https://learn.microsoft.com/en-us/typography/script-development/arabic)
2. Logical properties define direction-relative equivalents to their corresponding physical properties, so a layout built with them adapts when the writing direction changes - CSS logical properties and values (MDN) [https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical\_properties\_and\_values](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Logical_properties_and_values)
3. In right-to-left layouts, directional UI icons such as back and forward should be mirrored, while not all elements mirror (for example, charts can keep a left-to-right orientation) - Bidirectionality and RTL (Material Design 3) [https://m3.material.io/foundations/layout/bidirectionality-rtl](https://m3.material.io/foundations/layout/bidirectionality-rtl)
