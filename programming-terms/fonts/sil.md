---
term: SIL fonts
slug: sil
aliases:
  - SIL
  - SIL Global fonts
level: intermediate
depth: core
summary: SIL fonts are a collection of free fonts from SIL Global, made for languages that most fonts do not support well.
related:
  - font
  - noto-fonts
  - font-coverage
  - iso-639-3
  - ethnologue
  - unicode-standard
status: voice-passed
version_added: 0.1
updated: 2026-10-14
contributors:
  - sam-gordashko
further_reading:
  - title: SIL Open Font License, official text
    url: https://openfontlicense.org/open-font-license-official-text/
    type: code
  - title: Fonts (SIL Language Technology)
    url: https://software.sil.org/fonts/
    type: authority
license: CC-BY-4.0
tags:
  - reference-sources
---

# SIL fonts

## Definition

SIL fonts are a collection of free fonts from SIL Global, made for languages that most fonts do not support well.<sup>1</sup>

SIL fonts are a collection of [fonts](font.md), the files that hold the shapes software uses to show text.<sup>2</sup> They include fonts for [Ethiopic](../../language-terms/writing-systems-and-scripts/ethiopic-script.md),<sup>3</sup> [Devanagari](../../language-terms/writing-systems-and-scripts/devanagari.md),<sup>4</sup> [Arabic](../../language-terms/writing-systems-and-scripts/arabic-script.md),<sup>5</sup> Myanmar<sup>6</sup> and [Canadian Aboriginal Syllabics](../../language-terms/writing-systems-and-scripts/canadian-aboriginal-syllabics.md),<sup>7</sup> as well as [Latin](../../language-terms/writing-systems-and-scripts/latin-script.md) and [Cyrillic](../../language-terms/writing-systems-and-scripts/cyrillic.md).<sup>8</sup> Each of these is a [script](../../language-terms/writing-systems-and-scripts/script.md), the set of [symbols](../../language-terms/writing-systems-and-scripts/symbol.md) and rules used to write one or more languages.

### Why it matters in design systems

Imagine making a reading book for children in your own language and finding that no single font has every symbol the language uses. Literacy teachers have faced exactly this. For years, many of them had to collect symbols from several fonts to get all the characters their language needs.<sup>9</sup> A page built that way mixes shapes from fonts that were never designed to sit together.

Andika, a font for people who are learning to read, was made to end that patchwork.<sup>10</sup> SIL makes many other fonts too, and many of them are for scripts that few other fonts serve.

This glossary does not list every SIL font. These are a few to explore; select a linked term to navigate to its glossary page.

| Font             | Script                                                                                                    | Made for                                                                                         |
| ---------------- | --------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Abyssinica SIL   | Ethiopic                                                                                                  | Every Ethiopic character in Unicode.<sup>11</sup>                                                |
| Andika           | Latin and Cyrillic                                                                                        | Materials for people who are learning to read.<sup>12</sup>                                      |
| Annapurna SIL    | Devanagari                                                                                                | The more than 225 languages written in Devanagari.<sup>13</sup>                                  |
| BJCree           | Canadian Aboriginal Syllabics                                                                             | Cree and Naskapi communities in Canada, in the style of syllabics they prefer.<sup>14</sup>      |
| Charis           | Latin and Cyrillic                                                                                        | The wide range of languages written in those two scripts.<sup>15</sup>                           |
| Gentium          | Latin, Cyrillic and [Greek](../../language-terms/writing-systems-and-scripts/greek-script.md)                                                           | Readable, high-quality publications by communities around the world.<sup>16</sup>                |
| Padauk           | Myanmar                                                                                                   | The writing systems that use the Myanmar script.<sup>17</sup>                                    |
| Scheherazade New | Arabic                                                                                                    | Languages written in Arabic script, including languages other than Arabic.<sup>18</sup>          |

Not every SIL font has "SIL" in its name. Abyssinica SIL does, and Padauk and Andika do not.<sup>19</sup>

Two things set these fonts apart. First, they hold the different glyphs that different communities use for the same symbol. Padauk includes the alternate forms that different language communities use for Myanmar,<sup>20</sup> and Abyssinica SIL includes the forms needed for two languages written in Ethiopic, Sebat Bet Gurage and Gumuz.<sup>21</sup> Second, they hold the symbols that a script's usual fonts leave out. Charis was made for the thousands of languages that use Latin script,<sup>22</sup> and many of them use letters with a hook added, a [diacritic](../../language-terms/writing-systems-and-scripts/diacritic.md) (a small [mark](../../language-terms/writing-systems-and-scripts/mark.md) above or below) or a shape turned upside down.<sup>23</sup>

SIL fonts are released under the SIL Open Font License (OFL),<sup>24</sup> a licence written for fonts.<sup>25</sup> A licence is permission to use font files under specific conditions.

