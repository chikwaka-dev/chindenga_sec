# Offline Learning Template

`offline-learning-template.html` is a one-file interactive book for learners who work **offline**.
Copy it, change the content, and share it by USB, SD card, Bluetooth, WhatsApp or a school hotspot.
It needs no internet, accounts, fonts or downloads.

## What learners get

| Feature | Why it matters offline |
|---|---|
| **Who's learning?** | Several learners can share one phone or lab PC. Each one keeps their own progress. |
| **Learn**: one step at a time | Short lesson cards with a progress bar. Works well on small screens. |
| **Practice**: stars, no scores | Learners try again until they get it right: 3 stars on the first try, 2 on the second, 1 after that. Hints appear after a wrong answer, and the answer can be shown after 3 tries. There are no percentages or failing grades. |
| **Missions** | Real-life tasks (interview an elder, visit a site) with a notes box. No device or data needed. |
| **Language switch** | Every text can have English, chiShona and isiNdebele versions. Missing translations fall back to English. |
| **Send my progress** | Creates a short message with a code. Learners copy it offline and send it on WhatsApp, SMS or email later. |
| **Teacher corner** | The teacher pastes learners' messages and gets a class table. Nothing leaves the device. |
| **Print this topic** | A paper worksheet (lessons, questions with answer lines, missions, answer key) for learners without devices. |
| **Draft / reviewed badge** | Each topic shows whether a teacher has checked it yet. |
| Safe saving | If the browser blocks saving (private mode, some in-app viewers), the book still works and shows a warning. |

## Making a new book

1. Copy the file and rename it, e.g. `geography-form3.html`.
2. Open it in a text editor and search for **`EDIT FROM HERE`**.
3. Change `COURSE`:
   - `id`: a **unique** short name per book (e.g. `geog-f3`). Progress is saved under this name, so two books must never share one.
   - `school`, `author`, `title`, `subtitle`, `languages`.
   - `topics`: each has `steps` (lessons), `practice` (questions) and `missions`.
   - `glossary`.
4. Open the file in a browser to check it. When a teacher has reviewed a topic, set `reviewed: true`.

### Any text can be one language or several

```js
title: 'Identity'                                   // English only
title: { en: 'Identity', sn: 'Kuzivikanwa', nd: '...' }   // with translations
```

### Question types

```js
{ type: 'mcq',  q: {en:'...'}, options: [{en:'A'}, {en:'B'}], answer: 0, hint: {en:'...'}, explain: {en:'...'} }
{ type: 'tf',   q: {en:'...'}, answer: false, hint: {...}, explain: {...} }
{ type: 'fill', q: {en:'Friends of the same age are ______.'}, answer: ['peers', 'peer group'], hint: {...} }
```

`answer` for `mcq` is the position of the right option, counting from **0**.
`fill` accepts any of the listed answers and ignores capital letters and punctuation.

Lesson `body` text can use simple HTML: `<p>`, `<b>`, `<ul><li>`, and two highlight boxes:
`<div class="example">...</div>` and `<div class="think">...</div>`.

### Interface words

Button labels live in the `UI` object just below `COURSE`. The Shona and Ndebele interface words are a
starting point and **should be checked by a fluent speaker**. Any missing word falls back to English.

## Before sharing a book

- [ ] A subject teacher has reviewed each topic (set `reviewed: true`)
- [ ] A fluent speaker has checked the translations
- [ ] Tested on an old Android phone's built-in browser
- [ ] Tested opening from WhatsApp's file viewer
- [ ] Printed one topic to check the worksheet
- [ ] Tried with a small group of learners and noted what confused them
