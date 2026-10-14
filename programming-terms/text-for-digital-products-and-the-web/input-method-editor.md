---
term: Input method editor (IME)
slug: input-method-editor
aliases:
  - IME
level: intermediate
depth: deep
summary: An input method editor (IME) is software that turns what a person types into the characters they mean, usually by offering a list of choices to pick from.
related:
  - keyboard-layout
  - internationalization
  - segmentation
status: voice-passed
version_added: 0.1
updated: 2026-10-14
contributors:
  - sam-gordashko
further_reading:
  - title: Input method editor (MDN)
    url: https://developer.mozilla.org/en-US/docs/Glossary/Input_method_editor
    type: code
  - title: UI Events (W3C)
    url: https://www.w3.org/TR/uievents/
    type: authority
license: CC-BY-4.0
tags:
  - i18n-engineering
---

# Input method editor (IME)

## Definition

An input method editor (IME) is software that turns what a person types into the characters they mean, usually by offering a list of choices to pick from.<sup>1</sup>

Input method editors are one of the things [internationalization (i18n)](internationalization.md) has to plan for. Internationalization is the design and development work that makes a product able to be adapted to other languages and places.<sup>2</sup>

People use one to type Chinese, Japanese, or Korean on a keyboard of Latin letters, and in several other situations where the keys in front of them do not match the text they want to write.<sup>3</sup>

### Why it matters in design systems

When you type English on a laptop, each key press puts one finished letter into the text field. It is easy to design every text field as if typing always worked that way. With an input method editor it does not. The person presses a few keys, watches a first attempt appear in the field, steps through suggestions until the right one shows, and only then confirms it.

Here is a person typing the Japanese word for city, which is pronounced "shi":

| What the person does | What the text field shows |
| -------------------- | ------------------------- |
| Presses `s` | s |
| Presses `i` | し, the [hiragana](../../language-terms/writing-systems-and-scripts/hiragana.md) symbol for the sound "shi" |
| Presses the convert key, which can be the space bar | 詩, a character that means poem and is also pronounced "shi" |
| Presses the convert key again | 市, the character that means city |
| Presses the accept key, which can be Enter | 市, now part of the text |

Five key presses made one character, and the field showed four different things on the way.<sup>4</sup> The two characters sound the same, so the software cannot know which one is meant. Only the person can choose.<sup>5</sup>

This whole stretch, from the first key to the confirmation, is called a composition. Software is told when a composition starts, each time it changes, and when it ends.<sup>6</sup> It can end with the text accepted, or with the person cancelling it.<sup>7</sup>

Chinese and Japanese are the well-known cases, but composition is not limited to them. Writing by hand on a touch screen works this way, and so does typing words on a number pad.<sup>8</sup> So do the word suggestions on a phone keyboard.<sup>9</sup> Even an accent can be a short composition: on a keyboard with a key that adds an accent to the next letter, pressing `^` and then `e` to get `ê` counts as one.<sup>10</sup>

An input method editor is not a [keyboard layout](keyboard-layout.md). A layout is a set of fixed rules, so the same keys always give the same character. An IME is a second way in, built for characters that the keys do not offer,<sup>11</sup> and it works by asking the person to choose. A product has to work with both.

### Common mistake

Treating every key press as finished text. A search box that searches on each key press runs a search for `s`, then for し, then for 詩, all before the person has reached 市. A character counter counts symbols that are about to be replaced. A form that checks its input while it is typed shows an error for a word that is only half made. And a message field that sends when Enter is pressed sends too early, because Enter is also a key people press to accept a suggestion.<sup>12</sup> None of this shows up when the product is tested by typing English on a laptop, which is how it reaches the people who type this way every day.

### In practice

The fix is the same in every case: let the composition finish before the product reacts.

* **Wait for the end of the composition.** Searching, counting, checking, and sending can all wait until the person has confirmed the text. Write that into the specification of every text field. It is possible to build: on the web, the browser announces the start of a composition with an event named `compositionstart`,<sup>13</sup> and the end with one named `compositionend`, and any key press can be asked whether it happened in between.<sup>14</sup>
* **Design around the suggestion window.** The IME opens its own window of suggestions,<sup>15</sup> and that window is not part of your design. Check what your own dropdowns, tooltips, and error messages do while it is open, because they are likely to want the same space next to the text.
* **Test by typing with a real IME.** Add a Japanese or Chinese input method in the settings of the operating system, then type into every field: search, tags, chat, and anything with a length limit. You do not need to read the language to see a search fire too early or a message send itself.

***

### Related terms and mentions

