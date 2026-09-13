---
roles: [roles/publication/reader]
url_pattern: /
status: valid
---
# Home

Three ways into a corpus, of equal standing: the file tree, the alphabetical index of words, and freshness. A prominent search field comes first, with the most cited words as shortcuts. The header states the number of sources, files and the date of the last build. The freshness entry shows the latest changes with their git date and flags dormant sources.

No dashboard, no maturity metric, no chart.

## Today

The page at `index.html` states the project name from `theme.yaml` or the configuration, the number of sources and files of the build and its date spelled in the project locale. A search region comes next, empty until the search index exists, with the twelve most cited pages as shortcuts: a note counts the links pointing at it, a keyword page its occurrences. Three entry points follow, of equal standing: the file tree, one folding block per source, open, with its folders closed and its notes as links; the letters of the alphabetical index with their counts; the twenty latest changes with their git date, and under them every source with the date of its newest change, flagged dormant when that change is older than `staleness.warn_after_days`, 180 days without the key. A last line leads to the to-do page with its count. No dashboard, no metric, no chart.

## Objects

- Reads: [model](../../objects/inference/model.md)

## Actions

1. Search → [search](search.md)
2. Browse the index → [alphabetical index](alphabetical-index.md)
3. Open a file → [entity page](entity-page.md)
4. See what is missing → [to-do page](todo-page.md)

## Rules

- [Stale source](../../rules/sources/stale-source.rule.md)
