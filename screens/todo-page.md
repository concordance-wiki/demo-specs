---
roles: [writer]
url_pattern: /todo
status: valid
---
# To-do page

Two lists, nothing else: documents without a markdown representation, and words above the threshold without a note. Each entry leads to the page concerned and states its occurrence or file count. Lists are sorted by decreasing count, then by identifier. This is not a health report; the linter in continuous integration plays that role.

## Today

The page at `todo/index.html` lists the keyword pages of the model, most occurrences first, and the entities the `W-DOC-NOMD` findings name with their finding count. The header of every page links to it with the total of both lists.

## Objects

- Reads: [finding](../objects/finding.md), [resource](../objects/resource.md)

## Actions

1. Open a document → [entity page](entity-page.md)
2. Open a word → [keyword page](keyword-page.md)

## Rules

- [Document without markdown](../rules/document-without-markdown.md)
- [Undefined term](../rules/undefined-term.md)
