---
aliases: [todo, to-do list]
roles: [roles/author, roles/quality-owner]
url_pattern: /todo
status: valid
---
# To-do page

Two lists, nothing else: documents without a markdown representation, and words above the threshold without a note. Each entry leads to the page concerned and states its occurrence or file count. Lists are sorted by decreasing count, then by identifier. This is not a health report; the linter in continuous integration plays that role.

## Today

The page at `todo/index.html` shows two lists and nothing else. The first names the documents without a markdown representation, the entities the `W-DOC-NOMD` findings point at, each with its number of files without a note; the second names the keyword pages, each with its occurrences and the files they spread over. Every entry leads to the page concerned; both lists go by decreasing count, then by identifier. No other finding reaches the page: a broken link, a stale source or an ambiguous relation stays with the linter. The header of every page and the home page link to it with the total of both lists.

## Objects

- Reads: [finding](../objects/finding.md), [resource](../objects/resource.md)

## Actions

1. Open a document → [entity page](entity-page.md)
2. Open a word → [keyword page](keyword-page.md)

## Rules

- [Document without markdown](../rules/document-without-markdown.md)
- [Undefined term](../rules/undefined-term.md)
