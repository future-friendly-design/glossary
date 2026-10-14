---
term: SIL fonts
slug: sil
aliases:
  - SIL
  - SIL Global fonts
  - Charis SIL
  - Gentium
  - Andika
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

SIL fonts are a kind of [font](font.md), the file that holds the shapes software uses to show text.<sup>2</sup> They range from fonts for [scripts](../../language-terms/writing-systems-and-scripts/script.md) that many languages share, such as [Latin](../../language-terms/writing-systems-and-scripts/latin-script.md) and [Cyrillic](../../language-terms/writing-systems-and-scripts/cyrillic.md), to fonts made for the scripts of minority-language communities.<sup>3</sup> A script is the set of symbols and rules used to write one or more languages. Not every SIL font has "SIL" in its name: Charis and Gentium do not, and Doulos SIL does.<sup>4</sup>

The fonts and the organization that makes them are two different things. SIL Global, previously called SIL International, is a faith-based nonprofit organization that works with language communities around the world.<sup>5</sup> Fonts are one part of its work. Its staff also propose new characters to [Unicode](../text-in-software/unicode.md), the standard that gives every [character](../text-in-software/character.md) its own number, when a local language needs them.<sup>6</sup> SIL Global is also the official registration agency for [ISO 639-3](../../language-terms/linguistics/iso-639-3.md), a role its ISO 639-3 site calls the Language Coding Agency.<sup>7</sup> ISO 639-3 is the set of three-letter codes for all known human [languages](../../language-terms/linguistics/language.md).<sup>8</sup> Its first list of codes was built partly from [Ethnologue](../../language-terms/linguistics/ethnologue.md), SIL's catalogue of the world's languages.<sup>9</sup>

### Why it matters in design systems

Imagine making a reading book for children in your own language and finding that no single font has every letter the language uses. Literacy teachers have faced exactly this. For years, many of them had to collect letters from several fonts to get all the characters their language needs.<sup>10</sup> A page built that way mixes shapes from fonts that were never designed to sit together.

SIL's fonts were made to end that patchwork, one script at a time, and many of them are for scripts other than Latin.

This glossary does not list every SIL font. These are a few to explore; select a linked term to navigate to its glossary page.

| Font             | Script                                                                                                    | Made for                                                                                         |
| ---------------- | --------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Abyssinica SIL   | [Ethiopic](../../language-terms/writing-systems-and-scripts/ethiopic-script.md)                           | Every Ethiopic character in Unicode.<sup>11</sup>                                                |
| Andika           | Latin and Cyrillic                                                                                        | Materials for people who are learning to read.<sup>12</sup>                                      |
| Annapurna SIL    | [Devanagari](../../language-terms/writing-systems-and-scripts/devanagari.md)                              | The more than 225 languages written in Devanagari.<sup>13</sup>                                  |
| BJCree           | [Canadian Aboriginal Syllabics](../../language-terms/writing-systems-and-scripts/canadian-aboriginal-syllabics.md) | Cree and Naskapi communities in Canada, in the style of syllabics they prefer.<sup>14</sup> |
| Charis           | Latin and Cyrillic                                                                                        | The wide range of languages written in those two scripts.<sup>15</sup>                           |
| Gentium          | Latin, Cyrillic and [Greek](../../language-terms/writing-systems-and-scripts/greek-script.md)             | Readable, high-quality publications by communities around the world.<sup>16</sup>                |
| Padauk           | Myanmar                                                                                                   | The writing systems that use the Myanmar script.<sup>17</sup>                                    |
| Scheherazade New | [Arabic](../../language-terms/writing-systems-and-scripts/arabic-script.md)                               | Languages written in Arabic script, including languages other than Arabic.<sup>18</sup>          |