[Character](../text-in-software/character.md) · [CJK](../../language-terms/writing-systems-and-scripts/cjk.md) · [Han characters script](../../language-terms/writing-systems-and-scripts/han-characters.md) · [Hiragana script](../../language-terms/writing-systems-and-scripts/hiragana.md) · [Internationalization (i18n)](internationalization.md) · [Keyboard layout](keyboard-layout.md) · [Language](../../language-terms/linguistics/language.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Segmentation](../text-in-software/segmentation.md) · [Symbol](../../language-terms/writing-systems-and-scripts/symbol.md) · [Internationalization & localization terms](../internationalization-and-localization/)

### Further reading

* Code & specs: [Input method editor (MDN)](https://developer.mozilla.org/en-US/docs/Glossary/Input_method_editor)
* Foundations: [UI Events (W3C)](https://www.w3.org/TR/uievents/)

### Sources

1. "An input method editor (IME), also known as a front end processor, is an application that performs the conversion between keystrokes and ideographs or other characters, usually by user-guided dictionary lookup" - UI Events, W3C Working Draft, Glossary [https://www.w3.org/TR/uievents/](https://www.w3.org/TR/uievents/)
2. "Designing and developing in a way that removes barriers to localization or international deployment" - Localization vs. Internationalization, W3C Internationalization [https://www.w3.org/International/questions/qa-i18n](https://www.w3.org/International/questions/qa-i18n)
3. "Input method editors are used in many situations: To enter Chinese, Japanese, or Korean text using a Latin keyboard" - MDN Web Docs Glossary: Input method editor [https://developer.mozilla.org/en-US/docs/Glossary/Input_method_editor](https://developer.mozilla.org/en-US/docs/Glossary/Input_method_editor)
4. "The following example describes a possible sequence of keys to generate the Unicode character "市" (Kanji character, part of CJK Unified Ideographs) using Japanese input methods", followed by a table of the key presses and of the text shown after each - UI Events, W3C Working Draft, section 4.3.3 Input Method Editors [https://www.w3.org/TR/uievents/](https://www.w3.org/TR/uievents/)
5. ""詩" (poem) and "市" (city) are homophones, both pronounced し (shi/si), so the user needs to use the Convert key to select the proper option" - UI Events, W3C Working Draft, section 4.3.3 Input Method Editors [https://www.w3.org/TR/uievents/](https://www.w3.org/TR/uievents/)
6. "a composition session consists of one compositionstart event, one or more compositionupdate events, and one compositionend event" - UI Events, W3C Working Draft, section 3.6 Composition Events [https://www.w3.org/TR/uievents/](https://www.w3.org/TR/uievents/)
7. "The compositionend event is fired when a text composition system such as an input method editor completes or cancels the current composition session" - MDN Web Docs, Element: compositionend event [https://developer.mozilla.org/en-US/docs/Web/API/Element/compositionend_event](https://developer.mozilla.org/en-US/docs/Web/API/Element/compositionend_event)
8. "To enter Latin text using a numeric keypad. To enter text on a touch screen using handwriting recognition" - MDN Web Docs Glossary: Input method editor [https://developer.mozilla.org/en-US/docs/Glossary/Input_method_editor](https://developer.mozilla.org/en-US/docs/Glossary/Input_method_editor)
9. "An IME MAY also be used for dictionary-based word completion, such as on mobile devices" - UI Events, W3C Working Draft, Glossary [https://www.w3.org/TR/uievents/](https://www.w3.org/TR/uievents/)
10. isComposing is "true if this event is dispatched during a dead key sequence or while an input method editor is active (such that composition events are being dispatched)" - UI Events, W3C Working Draft, section 3.4.3 Input Event Types [https://www.w3.org/TR/uievents/](https://www.w3.org/TR/uievents/)
11. "Composition Events provide a means for inputing text in a supplementary or alternate manner than by Keyboard Events, in order to allow the use of characters that might not be commonly available on keyboard" - UI Events, W3C Working Draft, section 3.6 Composition Events [https://www.w3.org/TR/uievents/](https://www.w3.org/TR/uievents/)
12. "The keys Convert and Accept MAY be replaced by others depending on the input device in use and the configuration of the IME, e.g., it can be respectively U+0020 (Space key) and Enter" - UI Events, W3C Working Draft, section 4.3.3 Input Method Editors [https://www.w3.org/TR/uievents/](https://www.w3.org/TR/uievents/)
13. "The compositionstart event is fired when a text composition system such as an input method editor starts a new composition session" - MDN Web Docs, Element: compositionstart event [https://developer.mozilla.org/en-US/docs/Web/API/Element/compositionstart_event](https://developer.mozilla.org/en-US/docs/Web/API/Element/compositionstart_event)
14. "returns a boolean value indicating if the event is fired within a composition session, i.e., after compositionstart and before compositionend" - MDN Web Docs, KeyboardEvent: isComposing property [https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/isComposing](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/isComposing)
15. Default action of the compositionstart event: "Show a text composition system candidate window" - UI Events, W3C Working Draft, section 3.1 List of Event Types [https://www.w3.org/TR/uievents/](https://www.w3.org/TR/uievents/)
