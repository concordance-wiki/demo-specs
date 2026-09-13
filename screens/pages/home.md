---
roles: [roles/publication/reader]
url_pattern: /
status: valid
---
# Home

Two ways into a corpus: a word, or a space. The page opens on a question, "What are you looking for?", and a search field that answers it as the reader types, because every word used anywhere in the documentation has a page, defined or not. The most cited pages stand next to it as shortcuts. Then the spaces, the [sources](../../objects/ingestion/source.md) the site is fed by, each with its freshness from the git history, and the pages changed last. A space that has not moved past the staleness threshold is named in an alert.

No dashboard, no maturity metric, no chart.

## Today

The page at `index.html` opens on the question and its explanation, then the search field drawn large, the same field as the one of the top bar: its live results appear under it in the flow of the page as the reader types, one link per match with its title, the query marked in it, a detail line ("Type — first line" for a note, "Glossary term — cited in N pages" for a note of a glossary source, "Used in N documents, never defined" for a word without a note) and its space, two rows of the same title told apart by their space or their folder after the title, the first row standing on the soft colour; the number of matches is written in the field, the keyboard help "↑ ↓ browse · Enter open" and the link "See the N results" close the list, `↓` reaches the rows and `↑` the field again, and `Enter` opens the row in focus. Without JavaScript the field is a plain form that submits to the [search](search.md) page. "Most cited" offers the five most cited pages as chips on one line, one chip per title, the most cited of two namesakes standing for both: a note counts the links pointing at it, a keyword page its occurrences.

"Spaces — fed by your repositories" lists one row per source, the most cited first: an initials badge, the name, "N pages" or "N documents" when the notes of the space mostly stand for converted documents, and the date of its newest change worded relative to the build, "2 days ago"; the row leads to the page of the [space](space.md), never unfolds a tree. Past five spaces, the others fold behind "N more spaces, less cited"; the [spaces](spaces.md) page lists them all. A note says that the dates come from the history of the repositories, so they are always right. "Recently changed" lists the four pages changed last, each with its space and its date, and under them one alert per dormant space, "A space has not moved for N days", naming the space and the threshold of the configuration, `staleness.warn_after_days`, 180 days without the key. The letters of the alphabetical index live on the index page, reached from the top bar, and the to-do link with its count in the footer. No dashboard, no metric, no chart.

## Objects

- Reads: [model](../../objects/inference/model.md)

## Actions

1. Search → [search](search.md)
2. Open a space → [space](space.md)
3. Browse the index → [alphabetical index](alphabetical-index.md)
4. Open a file → [entity page](entity-page.md)
5. See what is missing → [to-do page](todo-page.md)

## Rules

- [Stale source](../../rules/sources/stale-source.rule.md)
