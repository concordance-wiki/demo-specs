---
aliases: [todo, to-do list]
roles: [roles/ingestion/author, roles/quality/quality-owner]
url_pattern: /todo
status: valid
---
# To-do page

Three lists, nothing else: documents without a markdown representation, words above the threshold without a note, and, folded, the suspected noise the confidence set aside. Each entry of the first two leads to the page concerned and states its occurrence or file count; the lists are sorted by decreasing count, then by identifier. This is not a health report; the linter in continuous integration plays that role.

## Today

The page at `todo/index.html` shows three lists and nothing else. The first names the documents without a markdown representation, the entities the `W-DOC-NOMD` findings point at, each with its number of files without a note; the second names the keyword pages, each with its occurrences and the files they spread over, the first hundred in view and the others behind a disclosure worded "Show the N others", served in the HTML without a script. Every entry of both leads to the page concerned; both lists go by decreasing count, then by identifier. The third, folded under the heading "Suspected noise" with its count, lists the candidate expressions at the publication threshold whose word confidence stayed under `inference.keyword_pages.min_confidence`: best score first, each with its occurrences, its files and its reason in the language of the site, "in 68% of the files, 1.2 per file, verb or adverb form", none linked since none has a page nor a mark in the text, all still found by the search; a call to add them to the project's stopwords closes the section, leading to `project.contribute_url` when the project declares one. No other finding reaches the page: a broken link, a stale source or an ambiguous relation stays with the linter. The header of every page and the home page link to it with the total of the first two lists.

## Objects

- Reads: [finding](../../objects/quality/finding.md), [resource](../../objects/ingestion/resource.md)

## Actions

1. Open a document → [entity page](entity-page.md)
2. Open a word → [keyword page](keyword-page.md)

## Rules

- [Document without markdown](../../rules/documents/document-without-markdown.rule.md)
- [Undefined term](../../rules/vocabulary/undefined-term.rule.md)