| Question                                         | Answer                                                                                                                                 |
| ------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------- |
| Can we use the fonts in designs and on websites? | Yes, and the work does not need to credit the font.<sup>26</sup> Serving the font files to browsers is covered by the next row.         |
| Can we include the font files in our product?    | Yes, even in a product you sell, as long as each copy of the font comes with its copyright notice and the licence.<sup>27</sup>         |
| Can we change the font?                          | Yes, in any way.<sup>28</sup> If you share the changed font, it must stay under the OFL.<sup>29</sup>                                   |
| Can a changed font keep its name?                | Not if its makers reserved that name in the licence, unless they give written permission.<sup>30</sup>                                 |
| Is cutting a font down to a smaller file a change? | Yes. Removing any part of a font for a web page, even shapes nobody uses, counts as a change, so the naming rule applies.<sup>31</sup> |
| Can we sell the font on its own?                 | No.<sup>32</sup>                                                                                                                       |

The OFL is not only for SIL's fonts. The [Noto fonts](noto-fonts.md), a collection designed to cover all of Unicode, use it too,<sup>33</sup> and so do most of the font families (sets of fonts that share one design) on Google Fonts, a free font service from Google.<sup>34</sup> So a font under the OFL is not necessarily an SIL font. Because Noto and SIL fonts are free to use in the same ways, the choice between them comes down to the script and its readers. Noto aims for every script, and SIL's fonts were made around the needs of particular language communities, as the first table shows.

The fonts and the organization that makes them are two different things. SIL Global, previously called SIL International, is a faith-based nonprofit organization that works with language communities around the world.<sup>35</sup> Its staff propose new characters to [Unicode](../text-in-software/unicode.md), the standard that aims to give every [character](../text-in-software/character.md) its own number, when a local language needs them.<sup>36</sup> SIL Global is the Language Coding Agency for [ISO 639-3](../../language-terms/linguistics/iso-639-3.md). It receives and registers requests for new and changed codes.<sup>37</sup> ISO 639-3 is the set of three-letter codes for all known human [languages](../../language-terms/linguistics/language.md).<sup>38</sup> Its first list of codes went beyond an older, shorter ISO list, and the living languages it added came mainly from [Ethnologue](../../language-terms/linguistics/ethnologue.md), SIL's catalogue of the world's languages.<sup>39</sup>

This matters most when you choose a font for a language that your brand font has no glyphs for, because its [font coverage](font-coverage.md) stops short, and that Noto either does not cover or does not show in the form its readers use. SIL's catalogue groups its fonts by the region where they are most used,<sup>40</sup> so look there for the script you need. Add the font you choose to the product's list of [fallback fonts](fallback-font.md) for that script, and keep its licence file with the font files you ship. If you cut it down with [font subsetting](font-subsetting.md), check whether the smaller file needs a new name. Then ask people who read the language to check real text in it, because a font that holds every character can still show some of them in a form its readers do not use.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Canadian Aboriginal Syllabics script](../../language-terms/writing-systems-and-scripts/canadian-aboriginal-syllabics.md) · [Character](../text-in-software/character.md) · [Cyrillic script](../../language-terms/writing-systems-and-scripts/cyrillic.md) · [Devanagari script](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Diacritic](../../language-terms/writing-systems-and-scripts/diacritic.md) · [Ethiopic script](../../language-terms/writing-systems-and-scripts/ethiopic-script.md) · [Ethnologue](../../language-terms/linguistics/ethnologue.md) · [Fallback font](fallback-font.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Font subsetting](font-subsetting.md) · [Greek script](../../language-terms/writing-systems-and-scripts/greek-script.md) · [ISO 639-3](../../language-terms/linguistics/iso-639-3.md) · [Language](../../language-terms/linguistics/language.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Mark](../../language-terms/writing-systems-and-scripts/mark.md) · [Noto fonts](noto-fonts.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Symbol](../../language-terms/writing-systems-and-scripts/symbol.md) · [Unicode](../text-in-software/unicode.md) · [Unicode Standard](../text-in-software/unicode-standard.md) · [Reference sources](../../terms/reference-sources.md) · [Font terms](./)

### Further reading

