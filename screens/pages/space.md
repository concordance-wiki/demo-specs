---
aliases: [space page, page of a space]
roles: [roles/publication/reader]
url_pattern: /{source}
status: valid
---
# Space

The page of one [source](../../objects/ingestion/source.md), where a row of the [home](home.md) or of the [spaces](spaces.md) page leads: one changes page, nothing unfolds. A space reads like a small wiki within the wiki: its own search, its own vocabulary, its own news.

## Today

The page stands at `<source>/index.html`, where no note can stand since an identifier has two segments at least. The search field of the top bar reads "Search in this space" and submits with the space set as the source facet of the [search](search.md); its live results keep to the space too. The breadcrumb reads "Spaces › title". Then the initials badge, the title (`sources[].title`, else the name of the source, which stays the address of the page), the sentence `sources[].description` declares in the configuration when there is one, and the line "N pages · repository X · updated N days ago", the repository named from the URL of a git source, else by the name of the source, the change being the newest git date among the notes of the space.

"Browse — N categories, as filed in the repository" lists one card per top-level folder of the repository, by name: the folder by the title `sources[].folders` gives it, else as written, one sentence (the description the configuration gives the folder, else the description of the type every note of the folder shares, else nothing), its page count, folders included, and an arrow. A category opens its own list, the [category](category.md) page; when a note takes the address of that list, the card leads to the page the tree lists first under the folder, where the tree opens on it. The note under the cards reads "Each category opens its own list. The tree on the left appears only once in a page, so that nothing has to be unfolded from the home page.": the page carries no tree, which appears once, on the [entity page](entity-page.md).

On the right, "Recently changed" lists the four latest pages of the space, each with its category and its date relative to the build, and "The most cited words here" offers as chips the five pages the notes of the space cite most, a note counted by the links from those notes, a [keyword page](keyword-page.md) by the passages read in the space and drawn dashed, with the note "Counted in this space only, which gives its own vocabulary." The column closes on the sentence "A space reads like a small wiki within the wiki: its own search, its own vocabulary, its own news."

## Objects

- Reads: [model](../../objects/inference/model.md), [source](../../objects/ingestion/source.md), [entity](../../objects/inference/entity.md)

## Actions

1. Search in the space → [search](search.md)
2. Open a category → [category](category.md)
3. Open a recent page → [entity page](entity-page.md)
4. Open a cited word → [keyword page](keyword-page.md)
5. Back to every space → [spaces](spaces.md)

## Rules

- [Stale source](../../rules/sources/stale-source.rule.md)