Two things set these fonts apart. First, they hold the letters that a script's usual fonts leave out. Charis was made for the thousands of languages that use Latin script,<sup>19</sup> and many of them use letters with a hook added, a [diacritic](../../language-terms/writing-systems-and-scripts/diacritic.md) (a small [mark](../../language-terms/writing-systems-and-scripts/mark.md) above or below) or a shape turned upside down.<sup>20</sup> Second, they hold the different shapes that different communities use for the same [symbol](../../language-terms/writing-systems-and-scripts/symbol.md). Padauk includes the alternate forms that different language communities use for Myanmar,<sup>21</sup> and Abyssinica SIL includes the forms needed for two languages written in Ethiopic, Sebat Bet Gurage and Gumuz.<sup>22</sup>

SIL fonts are released under the SIL Open Font License (OFL),<sup>23</sup> a licence written for fonts.<sup>24</sup> A licence is the permission that says what you may do with a font file. The table answers the questions a design system most often has.

| Question                                         | Answer                                                                                                                                 |
| ------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------- |
| Can we use the fonts in designs and on websites? | Yes, and the work does not need to credit the font.<sup>25</sup>                                                                       |
| Can we include the font files in our product?    | Yes, even in a product you sell, as long as each copy of the font comes with its copyright notice and the licence.<sup>26</sup>         |
| Can we change the font?                          | Yes, in any way.<sup>27</sup>                                                                                                          |
| Can a changed font keep its name?                | Not if its makers reserved that name in the licence, unless they give written permission.<sup>28</sup>                                 |
| Is cutting a font down to a smaller file a change? | Yes. Removing any part of a font for a web page, even shapes nobody uses, counts as a change, so the naming rule applies.<sup>29</sup> |
| Can we sell the font on its own?                 | No.<sup>30</sup>                                                                                                                       |

The OFL is not only for SIL's fonts. The [Noto fonts](noto-fonts.md), a collection designed to cover all of Unicode, use it too,<sup>31</sup> and so do most of the font families (sets of fonts that share one design) on Google Fonts, a free font service from Google.<sup>32</sup> So a font under the OFL is not necessarily an SIL font. Because Noto and SIL fonts are free to use in the same ways, the choice between them comes down to the script and its readers: Noto aims for every script, and SIL's fonts were made around the needs of particular language communities, as the first table shows.

This matters most when you choose a font for a language that your brand font has no shapes for, because its [font coverage](font-coverage.md) stops short, and that Noto either does not cover or does not show in the form its readers use. SIL's catalogue groups its fonts by the region where they are most used,<sup>33</sup> so look there for the script you need. Add the font you choose to the product's list of [fallback fonts](fallback-font.md) for that script, and keep its licence file with the font files you ship. If you cut it down with [font subsetting](font-subsetting.md), check whether the smaller file needs a new name. Then ask people who read the language to check real text in it, because a font that holds every character can still show some of them in a form its readers do not use.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Canadian Aboriginal Syllabics script](../../language-terms/writing-systems-and-scripts/canadian-aboriginal-syllabics.md) · [Character](../text-in-software/character.md) · [Cyrillic script](../../language-terms/writing-systems-and-scripts/cyrillic.md) · [Devanagari script](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Diacritic](../../language-terms/writing-systems-and-scripts/diacritic.md) · [Ethiopic script](../../language-terms/writing-systems-and-scripts/ethiopic-script.md) · [Ethnologue](../../language-terms/linguistics/ethnologue.md) · [Fallback font](fallback-font.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Font subsetting](font-subsetting.md) · [Greek script](../../language-terms/writing-systems-and-scripts/greek-script.md) · [ISO 639-3](../../language-terms/linguistics/iso-639-3.md) · [Language](../../language-terms/linguistics/language.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Mark](../../language-terms/writing-systems-and-scripts/mark.md) · [Noto fonts](noto-fonts.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Symbol](../../language-terms/writing-systems-and-scripts/symbol.md) · [Unicode](../text-in-software/unicode.md) · [Unicode Standard](../text-in-software/unicode-standard.md) · [Reference sources](../../terms/reference-sources.md) · [Font terms](./)

### Further reading

