---
aliases: [category list, list of a category]
roles: [roles/publication/reader]
url_pattern: /{source}/{folder}
status: valid
---
# Category

The list of one category of a [space](space.md): a folder at the top of the repository, where a card of the space page or a folder of the tree leads. A category does not unfold in the tree, it opens as a page, the missing link between the space and the note.

## Today

The page stands at `<source>/<folder>/index.html`, the address a note of that identifier would take, and yields to such a note. The search field of the top bar reads "Search in <category>" and submits with the space and, when every note of the folder got the same type from the [source](../../objects/ingestion/source.md), a rule, a suffix or the default, that type set as facets of the [search](search.md). The tree of the space stands on the left, as on the [entity page](entity-page.md), with the folders at the top and their counts, this one marked as the current page, the others leading to their lists. The breadcrumb reads "Spaces › name › Category".

The title is the folder name, capitalised. Under it, the notes are counted as the type words it, "64 screens described.", followed by the sentence the profile keeps for the type, "A screen is a page of the application, with what it shows and what it allows."; a folder whose notes have several types reads "64 pages." alone. Two selectors follow: the first attribute the type highlights, "Roles ▾", whose values filter the list and whose first entry, "All", lifts the filter, and the sort, "A–Z ▾", by title or by links. The table has fixed columns, the type of the folder or "Page" (the title, linked), the highlighted attribute (its values, linked when they name a page), "First line" (the summary of the note) and "Links" (the number of related pages, the one-hop neighbours of the [model](../../objects/inference/model.md)); no score. The line under it reads "8 screens of 64 — pagination by twenty." with the page links, then the note "The Links column counts the related pages, which brings the most central screens of the journey to the top." The list opens by title, never by links, so that it does not change with every build.

The selectors are links to pages rendered at build under `<source>/<folder>/-/` (`-/links/`, `-/roles-reader/`, `-/page-2/`) while the two sorts times the values of the attribute give twelve pages at most; beyond, the page carries every row and an island applies the sort and the filter in place, the served page reading by title without JavaScript, the selectors appearing once the island runs.

## Objects

- Reads: [model](../../objects/inference/model.md), [source](../../objects/ingestion/source.md), [entity](../../objects/inference/entity.md)

## Actions

1. Search in the category → [search](search.md)
2. Open a note → [entity page](entity-page.md)
3. Open a value of the attribute → [entity page](entity-page.md)
4. Filter or sort the list → [category](category.md)
5. Back to the space → [space](space.md)

## Rules

- [Invalid identifier](../../rules/identifiers/invalid-identifier.rule.md)
