---
aliases: [index, letter index]
roles: [roles/publication/reader, roles/inference/glossary-owner]
url_pattern: /index
status: valid
---
# Alphabetical index

Every word the documentation uses, with or without a definition, by initial letter. Letters without an entry stay in view, struck through and inert. Each word is listed with its type, the first line of its page and the number of pages citing it; a word without a definition is dotted and described by the passage that uses it most. Sorting follows the collation rules of the project locale, accents included, and the words without a definition are never set apart: they are the working list of a [glossary owner](../../roles/inference/glossary-owner.md).

## Today

The index at `index/index.html` lists every entity and keyword page of the model in the order of the language pack of the project locale, accents and case set aside and digits compared by value, so that `étude` files between `estimate` and `event`; two titles that collate alike follow their identifiers. The page is titled "A–Z index" and opens on the sentence "N words used in the documentation. N have a written page, the others exist through their uses alone."; beside it the "Filters" button folds a menu of links to the [search results](search.md) page filtered by type, by space or to the words without a definition, so that the filters work without any script. A bar of letters follows: a letter without an entry is struck through and carries no link, an active letter leads to its place, titles that open with a digit or a symbol gather under `#`, and the line "N letters without an entry" closes the bar. Every letter of the page is headed "A — 94 words" and its entries form a table of four columns: the word, its type from the profile, the first line of its page (the summary of the note, cut at a word before 200 characters) and the number of pages citing it, the pages linking to a note or the files an expression is read in. A word without a definition sits among the others, its title dotted, "no definition" in the type column and, in place of a first line, the earliest passage of the file that uses it most, quoted and followed by the title of that file; the note under the table says that those words are the working list of a glossary owner. When the whole index rendered as one page would weigh more than 100 kB, every letter with entries gets its own page, `index/a/index.html` to `index/other/index.html`, the index address shows the first of them, and every letter page links to its siblings, each under the page budget.

## Objects

- Reads: [model](../../objects/inference/model.md)

## Actions

1. Open a word → [entity page](entity-page.md)
2. Open a noteless word → [keyword page](keyword-page.md)