* Code & specs: [SIL Open Font License, official text](https://openfontlicense.org/open-font-license-official-text/)
* Foundations: [Fonts (SIL Language Technology)](https://software.sil.org/fonts/)

### Sources

1. "SIL designs and maintains free, open-source fonts that support the full range of scripts and writing systems used around the world" - Fonts, SIL Language Technology [https://software.sil.org/fonts/](https://software.sil.org/fonts/)
2. "a file containing a collection of glyphs and related supporting information used to render text" - Glossary, Computers and Writing Systems (SIL, archived site) [https://scripts.sil.org/cms/scripts/page.php?id=glossary&site\_id=nrsi](https://scripts.sil.org/cms/scripts/page.php?id=glossary&site_id=nrsi)
3. "specialized fonts for minority-language and complex scripts" - Fonts, SIL Language Technology [https://software.sil.org/fonts/](https://software.sil.org/fonts/)
4. "SIL's Writing Systems Technology team has created very comprehensive fonts for Latin, Cyrillic and Greek script character sets: Andika, Charis, Doulos SIL, Galatia SIL, and Gentium" - Fonts, SIL Language Technology [https://software.sil.org/fonts/](https://software.sil.org/fonts/)
5. "SIL Global (previously SIL International) is a global, faith-based nonprofit that works with local communities around the world to develop language solutions" - About Language Technology, SIL Language Technology [https://software.sil.org/about/](https://software.sil.org/about/)
6. "The team regularly submits proposals to the Unicode Consortium when new characters are needed for local languages" - About Language Technology, SIL Language Technology [https://software.sil.org/about/](https://software.sil.org/about/)
7. "SIL Global functions as the Language Coding Agency for Set 3 of the ISO 639 language code standard" - About ISO 639-3, ISO 639-3 Language Coding Agency (SIL Global) [https://iso639-3.sil.org/about](https://iso639-3.sil.org/about)
8. "ISO 639-3 is a set of codes that defines three-letter identifiers for all known human languages" - About ISO 639-3, ISO 639-3 Language Coding Agency (SIL Global) [https://iso639-3.sil.org/about](https://iso639-3.sil.org/about)
9. "based on a harmonization of ISO 639-2 with the code set of SIL’s Ethnologue 15th edition" - ISO 639-3 home, ISO 639-3 Language Coding Agency (SIL Global) [https://iso639-3.sil.org/](https://iso639-3.sil.org/)
10. "they have had to hunt for and then tediously assemble letters from a variety of fonts in order to get all of the characters they need for their particular language" - Andika, SIL Writing Systems Technology [https://software.sil.org/andika/](https://software.sil.org/andika/)
11. "The font supports the complete range of Unicode characters for Ethiopic (Ge’ez)" - Abyssinica SIL, SIL Writing Systems Technology [https://software.sil.org/abyssinica/](https://software.sil.org/abyssinica/)
12. "Andika is a sans-serif font family designed and optimized especially for use as a literacy font. It supports a near-complete range of Unicode characters for the Latin and Cyrillic scripts" - Andika, SIL Writing Systems Technology [https://software.sil.org/andika/](https://software.sil.org/andika/)
13. "Annapurna SIL is a Devanagari font family with broad support for the 225+ languages that are written with this beautiful script" - Annapurna SIL, SIL Writing Systems Technology [https://software.sil.org/annapurna/](https://software.sil.org/annapurna/)
14. "The BJCree (Baie-James Cree) font is a Canadian Syllabics font in the style preferred by Cree and Naskapi communities of Canada" - BJCree, SIL Writing Systems Technology [https://software.sil.org/bjcree/](https://software.sil.org/bjcree/)
15. "Charis is a Unicode-based font family that supports the wide range of languages that use the Latin and Cyrillic scripts" - Charis, SIL Writing Systems Technology [https://software.sil.org/charis/](https://software.sil.org/charis/)
16. "A serif typeface family designed to enable the diverse ethnic groups around the world who use the Latin, Cyrillic and Greek scripts to produce readable, high-quality publications" - Fonts (entry for Gentium), SIL Language Technology [https://software.sil.org/fonts/](https://software.sil.org/fonts/)
17. "Padauk is a Unicode Myanmar font family with broad support for writing systems that use the Myanmar script" - Padauk, SIL Writing Systems Technology [https://software.sil.org/padauk/](https://software.sil.org/padauk/)
18. "its character inventory has been extended to cover the Unicode Arabic repertoire for non-Arabic languages" - Scheherazade New, SIL Writing Systems Technology [https://software.sil.org/scheherazade/](https://software.sil.org/scheherazade/)
19. "Charis has sought to provide an extended Latin font for the thousands of languages that use Latin script" - Charis, SIL Writing Systems Technology [https://software.sil.org/charis/](https://software.sil.org/charis/)
20. "They might have a hook added to a letter’s stem, or a diacritic (accent mark) above or below the letter, or perhaps have been rotated 180°" - Charis, SIL Writing Systems Technology [https://software.sil.org/charis/](https://software.sil.org/charis/)
21. "A wealth of alternate character forms used by different language communities are included in Padauk" - Padauk, SIL Writing Systems Technology [https://software.sil.org/padauk/](https://software.sil.org/padauk/)
22. "support for the variants required for the Sebat Bet Gurage \[sgw] and Gumuz \[guk] languages" - Abyssinica SIL, SIL Writing Systems Technology [https://software.sil.org/abyssinica/](https://software.sil.org/abyssinica/)
23. "This font software is free to use, modify and redistribute according to the terms of the SIL Open Font License" - Abyssinica SIL, SIL Writing Systems Technology [https://software.sil.org/abyssinica/](https://software.sil.org/abyssinica/)
24. "The widely used, community-approved, free, libre, and open source license specifically designed for fonts and related software" - SIL Open Font License home [https://openfontlicense.org/](https://openfontlicense.org/)
25. "you can use them for books, graphics, videos, websites, signage, objects, etc. - and you do not need to include the license, copyright, or any other acknowledgement" - Using OFL fonts, SIL Open Font License [https://openfontlicense.org/how-to-use-ofl-fonts/](https://openfontlicense.org/how-to-use-ofl-fonts/)
26. "Original or Modified Versions of the Font Software may be bundled, redistributed and/or sold with any software, provided that each copy contains the above copyright notice and this license" - SIL Open Font License, official text, Permission & Conditions [https://openfontlicense.org/open-font-license-official-text/](https://openfontlicense.org/open-font-license-official-text/)
27. "The OFL allows any types of modification" - Modifying and redistributing OFL fonts, SIL Open Font License [https://openfontlicense.org/how-to-modify-ofl-fonts/](https://openfontlicense.org/how-to-modify-ofl-fonts/)
28. "No Modified Version of the Font Software may use the Reserved Font Name(s) unless explicit written permission is granted by the corresponding Copyright Holder" - SIL Open Font License, official text, Permission & Conditions [https://openfontlicense.org/open-font-license-official-text/](https://openfontlicense.org/open-font-license-official-text/)
29. "Removing any parts of the font when delivering a webfont to a browser, including unused glyphs and smart font code, is considered modification. This is permitted by the OFL but would not normally allow the use of RFNs" - OFL-FAQ, question 2.6, SIL Open Font License [https://openfontlicense.org/ofl-faq/](https://openfontlicense.org/ofl-faq/)
30. "Neither the Font Software nor any of its individual components, in Original or Modified Versions, may be sold by itself" - SIL Open Font License, official text, Permission & Conditions [https://openfontlicense.org/open-font-license-official-text/](https://openfontlicense.org/open-font-license-official-text/)
31. "The large-scope Noto font collection designed to cover all of Unicode is re-released and re-licensed under the OFL" - History, SIL Open Font License [https://openfontlicense.org/history/](https://openfontlicense.org/history/)
32. "The Google Fonts service has now published over 1500 font families, the vast majority commissioned and released under the OFL" - History, SIL Open Font License [https://openfontlicense.org/history/](https://openfontlicense.org/history/)
33. "Fonts are grouped by the region where they're most used" - Fonts, SIL Language Technology [https://software.sil.org/fonts/](https://software.sil.org/fonts/)
