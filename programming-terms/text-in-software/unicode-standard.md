---
term: Unicode Standard
slug: unicode-standard
aliases:
  - The Unicode Standard
level: foundational
depth: core
summary: >-
  The Unicode Standard is the published specification that defines Unicode,
  maintained by the Unicode Consortium.
related:
  - unicode
  - code-point
  - noto-fonts
status: voice-passed
version_added: 0.1
updated: 2026-08-04T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: The Unicode Standard, current version (unicode.org)
    url: https://www.unicode.org/versions/latest/
    type: authority
license: CC-BY-4.0
tags:
  - reference-sources
---

# Unicode Standard

## Definition

The Unicode Standard is the published specification that defines [Unicode](unicode.md), maintained by the Unicode Consortium.

It is one document set in four parts: the core specification, the code charts, the Unicode Standard Annexes, and the Unicode Character Database.<sup>1</sup>

### Why it matters in design systems

Those four parts do different jobs, and knowing which one answers your question saves a lot of searching. The core specification gives the general principles, requirements for conformance, and guidelines for implementers. The code charts show representative [glyphs](../fonts/glyph.md) for all the Unicode characters. The annexes, each a separate numbered document covering one aspect of text in detail, supply the information that anyone building software is required to follow. The Character Database supplies the normative and informative data implementers need.<sup>2</sup>

When an entry here explains how text is segmented, normalized, or laid out in two directions at once, it is citing an annex, and those annexes are the closest thing the field has to a shared rulebook. If you ever need to settle an argument about how text should behave, this is where the answer lives.

The standard is versioned, and the version matters more than it looks. The current release is Unicode 18.0.0, published 2026 September 16,<sup>3</sup> which added 13,007 characters for a total of 172,808.<sup>4</sup> A character existing in the standard is the starting line, not the finish: newly encoded scripts still need fonts drawn, keyboards built, and operating system support shipped before anyone can actually use them, which is why an encoding date and a usable date can be years apart. When you are supporting a recently encoded script, check what your platforms and fonts actually implement rather than assuming the standard's coverage is available to you.

The Unicode Consortium was founded in 1988 and incorporated in 1991.<sup>5</sup>

***

### Related terms and mentions

[Bidirectional text](../../language-terms/writing-systems-and-scripts/bidirectional-text.md) · [Character](character.md) · [Code point](code-point.md) · [Font](../fonts/font.md) · [Glyph](../fonts/glyph.md) · [Noto fonts](../fonts/noto-fonts.md) · [Normalization](normalization.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Segmentation](segmentation.md) · [Unicode](unicode.md) · [Text encoding & character terms](./)

### Further reading

* Foundations: [The Unicode Standard, current version (unicode.org)](https://www.unicode.org/versions/latest/)

### Sources

1. "Version 18.0 of the Unicode Standard consists of: The core specification / The code charts for this version / The Unicode Standard Annexes / The Unicode Character Database (UCD)" - Unicode 18.0.0, Technical Overview [https://www.unicode.org/versions/Unicode18.0.0/](https://www.unicode.org/versions/Unicode18.0.0/)
2. "The core specification gives the general principles, requirements for conformance, and guidelines for implementers. The code charts show representative glyphs for all the Unicode characters. The Unicode Standard Annexes supply detailed normative information about particular aspects of the standard. The Unicode Character Database supplies normative and informative data for implementers to allow them to implement the Unicode Standard" - Unicode 18.0.0, Technical Overview [https://www.unicode.org/versions/Unicode18.0.0/](https://www.unicode.org/versions/Unicode18.0.0/)
3. "Unicode® 18.0.0 / 2026 September 16" - Unicode 18.0.0 [https://www.unicode.org/versions/Unicode18.0.0/](https://www.unicode.org/versions/Unicode18.0.0/)
4. "Unicode 18.0 adds 13,007 characters, for a total of 172,808 characters" - Unicode 18.0.0 [https://www.unicode.org/versions/Unicode18.0.0/](https://www.unicode.org/versions/Unicode18.0.0/)
5. "Founded in 1988, incorporated in 1991" - About the Unicode Consortium [https://home.unicode.org/about-unicode/](https://home.unicode.org/about-unicode/)
