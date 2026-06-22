---
term: Writing system
slug: writing-system
aliases: []
tags: [writing-systems-scripts]
level: foundational
depth: deep
summary: "A writing system is a script applied to a specific language together with the orthographic rules for using it; the script is the sign set, the writing system is that set put to work for one language."
related: [language, script, orthography, latin-script]
status: voice-passed
version_added: 0.1
updated: 2026-06-22
contributors: [sam-gordashko]
further_reading:
  - title: "Writing system (Wikipedia)"
    url: https://en.wikipedia.org/wiki/Writing_system
    type: authority
license: CC-BY-4.0
---

# Writing system

## Definition
A writing system is a script applied to a specific language together with the orthographic rules for using it; the script is the sign set, the writing system is that set put to work for one language.

## Why it matters
This is the rung between [language](language.md) and [script](script.md). A script is a set of signs, the [Latin script](latin-script.md) is just the letters, available to anyone. A writing system is what you get when one language adopts that script and settles how to use it: which letters, what spelling and capitalization, which punctuation, how words are separated. The English writing system and the Vietnamese writing system both use the Latin script, but they are different writing systems because each adds its own [orthography](orthography.md). Keeping this distinct from "script" is practical, not pedantic: font coverage and shaping are properties of the script, while spelling, casing, hyphenation, and punctuation rules are properties of the writing system, and a product that supports the script still has to get the writing system's rules right.

## Example
English and Turkish are two writing systems built on the same Latin script: Turkish adds the dotless "ı" and the dotted "İ" and capitalizes them as a matched pair, a rule the English writing system does not have.

## Common mistake
Using "writing system" and "script" as synonyms. They are different levels: many writing systems can share one script, and (less often) one language's writing can draw on more than one script. Collapsing them hides the language-specific rules, the casing, spelling, and punctuation, that live in the writing system rather than in the script.

## In practice
- **Separate script-level from writing-system-level support:** verify [font coverage](font-coverage.md) and shaping at the script level, but localize casing, hyphenation, quotation marks, and number formatting at the writing-system level. The two are different work and different data.
- **Drive writing-system rules from the language, not the script:** the same Latin letters behave differently across languages, so tie orthographic behavior to a [locale](locale.md), not to the script alone.

## Related terms
[Language](language.md) · [Script](script.md) · [Orthography](orthography.md) · [Latin script](latin-script.md)

## Further reading
- Foundations: [Writing system (Wikipedia)](https://en.wikipedia.org/wiki/Writing_system)

<!-- NEEDS EXPERT REVIEW: source is Wikipedia (interim). Upgrade to an authoritative primary (Unicode Standard, ScriptSource) vetted by the SILCON cohort. The Turkish dotted/dotless-i casing example is well known but should be confirmed. This entry is promoted out of being an alias of `script`; see the matching note in orthography.md and the updated aliases on script.md. -->
