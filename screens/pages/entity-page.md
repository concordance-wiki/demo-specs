---
roles: [roles/publication/reader]
url_pattern: /{source}/{path}
status: valid
---
# Entity page

The page of a note, laid out as a wiki a corporate reader already knows: the text in the centre, what the tool computed in the right panel. One template serves every type; only the highlighted properties, the labels of the attributes and the order of neighbours change, and all of them come from the profile. A type may have a page of its own: a component a theme or the type's module provides for it is rendered instead of the generic template, which stays the fallback of every type.

The order is fixed. On the left, the tree of the space of the page, the [source](../../objects/ingestion/source.md) it comes from. In the centre, the breadcrumb, the title, a line naming the type with two qualifying properties, then the rendered markdown at full column width and the path of the file with its edit link. On the right, three stacked blocks, never tabs: the declared metadata, the table of contents of the note and the related pages, then the line that unfolds the neighbourhood. Metadata never sits between the title and the text, and at most five properties are highlighted; the attributes the profile does not declare for the type follow in a block of their own, as written. Written links and recognised words are distinguished in the text, with a legend.

## Today

The page at `<id>/index.html` is a grid of three regions. The left column is the tree of the space: an initials badge and the name of the source, its folders with their page counts, the folders on the way to the page open, the page marked by a rule and the bold weight, never by colour alone; a folder of more than forty pages lists a window around the current one and counts the others. The centre opens with the breadcrumb, space › folder › page, the space linking to the file tree of the [home](home.md); then the title, then a line naming the type, when the note last changed relative to the build, the space, and the first two properties the profile highlights for the type, a second line for the next three when it names that many. The note follows as an article at full column width, one section per heading, with its headings, lists, tables, quotes, code blocks and the images of its repository, which the build copies next to the page; an external image keeps its URL and is never fetched. In the text, a markdown link whose target is a page of the site is marked as written, and every recognised word is a dotted link to the page of the [entity](../../objects/inference/entity.md) it names; a legend under the article names the two marks. Under the note, the path of the file in the monospace family and, when the source is a GitHub or GitLab repository or the configuration gives an edit pattern, "Something to correct? Edit this page" leading to the edit page on the declared ref.

The right panel holds its blocks in a fixed order. "Properties" lists the declared metadata: the common properties, then the attributes the type declares in the order of its declaration, each labelled as the profile says in the language of the site, the values of a list separated by commas, with the note "Declared at the top of the file."; the keys of the frontmatter the profile declares for no type follow in a block of their own, "Other attributes", kept as written, so that a note of any type shows everything its author wrote. "On this page" lists the sections of the note that have a heading, each a link. "Related pages" is the [mentions panel](../panels/mentions-panel.md). Last, "See the neighbourhood map · N pages" unfolds the [neighbourhood map](../panels/neighbourhood-map.md) and its list. The same template serves every type, and only the badge, the highlighted properties, the labels and the order of the neighbours change with it.

## Three widths

The same page serves a phone, a tablet and a desktop; the text never shrinks, the two side regions give way. Under 768 px the bar keeps the mark, the site name and a menu button, a target of 48 px, that opens a drawer over the whole screen: ✕ and the name in the bar, the search field first, the spaces with their initials badges and page counts, the tree of the current space unfolded to the page, the index and the recent changes at the foot, the mode switch after them. The page reads in one column: the breadcrumb cut to the last folder and the page, the type and the short date under the title, the note, then the blocks of the panel as folded sections with their counts, the related pages open, the neighbourhood behind its line. Between 768 and 1179 px the bar gains a search button that unfolds the field under itself and the mode switch, the tree stays in the drawer, and the panel keeps its column beside the text, condensed: the properties show their values alone, the related pages three titles and the others behind their count, and the neighbourhood map spans the foot of the page. From 1180 px the page has three columns, the tree, the text and the full panel. The drawer, the tree and every block are native disclosure elements, which the stylesheet keeps open where the layout has room, so that the folding needs no script and the page reads over `file://` and without JavaScript. Every control is a target of at least 40 px, 48 px on the phone, and no text goes under 13 px; the chrome uses one type family for the text, headings included, and a monospace one for paths and identifiers only, both shipped with the site.

## Per type

The page of a type is resolved before it is rendered: a component named `EntityPage@<type>` by a theme, or the `EntityPage` a type module ships, replaces the generic template for every entity of that type, and receives the same view model, the declaration of the type included, so that it lays the page out from the declaration rather than from a list of keys. The same goes for one attribute (`Attribute@<name>`) and one mapped section (`Section@<key>`), which the generic template renders through the resolved component when there is one. The priority is fixed: the project theme, then the type module, then the default theme; the build summary lists every resolved component. The runbook of the example plugin, a procedure for operating the tool, has such a page.

## Contract

The page of an API whose contract the build imported carries the [contract viewer](../../viewers/contract-viewer.md) between the article and the side panel: the operations as a plain list, the download link and the viewer that loads the signatures on demand. The markdown of the note is untouched.

## Documents

The page of a slide deck, a PDF or a transcript, or of a note merged with one, carries the [document viewer](../../viewers/document-viewer.md) after the article: the download link of each file, its PDF, a rail of its pages, slides or cues, their extracted text in disclosure blocks, and the viewer that opens the PDF on demand. The markdown of the note is untouched.

## Mentions

The [mentions panel](../panels/mentions-panel.md) is the "Related pages" block of the right panel: one entry per page that evokes the entity, most passages first, written links and recognised words counted alike, each entry marked "Cited" when the page writes a link. The first twenty mentions are in the served HTML; the rest loads from a JSON fragment specific to the entity.

## Neighbourhood

The neighbourhood map, folded behind the last line of the right panel, shows the six closest entities at one hop, each with its name in plain text, next to a list that carries the same information. The order is type-driven and comes from the profile: on an API the operations come first, on a screen the accessed objects, on a rule what it applies to; the types the profile does not list for the page's type, keyword pages among them, come after, and within a group the most confident neighbour leads. The truncation to six happens after this ordering, so the map shows the best of the priority order rather than the most confident overall. A type without a declaration keeps the order by confidence. A separator marks each change of group; the template knows no type and renders the list as the model gives it.

## Objects

- Reads: [entity](../../objects/inference/entity.md), [link](../../objects/inference/link.md), [source](../../objects/ingestion/source.md), [finding](../../objects/quality/finding.md)

## Actions

1. Open a page of the tree → [entity page](entity-page.md)
2. Open a neighbour → [entity page](entity-page.md)
3. Open a keyword → [keyword page](keyword-page.md)
4. Search → [search](search.md)

## Rules

- [Broken link](../../rules/links/broken-link.rule.md)
- [Ambiguous relation](../../rules/vocabulary/ambiguous-relation.rule.md)
