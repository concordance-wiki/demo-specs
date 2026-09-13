---
roles: [reader]
url_pattern: /search
status: valid
---
# Search

Full-text search over the whole corpus, without a server. The index is generated at build and loaded in fragments as the user types. Facets on type, source, domain and application carry counts frozen at build; they combine, and a facet with no result is disabled rather than hidden. The query and the active filters live in the URL, so a search can be sent to a colleague and replays exactly.

Expressions without a note appear among the results with a dotted outline and their occurrence count; a "no note" facet isolates or excludes them.

## Today

The field sits in the header of every page. Press `/` anywhere to reach it, `Escape` to leave it. From two characters on, the best eight results appear under the field with their title, their type badge and the application and domain the entity is filed under; `Enter` opens the results page at `search/index.html?q=…`, which lists every result of the query in its address and follows the field as it changes. A query matches by prefix (`key` finds "Keyword page", `checks` and `check` find the same note), every word must match, and there is no typo correction. The title weighs 5, an alias 4, the summary 2, the body, type, application, domain, status and source 1 each; the score of a result sums the weights of the fields each word matched, ties keeping the order of the model. The body of a note enters the index up to `build.extracted_text_max_chars` characters.

The index is written at build under `search/`: an entity table and one shard per two-character prefix, each a classic script the page loads by injecting a script tag, so that the search works when the site is opened from the disk as it does behind a server (see [Purpose-built search index](../decisions/purpose-built-search-index.md)). The page loads the table when the field takes focus and one shard per word typed, once. Facets, the search state in the URL and the noteless words with their outline come next; without JavaScript, the field is a plain form that submits to the results page.

## Objects

- Reads: [model](../objects/model.md), [entity](../objects/entity.md)

## Actions

1. Open a result → [entity page](entity-page.md)
2. Open a noteless result → [keyword page](keyword-page.md)

## Rules

- [Undefined term](../rules/undefined-term.md)
