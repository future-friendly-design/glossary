---
term: Sign language
slug: sign-language
aliases: [signed language]
level: foundational
depth: deep
summary: "A sign language is a natural language that uses the visual-manual mode, conveying meaning through manual articulation such as handshape, movement, and location combined with facial expression rather than through sound."
related:
  - language
  - iso-639-3
  - endangered-language
  - localization
  - locale
status: voice-passed
version_added: 0.1
updated: 2026-08-03
contributors:
  - sam-gordashko
further_reading:
  - title: Sign language (Wikipedia)
    url: https://en.wikipedia.org/wiki/Sign_language
    type: authority
license: CC-BY-4.0
tags:
  - language-linguistics
---

# Sign language

## Definition

A sign language is a natural language that uses the visual-manual mode, conveying meaning through manual articulation such as handshape, movement, and location combined with facial expression rather than through sound.<sup>1</sup> Like spoken languages, sign languages are full-fledged natural languages with their own grammar and lexicon,<sup>2</sup> not a spoken language expressed in signs and not invented by hearing people.<sup>3</sup> Nor are they an intuitive system of gestures or mime: like spoken words, most signs are conventional and often arbitrary, without a necessary visual link to what they mean.<sup>4</sup> They are also not universal, and each is its own language, distinct from whatever spoken language happens to surround it.<sup>5</sup>

### Why it matters in design systems

The common misconception is that there is one universal sign language, or that captioning a video in the surrounding spoken language gives a Deaf audience access to it. Neither holds. Because a sign language is a distinct natural language, usually with no written form, the localization playbook built for spoken languages, translate the strings, pick a [font](../../programming-terms/text-for-digital-products-and-the-web/font.md), set the [text direction](../writing-systems-and-scripts/text-direction.md), does not apply: there is no text to localize. Support for a sign language lives in video: signed video content, captioning treated as a separate deliverable, and emerging avatar or animation approaches. This shapes representation too. A language picker or [locale](../../programming-terms/text-for-digital-products-and-the-web/locale.md) model that lists only spoken languages quietly tells signers their language is not supported, even though stable identifiers for many sign languages exist, for example in [ISO 639-3](iso-639-3.md). Naming and specifics belong to the Deaf communities who use each language, with capital-D Deaf marking a cultural identity rather than an audiological status.

### Example

American Sign Language (ASL) and British Sign Language (BSL) are quite different and mutually unintelligible, even though the hearing people of the United States and the United Kingdom share the same spoken language.<sup>6</sup> ASL, BSL, and French Sign Language (LSF) are each their own language, so "sign language" in the singular is as imprecise as "spoken language" would be. And because sign languages do not have a traditional or formal written form,<sup>7</sup> supporting one is a matter of recording and presenting video, not of translating and rendering strings of text.

### Common mistake

Treating captions in the spoken language as sign-language access. Captions render the surrounding spoken or written language, which for many Deaf people is a second language learned after their sign language, so captions are an accommodation in that spoken language, not a substitute for content in the sign language itself. If your audience includes a signing community, plan for signed video alongside captions, and do not count either one as delivering the other.

### In practice

* **Support sign languages with video, not text fields:** because most have no written form, there are no strings to translate, so budget for signed video, captioning as its own track, and, where it fits, avatar or animation rather than a [localization](../../programming-terms/text-for-digital-products-and-the-web/localization.md) string table.
* **Keep captions and signed content as separate deliverables:** caption for the spoken language and provide signed video for the sign language; conflating the two leaves signers with access to neither in their own language.
* **Represent sign languages honestly in your language model:** stable codes exist to tag them, for example [ISO 639-3](iso-639-3.md), so a picker can name a sign language rather than omit it; defer the naming and the specifics to the Deaf communities who use it.

***

### Related terms and mentions

[Endangered language](endangered-language.md) · [Font](../../programming-terms/text-for-digital-products-and-the-web/font.md) · [ISO 639-3](iso-639-3.md) · [Language](language.md) · [Locale](../../programming-terms/text-for-digital-products-and-the-web/locale.md) · [Localization](../../programming-terms/text-for-digital-products-and-the-web/localization.md) · [Text direction](../writing-systems-and-scripts/text-direction.md) · [Writing system](../writing-systems-and-scripts/writing-system.md) · [Language & linguistics](./)

### Further reading

* Foundations: [Sign language (Wikipedia)](https://en.wikipedia.org/wiki/Sign_language)

### Sources

1. "Sign languages (also known as signed languages) are languages that use the visual-manual modality to convey meaning rather than spoken words." [Sign language (Wikipedia)](https://en.wikipedia.org/wiki/Sign_language)
2. "They are expressed through manual articulation in combination with non-manual markers, and are full-fledged natural languages with their own grammar and lexicon." [Sign language (Wikipedia)](https://en.wikipedia.org/wiki/Sign_language)
3. "There is a common misconception that sign languages are spoken language expressed in signs, or that they were invented by hearing people." [Sign language (Wikipedia)](https://en.wikipedia.org/wiki/Sign_language)
4. Sign languages are "not mime"; their signs are "conventional, often arbitrary and do not necessarily have a visual relationship to their referent." [Sign language (Wikipedia)](https://en.wikipedia.org/wiki/Sign_language)
5. "Sign languages are not universal and are usually not mutually intelligible, although there are similarities among different sign languages." [Sign language (Wikipedia)](https://en.wikipedia.org/wiki/Sign_language)
6. "British Sign Language (BSL) and American Sign Language (ASL) are quite different and mutually unintelligible, even though the hearing people of the United Kingdom and the United States share the same spoken language." [Sign language (Wikipedia)](https://en.wikipedia.org/wiki/Sign_language)
7. "Sign languages do not have a traditional or formal written form." [Sign language (Wikipedia)](https://en.wikipedia.org/wiki/Sign_language)
