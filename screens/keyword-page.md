---
roles: [reader]
url_pattern: /keywords/{word}
status: valid
---
# Keyword page

The page of a word nobody defined. Same template as the [entity page](entity-page.md), without the markdown and the declared properties. A banner says that no note exists and how many passages were recorded. Three numbers only: occurrences, files, sources. The passages follow, grouped by file in corpus order, with their context. Accompanying words are sized by co-occurrence, and expressions with a similar form are offered as a lead, worded to assert nothing.

A keyword page exists from three occurrences in at least two files. If a note is created later, the page keeps its address and fills in.

## Objects

- Reads: [entity](../objects/entity.md), [model](../objects/model.md)

## Actions

1. Open a passage's file → [entity page](entity-page.md)
2. Open an accompanying word → [keyword page](keyword-page.md)

## Rules

- [Undefined term](../rules/undefined-term.md)
