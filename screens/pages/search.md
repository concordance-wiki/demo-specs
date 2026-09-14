---
aliases: [search results, results page]
roles: [roles/publication/reader]
url_pattern: /search
status: valid
calls: [api/operations/search-model, api/operations/list-entities]
---
# Search

Full-text search over the whole corpus, without a server. The index is generated at build and loaded in fragments as the user types. Facets on type, source, domain and application carry counts frozen at build; they combine, and a facet with no result is disabled rather than hidden. The query and the active filters live in the URL, so a search can be sent to a colleague and replays exactly.

Expressions without a note appear among the results with a dotted outline and their occurrence count; a "no note" facet isolates or excludes them.

## Today

The field sits in the header of every page. Press `/` anywhere to reach it, `Escape` to leave it. From two characters on, the best eight results appear under the field, each with its title and a detail line, the type and the first line of a note, the citations of a glossary term or the documents of a word without a note; `Enter` opens the results page at `search/index.html?q=…`, which lists every result of the query in its address and follows the field as it changes. The field shows the query with a ✕ that clears it, shown in place of the `/` hint while the field holds something. A query matches by prefix (`key` finds "Keyword page", `checks` and `check` find the same note), every word must match, and there is no typo correction. The title weighs 5, an alias 4, the summary 2, the body, type, application, domain, status and source 1 each; the score of a result sums the weights of the fields each word matched; among results of the same score the most cited comes first, the pages citing an entity being the distinct sources of the links pointing at it, then the order of the model. The body of a note enters the index up to `build.extracted_text_max_chars` characters.

The index is written at build under `search/`: an entity table and one shard per two-character prefix, each a classic script the page loads by injecting a script tag, so that the search works when the site is opened from the disk as it does behind a server (see [Purpose-built search index](../../decisions/publication/purpose-built-search-index.md)). The page loads the table when the field takes focus and one shard per word typed, once. Without JavaScript, the field is a plain form that submits to the results page.

The results page is laid out like a catalogue; its heading "Search" is kept for assistive technology alone, the query in the field naming the page. The left column, as tall as the page, on the surface colour and ruled on its right, holds the facets as checkbox groups with the count of every value: "Page type" and "Space" (the type and the source) open, "Domain", "Application" and "Without a note" folded under them, the keyword type labelled "Without a definition", listed last among the types and drawn with a dashed box, and at the foot of the column the note that the counters are set when the site is published and that the filtering happens in the browser, without a round trip; on a phone the column folds behind a "Filters" heading above the results. The values come from the entity table and the counts are computed in the browser over the results of the current query, each facet under the filters of the others, so that nothing is fetched beyond the shards of the words typed. Facets combine by intersection; two values of the same facet keep the entities carrying either. A value nothing would come of stays listed at 0, its box disabled rather than hidden. The selected values are recalled above the results as chips, each with a ✕ that lifts it, next to a link that clears them all and the summary, "218 results, most cited first", in the site language and never a time: nothing is timed in a static site. Without a query, the page lists every entity of the site under the facets, the most cited first, with the counts of the whole table.

The first result is an expanded card: the type as a chip, the title, "cited in 64 pages", the whole summary (the first paragraph of the note cut at two hundred characters when it declares none), then the line of its space, its other names ("Also called: word page") and its broader term ("Broader term: Link") when the note declares them, the broader term named by the title of its page when the reference resolves. The following results are condensed on one line each: the chip, the title, the bare count of citing pages and the summary cut to the row; a page nothing cites shows no count at all. Twenty rows are drawn, then a button "Show the next 20" adds the next batch without leaving the page; the summary keeps counting them all. When nothing matches, the page names the query and, when the query has words, proposes the closest form of the dictionary, the title or alias sharing the longest prefix with the query, the shortest among equals, with its citations or its occurrences, as a link to the search on that form under the same filters.

The state of a search is its address, `search/index.html?q=threshold&type=term&source=specs&nonote=exclude`: the query under `q`, the selected values of every facet under its name, comma-separated. A facet followed pushes an entry to the history, typing rewrites the current entry once the reader pauses for 300 ms, and the back and forward buttons replay the state of the address, field, facets and list included. Opening an address restores the query, the filters and the scroll position, remembered per address in the session storage of the browser. Nothing on the page repeats the address: the one in the bar of the browser is the state, and can be sent as it is.

The words without a note appear among the results in a dashed card with a dashed chip reading "Without a definition" and a dotted title, followed on the same line by "Used in 6 documents, never defined in the glossary", from the counts of the [keyword page](keyword-page.md); a note under the list says that the words used but not defined appear with the others, dotted, which is how a gap of the glossary shows. A fifth facet, "Without a note", keeps them among the results, keeps them alone or leaves them out, as `nonote=only` or `nonote=exclude` in the address. A keyword page never comes before an entity of the same score: at equal relevance the entities go first, then the keyword pages, each in the order of the model.

## Objects

- Reads: [model](../../objects/inference/model.md), [entity](../../objects/inference/entity.md)

## Actions

1. Open a result → [entity page](entity-page.md)
2. Open a noteless result → [keyword page](keyword-page.md)

## Rules

- [Undefined term](../../rules/vocabulary/undefined-term.rule.md)
