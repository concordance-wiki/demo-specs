---
aliases: [search results, results page]
roles: [roles/reader]
url_pattern: /search
status: valid
---
# Search

Full-text search over the whole corpus, without a server. The index is generated at build and loaded in fragments as the user types. Facets on type, source, domain and application carry counts frozen at build; they combine, and a facet with no result is disabled rather than hidden. The query and the active filters live in the URL, so a search can be sent to a colleague and replays exactly.

Expressions without a note appear among the results with a dotted outline and their occurrence count; a "no note" facet isolates or excludes them.

## Today

The field sits in the header of every page. Press `/` anywhere to reach it, `Escape` to leave it. From two characters on, the best eight results appear under the field with their title, their type badge and the application and domain the entity is filed under; `Enter` opens the results page at `search/index.html?q=…`, which lists every result of the query in its address and follows the field as it changes. A query matches by prefix (`key` finds "Keyword page", `checks` and `check` find the same note), every word must match, and there is no typo correction. The title weighs 5, an alias 4, the summary 2, the body, type, application, domain, status and source 1 each; the score of a result sums the weights of the fields each word matched, ties keeping the order of the model. The body of a note enters the index up to `build.extracted_text_max_chars` characters.

The index is written at build under `search/`: an entity table and one shard per two-character prefix, each a classic script the page loads by injecting a script tag, so that the search works when the site is opened from the disk as it does behind a server (see [Purpose-built search index](../decisions/purpose-built-search-index.md)). The page loads the table when the field takes focus and one shard per word typed, once. Without JavaScript, the field is a plain form that submits to the results page.

The results page narrows the list with four facets, type, source, domain and application, drawn under the summary with the count of every value. The values come from the entity table and the counts are computed in the browser over the results of the current query, each facet under the filters of the others, so that nothing is fetched beyond the shards of the words typed. Facets combine by intersection; two values of the same facet keep the entities carrying either. A value nothing would come of stays listed at 0, disabled rather than hidden. The selected values are recalled above the results with a link that lifts each one and a link that clears them all. Without a query, the page lists every entity of the site under the facets, with the counts of the whole table. The summary reads "218 results" in the site language and never a time: nothing is timed in a static site.

The state of a search is its address, `search/index.html?q=versement&type=term&source=specs&nonote=exclude`: the query under `q`, the selected values of every facet under its name, comma-separated. A facet followed pushes an entry to the history, typing rewrites the current entry once the reader pauses for 300 ms, and the back and forward buttons replay the state of the address, field, facets and list included. Opening an address restores the query, the filters and the scroll position, remembered per address in the session storage of the browser. The address is written under the summary so that the state is explicit, with a "Copy" button where the browser exposes a clipboard, which most refuse over `file://`.

The words without a note appear among the results in a row outlined in dots that states, under the title, that no note defines the expression and how many occurrences and files it has, "17 occurrences · 6 documents", from the counts of the [keyword page](keyword-page.md). A fifth facet, "Without a note", keeps them among the results, keeps them alone or leaves them out, as `nonote=only` or `nonote=exclude` in the address. A keyword page never comes before an entity of the same score: at equal relevance the entities go first, then the keyword pages, each in the order of the model.

## Objects

- Reads: [model](../objects/model.md), [entity](../objects/entity.md)

## Actions

1. Open a result → [entity page](entity-page.md)
2. Open a noteless result → [keyword page](keyword-page.md)

## Rules

- [Undefined term](../rules/undefined-term.md)
