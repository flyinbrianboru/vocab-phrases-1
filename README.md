# Foclóir IRS139

Ulster Irish vocabulary and phrases from IRS139 class notes, as a browsable, searchable
study site with flashcards, a quiz and grammar notes.

**295 entries** across eleven categories, each with a translation and — where there's
something worth knowing — a note on the grammar, the dialect form, the etymology or the
story behind it.

## What's in it

| Tab | What it does |
|---|---|
| **Foclóir** | Search and filter all entries. Search covers Irish, English and the notes, and ignores accents (`fearr` finds `fearr`, `aireamh` finds `áireamh`). Star anything to build your own list. |
| **Cártaí** | Flashcards. Pick a deck (all, to-learn, starred, or any category) and a direction. Space flips, `1`/`2` or ←/→ mark again / got it. Two correct passes marks an entry as known. |
| **Tráth na gCeist** | Multiple choice, 10–30 questions, either direction. Distractors are drawn from the same category so they're not giveaways. The note appears as the explanation after each answer, and misses are listed at the end. |
| **Nótaí** | The longer grammar write-ups: the three degrees of comparison, DAFTA, the `a` of totality, verbs of motion, the preposition table for feelings, word families, the compass logic, a history timeline, an Ulster/Caighdeán table, the two conjugations, `má` vs `dá`, and written vs spoken forms. |

Progress and starred items are saved in the browser's local storage, so they persist
between visits on the same device. **Athshocraigh** clears them.

## Running it

It's a static site with no build step and no dependencies.

- **Locally:** open `index.html` in a browser.
- **GitHub Pages:** push these files to a repo, then Settings → Pages → Deploy from a
  branch → `main` / root. The site appears at `https://<user>.github.io/<repo>/`.

## Adding a week's vocabulary

Everything lives in `vocab.js`. Add objects to the end of the `VOCAB` array:

```js
{ ga:"an focal nua", en:"the new word", cat:"focail",
  note:"Why it works this way. <b>Bold</b> and <i>italic</i> are allowed.",
  see:["a related headword"] },
```

| Field | |
|---|---|
| `ga` | Irish — required, and must be unique |
| `en` | English — required |
| `cat` | one of the keys in `CATS` at the top of the file — required |
| `note` | optional; simple HTML is fine |
| `see` | optional array of other entries' `ga` values; renders as clickable chips |
| `noq` | optional `true` to keep long phrases out of the quiz |

The counts, filters, decks and quiz all rebuild themselves from the array — nothing else
needs touching. To add a category, add a key to `CATS`.

## Note on accuracy

Translations follow the class sheet. Grammar explanations and background notes were added
as a study aid, and a few places where the sheet looks to have a slip are flagged in the
note itself (for example the Plantation of Ulster being 17th century, not 19th). Anything
marked uncertain is worth checking with the lecturer.

## Files

```
index.html   the whole app — markup, styles, logic
vocab.js     the data
README.md    this file
```
