---
roles: [reader]
url_pattern: /search
status: valid
---
# Search

Full-text search over the whole corpus, without a server. The index is generated at build and loaded in fragments as the user types. Facets on type, source, domain and application carry counts frozen at build; they combine, and a facet with no result is disabled rather than hidden. The query and the active filters live in the URL, so a search can be sent to a colleague and replays exactly.

Expressions without a note appear among the results with a dotted outline and their occurrence count; a "no note" facet isolates or excludes them.

## Objects

- Reads: [model](../objects/model.md), [entity](../objects/entity.md)

## Actions

1. Open a result → [entity page](entity-page.md)
2. Open a noteless result → [keyword page](keyword-page.md)

## Rules

- [Undefined term](../rules/undefined-term.md)
