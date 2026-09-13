---
roles: [reader]
url_pattern: /
status: valid
---
# Home

Three ways into a corpus, of equal standing: the file tree, the alphabetical index of words, and freshness. A prominent search field comes first, with the most cited words as shortcuts. The header states the number of sources, files and the date of the last build. The freshness entry shows the latest changes with their git date and flags dormant sources.

No dashboard, no maturity metric, no chart.

## Today

The page at `index.html` shows the project name from `theme.yaml` or the configuration, the five most cited entities as shortcuts, the number of sources and files of the build and its date, and three entry points that count the entities by domain, by type and by application, each item leading to the alphabetical index. The search field waits for the search index; the file tree and the freshness entries wait for their own pages.

## Objects

- Reads: [model](../objects/model.md)

## Actions

1. Search → [search](search.md)
2. Browse the index → [alphabetical index](alphabetical-index.md)
3. Open a file → [entity page](entity-page.md)
4. See what is missing → [to-do page](todo-page.md)

## Rules

- [Stale source](../rules/stale-source.md)
