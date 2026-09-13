---
roles: [roles/publication/reader]
url_pattern: /
status: valid
---
# Home

Two ways into a corpus: a word, or a space. The page opens on a question, "What are you looking for?", and a search field that answers it as the reader types, because every word used anywhere in the documentation has a page, defined or not. The most cited pages stand next to it as shortcuts. Then the spaces, the [sources](../../objects/ingestion/source.md) the site is fed by, each with its freshness from the git history, and the pages changed last. A space that has not moved past the staleness threshold is named in an alert.

No dashboard, no maturity metric, no chart.

## Today

The page at `index.html` opens on the question and its explanation, then the search field drawn large, the same field as the one of the top bar: its live results appear under it in the flow of the page as the reader types, one link per match with its title, the query marked in it, its type or, for a word without a note, "Used in N documents, never defined", and its space; the number of matches is written in the field, the keyboard help "↑ ↓ browse · Enter open" and the link "See the N results" close the list, `↓` reaches the rows and `↑` the field again, and `Enter` opens the row in focus. Without JavaScript the field is a plain form that submits to the [search](search.md) page. "Most cited" offers the twelve most cited pages as chips: a note counts the links pointing at it, a keyword page its occurrences.

"Spaces — fed by your repositories" lists one row per source, the most cited first: an initials badge, the name, "N pages" or "N documents" when the notes of the space mostly stand for converted documents, and the date of its newest change worded relative to the build, "2 days ago"; the whole tree of the space, every folder open, folds behind the row, the same tree the [entity page](entity-page.md) shows on its left. Past five spaces, the others fold behind "N more spaces, less cited". A note says that the dates come from the history of the repositories, so they are always right. "Recently changed" lists the eight pages changed last, each with its space and its date, and under them one alert per dormant space, "A space has not moved for N days", naming the space and the threshold of the configuration, `staleness.warn_after_days`, 180 days without the key. The letters of the alphabetical index live on the index page, reached from the top bar, and the to-do link with its count in the footer. No dashboard, no metric, no chart.

## Objects

- Reads: [model](../../objects/inference/model.md)

## Actions

1. Search → [search](search.md)
2. Browse the index → [alphabetical index](alphabetical-index.md)
3. Open a file → [entity page](entity-page.md)
4. See what is missing → [to-do page](todo-page.md)

## Rules

- [Stale source](../../rules/sources/stale-source.rule.md)
