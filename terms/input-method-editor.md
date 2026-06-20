---
term: Input method editor (IME)
slug: input-method-editor
aliases: [IME]
tags: [i18n-engineering]
level: intermediate
depth: deep
summary: An input method editor is software that lets users type characters that are not directly available on their keyboard, such as Chinese or Japanese.
related: [keyboard-layout, internationalization, segmentation]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Input method editor (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Glossary/Input_method_editor
    type: code
license: CC-BY-4.0
---

## Definition
An input method editor is software that lets users type characters that are not directly available on their keyboard, such as Chinese or Japanese.

## Why it matters
An IME converts sequences of keystrokes into characters from scripts that have far more symbols than there are keys. Users typically type a phonetic or romanized form and pick from candidate characters the IME offers. IMEs are essential for East Asian languages and also power emoji pickers, handwriting input, and predictive text. For anyone building text inputs, the part that matters is that typing is a multi-step composition, not one key per character.

## Example
Typing "nihao" in pinyin and the IME suggesting the Chinese characters for "hello".

## Common mistake
Running per-keystroke logic (validation, live search, autocomplete, submit-on-Enter) on every keypress while the user is mid-composition. During IME composition the field holds intermediate text, so reacting to each key corrupts the input, fires premature submits, or fights the candidate window. It is a classic bug for CJK users that English-only testing never surfaces.

## In practice
- **Respect composition events:** on the web, listen for `compositionstart` and `compositionend` and hold keystroke-driven logic until composition finishes, instead of reacting to every `keydown` or `input`. See [Input method editor (MDN)](https://developer.mozilla.org/en-US/docs/Glossary/Input_method_editor).
- **Test with a real IME:** include CJK input in QA for any search box, tag field, or inline editor, because the bug only appears with an active IME.
- **One keystroke is not one character:** counting, validating, or truncating mid-composition needs the same grapheme and [[segmentation]] awareness as the rest of text handling.

## Related terms
[[keyboard-layout]] · [[internationalization]] · [[segmentation]]

## Further reading
- Code & specs: [Input method editor (MDN)](https://developer.mozilla.org/en-US/docs/Glossary/Input_method_editor)
