---
aliases: [spaces page, all spaces]
roles: [roles/publication/reader]
url_pattern: /spaces
status: valid
---
# Spaces

The second way into a corpus, after a word: a space, one per [source](../../objects/ingestion/source.md) the site is fed by. The page lists every space, none folded, and completes the first five of the [home](home.md). A row leads to the page of the space, never unfolds a tree.

## Today

The page at `spaces/index.html` is titled "Spaces" and opens on the sentence "N spaces, fed by the repositories declared in the configuration. A repository may carry several spaces, and a space may spread over several repositories." Then one table, in the order of the home page, the most cited first, with the columns SPACE, CONTENT, PAGES and LAST UPDATE: the initials badge and the title of the space, `sources[].title` in the configuration or its name without one, linking to its page; what it holds, the sentence `sources[].description` declares in the configuration or, without it, the labels of the dominant types of the space ("Business rule, Decision, Screen"); its page count; and the date of its newest change from the git history, worded relative to the build ("2 days ago"). A space past the staleness threshold, `staleness.warn_after_days` (180 days without the key), shows its date in the accent colour, doubled by its value in days ("193 days ago"): the only place where a colour carries an alert. The note under the table says so: "The dates come from the git history, so they are always exact. A space past the freshness threshold — 180 days by default — is marked in accent, the only case where colour carries an alert, doubled by the value in days."

The "Spaces" link of the top bar and the "SPACES" entry of the drawer lead here; on a phone the table gives up its content column and its heading row, each row reading the badge and the title, then the count and the date. A dormant space also reads, after its date and for assistive technology alone, "past the freshness threshold", so that the alert never rests on the colour.

Left open: the length of space labels. The title of a space is written by the configuration and stands in the bar, the drawer, the breadcrumb and this table; a long one is cut with an ellipsis in the bar and the breadcrumb today, and whether the configuration should bound it, or the pages abbreviate it by the initials badge alone under a width, is to be decided once a corpus carries such a title.

## Objects

- Reads: [model](../../objects/inference/model.md), [source](../../objects/ingestion/source.md)

## Actions

1. Open a space → [space](space.md)

## Rules

- [Stale source](../../rules/sources/stale-source.rule.md)