* Code & specs: [SIL Open Font License, official text](https://openfontlicense.org/open-font-license-official-text/)
* Foundations: [Fonts (SIL Language Technology)](https://software.sil.org/fonts/)

### Sources

1. "SIL designs and maintains free, open-source fonts", and "specialized fonts for minority-language and complex scripts" - Fonts, SIL Language Technology [https://software.sil.org/fonts/](https://software.sil.org/fonts/)
2. "a file containing a collection of glyphs and related supporting information used to render text" - Glossary, Computers and Writing Systems (SIL, archived site) [https://scripts.sil.org/cms/scripts/page.php?id=glossary&site\_id=nrsi](https://scripts.sil.org/cms/scripts/page.php?id=glossary&site_id=nrsi)
3. "Abyssinica SIL is an Ethiopic font (often called Ge’ez) based on calligraphic traditions" - Abyssinica SIL, SIL Writing Systems Technology [https://software.sil.org/abyssinica/](https://software.sil.org/abyssinica/)
4. "Annapurna SIL supports a full range of the writing systems that use Devanagari" - Annapurna SIL, SIL Writing Systems Technology [https://software.sil.org/annapurna/](https://software.sil.org/annapurna/)
5. "This font is an OpenType-enabled font family that supports the Arabic script" - Scheherazade New, SIL Writing Systems Technology [https://software.sil.org/scheherazade/](https://software.sil.org/scheherazade/)
6. "More than 40 languages use Myanmar script for their writing system. Padauk fully supports all of these languages" - Padauk, SIL Writing Systems Technology [https://software.sil.org/padauk/](https://software.sil.org/padauk/)
7. "The BJCree font supports all of the characters in the Unified Canadian Aboriginal Syllabics blocks which are required by the “Algonquian” languages" - BJCree, SIL Writing Systems Technology [https://software.sil.org/bjcree/](https://software.sil.org/bjcree/)
8. "SIL's Writing Systems Technology team has created very comprehensive fonts for Latin, Cyrillic and Greek script character sets: Andika, Charis, Doulos SIL, Galatia SIL, and Gentium" - Fonts, SIL Language Technology [https://software.sil.org/fonts/](https://software.sil.org/fonts/)
9. "they have had to hunt for and then tediously assemble letters from a variety of fonts in order to get all of the characters they need for their particular language" - Andika, SIL Writing Systems Technology [https://software.sil.org/andika/](https://software.sil.org/andika/)
10. "The Andika literacy font addresses these and other issues with clear, simply designed letters" - Andika, SIL Writing Systems Technology [https://software.sil.org/andika/](https://software.sil.org/andika/)
11. "The font supports the complete range of Unicode characters for Ethiopic (Ge’ez)" - Abyssinica SIL, SIL Writing Systems Technology [https://software.sil.org/abyssinica/](https://software.sil.org/abyssinica/)
12. "Andika is a sans-serif font family designed and optimized especially for use as a literacy font. It supports a near-complete range of Unicode characters for the Latin and Cyrillic scripts" - Andika, SIL Writing Systems Technology [https://software.sil.org/andika/](https://software.sil.org/andika/)
13. "Annapurna SIL is a Devanagari font family with broad support for the 225+ languages that are written with this beautiful script" - Annapurna SIL, SIL Writing Systems Technology [https://software.sil.org/annapurna/](https://software.sil.org/annapurna/)
14. "The BJCree (Baie-James Cree) font is a Canadian Syllabics font in the style preferred by Cree and Naskapi communities of Canada" - BJCree, SIL Writing Systems Technology [https://software.sil.org/bjcree/](https://software.sil.org/bjcree/)
15. "Charis is a Unicode-based font family that supports the wide range of languages that use the Latin and Cyrillic scripts" - Charis, SIL Writing Systems Technology [https://software.sil.org/charis/](https://software.sil.org/charis/)
16. "A serif typeface family designed to enable the diverse ethnic groups around the world who use the Latin, Cyrillic and Greek scripts to produce readable, high-quality publications" - Fonts (entry for Gentium), SIL Language Technology [https://software.sil.org/fonts/](https://software.sil.org/fonts/)
17. "Padauk is a Unicode Myanmar font family with broad support for writing systems that use the Myanmar script" - Padauk, SIL Writing Systems Technology [https://software.sil.org/padauk/](https://software.sil.org/padauk/)
18. "its character inventory has been extended to cover the Unicode Arabic repertoire for non-Arabic languages" - Scheherazade New, SIL Writing Systems Technology [https://software.sil.org/scheherazade/](https://software.sil.org/scheherazade/)
19. The catalogue lists the fonts by these names: "Abyssinica SIL A font based on Ethiopic calligraphic traditions", "Padauk A fully capable Unicode 16.0 font supporting all the Myanmar script characters", and "Andika A sans serif Latin and Cyrillic script font designed especially for literacy use" - Fonts, SIL Language Technology [https://software.sil.org/fonts/](https://software.sil.org/fonts/)
20. "A wealth of alternate character forms used by different language communities are included in Padauk" - Padauk, SIL Writing Systems Technology [https://software.sil.org/padauk/](https://software.sil.org/padauk/)
21. "support for the variants required for the Sebat Bet Gurage \[sgw] and Gumuz \[guk] languages" - Abyssinica SIL, SIL Writing Systems Technology [https://software.sil.org/abyssinica/](https://software.sil.org/abyssinica/)
22. "Charis has sought to provide an extended Latin font for the thousands of languages that use Latin script" - Charis, SIL Writing Systems Technology [https://software.sil.org/charis/](https://software.sil.org/charis/)
23. "They might have a hook added to a letter’s stem, or a diacritic (accent mark) above or below the letter, or perhaps have been rotated 180°" - Charis, SIL Writing Systems Technology [https://software.sil.org/charis/](https://software.sil.org/charis/)
24. "This font software is free to use, modify and redistribute according to the terms of the SIL Open Font License" - Abyssinica SIL, SIL Writing Systems Technology [https://software.sil.org/abyssinica/](https://software.sil.org/abyssinica/)
25. "The widely used, community-approved, free, libre, and open source license specifically designed for fonts and related software" - SIL Open Font License home [https://openfontlicense.org/](https://openfontlicense.org/)
26. "you can use them for books, graphics, videos, websites, signage, objects, etc. - and you do not need to include the license, copyright, or any other acknowledgement" - Using OFL fonts, SIL Open Font License [https://openfontlicense.org/how-to-use-ofl-fonts/](https://openfontlicense.org/how-to-use-ofl-fonts/)
27. "Original or Modified Versions of the Font Software may be bundled, redistributed and/or sold with any software, provided that each copy contains the above copyright notice and this license" - SIL Open Font License, official text, Permission & Conditions [https://openfontlicense.org/open-font-license-official-text/](https://openfontlicense.org/open-font-license-official-text/)
28. "The OFL allows any types of modification" - Modifying and redistributing OFL fonts, SIL Open Font License [https://openfontlicense.org/how-to-modify-ofl-fonts/](https://openfontlicense.org/how-to-modify-ofl-fonts/)
29. "The Font Software, modified or unmodified, in part or in whole, must be distributed entirely under this license, and must not be distributed under any other license" - SIL Open Font License, official text, Permission & Conditions [https://openfontlicense.org/open-font-license-official-text/](https://openfontlicense.org/open-font-license-official-text/)
30. "No Modified Version of the Font Software may use the Reserved Font Name(s) unless explicit written permission is granted by the corresponding Copyright Holder" - SIL Open Font License, official text, Permission & Conditions [https://openfontlicense.org/open-font-license-official-text/](https://openfontlicense.org/open-font-license-official-text/)
31. "Removing any parts of the font when delivering a webfont to a browser, including unused glyphs and smart font code, is considered modification. This is permitted by the OFL but would not normally allow the use of RFNs" - OFL-FAQ, question 2.6, SIL Open Font License [https://openfontlicense.org/ofl-faq/](https://openfontlicense.org/ofl-faq/)
32. "Neither the Font Software nor any of its individual components, in Original or Modified Versions, may be sold by itself" - SIL Open Font License, official text, Permission & Conditions [https://openfontlicense.org/open-font-license-official-text/](https://openfontlicense.org/open-font-license-official-text/)
33. "The large-scope Noto font collection designed to cover all of Unicode is re-released and re-licensed under the OFL" - History, SIL Open Font License [https://openfontlicense.org/history/](https://openfontlicense.org/history/)
34. "The Google Fonts service has now published over 1500 font families, the vast majority commissioned and released under the OFL" - History, SIL Open Font License [https://openfontlicense.org/history/](https://openfontlicense.org/history/)
35. "SIL Global (previously SIL International) is a global, faith-based nonprofit that works with local communities around the world to develop language solutions" - About Language Technology, SIL Language Technology [https://software.sil.org/about/](https://software.sil.org/about/)
36. "The team regularly submits proposals to the Unicode Consortium when new characters are needed for local languages" - About Language Technology, SIL Language Technology [https://software.sil.org/about/](https://software.sil.org/about/)
37. "SIL Global functions as the Language Coding Agency for Set 3 of the ISO 639 language code standard", and "SIL is responsible for receiving and registering Change Requests", and "The ISO 639-3/LCA receives and reviews applications for requesting new language codes and for the change of existing ones" - About ISO 639-3, ISO 639-3 Language Coding Agency (SIL Global) [https://iso639-3.sil.org/about](https://iso639-3.sil.org/about)
38. "ISO 639-3 is a set of codes that defines three-letter identifiers for all known human languages" - About ISO 639-3, ISO 639-3 Language Coding Agency (SIL Global) [https://iso639-3.sil.org/about](https://iso639-3.sil.org/about)
39. "The large number of living languages in the initial inventory of ISO 639-3 beyond those already included in ISO 639-2 was derived primarily from Ethnologue (15th edition)" - About ISO 639-3, ISO 639-3 Language Coding Agency (SIL Global) [https://iso639-3.sil.org/about](https://iso639-3.sil.org/about)
40. "Fonts are grouped by the region where they're most used" - Fonts, SIL Language Technology [https://software.sil.org/fonts/](https://software.sil.org/fonts/)
