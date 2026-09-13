---
roles: [roles/publication/reader]
url_pattern: /{source}/{path}
status: valid
---
# Entity page

The page of a note, laid out as a wiki a corporate reader already knows: the text in the centre, what the tool computed in the right panel. One template serves every type; only the highlighted properties, the labels of the attributes and the order of neighbours change, and all of them come from the profile. A type may have a page of its own: a component a theme or the type's module provides for it is rendered instead of the generic template, which stays the fallback of every type.

The order is fixed. On the left, the tree of the space of the page, the [source](../../objects/ingestion/source.md) it comes from. In the centre, the breadcrumb, the title, a line naming the type with two qualifying properties, then the rendered markdown at full column width and the path of the file with its edit link. On the right, three stacked blocks, never tabs: the declared metadata, the table of contents of the note and the related pages, then the line that unfolds the neighbourhood. Metadata never sits between the title and the text, and at most five properties are highlighted; the attributes the profile does not declare for the type follow in a block of their own, as written. Written links, recognised words with a note and recognised expressions without one are distinguished in the text, with a legend of the three marks.

## Today

The page at `<id>/index.html` is a grid of three regions. The left column is the tree of the space: an initials badge and the title of the source, leading to the page of the space, its folders by their titles with their page counts, every folder leading to its [category](category.md) list, the folders on the way to the page open, the page marked by a rule and the bold weight, never by colour alone; a folder of more than forty pages lists a window around the current one and counts the others. The centre opens with the breadcrumb, space › folders › page, the space linking to its page and every folder to its list; then the title, then a line naming the type as a chip leading to the [search](search.md) filtered on that type, when the note last changed relative to the build, "Space <title>" leading to the page of the space, and the first two properties the profile highlights for the type, a second line for the next three when it names that many. The note follows as an article at full column width, one section per heading, with its headings, lists, quotes and code blocks; a table is drawn as a card, its header row in uppercase labels on the soft surface, the first column in the ink and the other cells in the secondary colour; an image of its repository that stands on a line of its own is shown in the flow of the text as a figure, with its alternative text as the caption, the note "Image of the repository, shown in the flow of the text" and the path of the file in its repository in the monospace family, the build copying the file next to the page; an image among text stays inline, and an external image keeps its URL and is never fetched. In the text, three marks tell three degrees of curation apart. A markdown link whose target is a page of the site is marked as written, a solid underline in the accent: someone wrote the link. A recognised word whose [entity](../../objects/inference/entity.md) has a note is a dotted link in the accent to the page of that entity. A recognised expression that has a [keyword page](keyword-page.md) and no note, one that only has occurrences, is a link to that page drawn with grey dashes, never the accent, so that its page is reachable from the prose and not only by search; an expression under the publication threshold has no page and gets no mark, so that one setting governs the volume of the site and the density of the text. A page is marked once per note, on its first occurrence: a page a written link on the same line or above, or a recognised word above, already leads to stays plain text; where two expressions overlap, the longest wins its position. Marking is rendering, and the counts of passages and mentions do not change. The dots and dashes never carry the information alone: every mark says on hover, and to assistive technology, "note: <title>" or "N passages, no note". The foot of the article carries the legend of the three marks, "written link", "recognised word, existing note" and "recognised word, no note", then the path of the file in the monospace family, linked to its edit page on the forge when the source is a GitHub or GitLab repository or the configuration gives an edit pattern, and "Something to correct? Edit this page" leading there, else to the contribution address `project.contribute_url` declares, and shown only when it leads somewhere. In the panel, the application and the domain of the page read by the titles the configuration gives them and lead to the search filtered on them.

The right panel holds its blocks in a fixed order. "Properties" lists the declared metadata: the common properties, then the attributes the type declares in the order of its declaration, each labelled as the profile says in the language of the site, the values of a list separated by commas, with the note "N declared keys. The rest of the file is free text."; the keys of the frontmatter the profile declares for no type follow in a block of their own, "Other attributes", kept as written, so that a note of any type shows everything its author wrote. "On this page" lists the sections of the note that have a heading, each a link. "Related pages" is the [mentions panel](../panels/mentions-panel.md). Last, "See the neighbourhood map · N pages" unfolds the [neighbourhood map](../panels/neighbourhood-map.md) and its list. The same template serves every type, and only the badge, the highlighted properties, the labels and the order of the neighbours change with it.

## Three widths

The same page serves a phone, a tablet and a desktop; the text never shrinks, the two side regions give way. Under 700 px the bar keeps a menu button, a bordered square of 48 px, the mark, the site name cut with an ellipsis where it does not fit, and a search button, a square drawing the magnifier that unfolds the field under the bar; the menu button opens a drawer over the whole screen: ✕ and the name in the bar, the search field first, the spaces with their initials badges and page counts, the tree of the current space unfolded to the page, the index and the recent changes at the foot, the mode switch after them. The page reads in one column: the breadcrumb cut to the last folder and the page, the type and the short date under the title, the note, the path of the file and the edit link, then the blocks of the panel as folded sections with their counts, the table of contents first, the related pages open with three entries and the others behind their count, the neighbourhood map behind its line with the number of pages it draws. Between 700 and 1099 px the search button reads as a small field after the name and unfolds the field under itself, the mode switch joins the bar, the tree stays in the drawer, and the panel stands in a narrow column beside the text, condensed: the properties show their values alone, the table of contents is left out, the related pages three titles and the others behind their count, and the neighbourhood map spans the foot of the page. From 1100 px the page has three columns, the tree, the text and the full panel. The drawer, the tree and every block are native disclosure elements, which the stylesheet keeps open where the layout has room, so that the folding needs no script and the page reads over `file://` and without JavaScript. Every control is a target of at least 40 px, 48 px on the phone, and no text goes under 13 px; the chrome uses one type family for the text, headings included, and a monospace one for paths and identifiers only, both shipped with the site.

## Per type

The page of a type is resolved before it is rendered: a component named `EntityPage@<type>` by a theme, or the `EntityPage` a type module ships, replaces the generic template for every entity of that type, and receives the same view model, the declaration of the type included, so that it lays the page out from the declaration rather than from a list of keys. The same goes for one attribute (`Attribute@<name>`) and one mapped section (`Section@<key>`), which the generic template renders through the resolved component when there is one. The priority is fixed: the project theme, then the type module, then the default theme; the build summary lists every resolved component. The runbook of the example plugin, a procedure for operating the tool, has such a page.

## Sketch

The layout the page was drawn from, before any rendering existed: the tree of the space on the left, the note in the centre, the panel on the right. The file lives next to the screen notes and the build copies it beside the page, as it does for every image of a repository that stands on a line of its own.

![Sketch of the entity page](../assets/entity-page-sketch.svg)

## Contract

The page of an API whose contract the build imported is the [API page](api-page.md): the same shell, its operations under it in the tree, the operations table matched to the contract and the contract block with the [contract viewer](../../viewers/contract-viewer.md) after the article, the properties cut to five keys and the operations first among the related pages. The markdown of the note is untouched.

## Documents

The page of a slide deck, a PDF or a transcript, or of a note merged with one, carries the [document viewer](../../viewers/document-viewer.md) after the article: the download link of each file, its PDF, a rail of its pages, slides or cues, their extracted text in disclosure blocks, and the viewer that opens the PDF on demand. The markdown of the note is untouched.

## Mentions

The [mentions panel](../panels/mentions-panel.md) is the "Related pages" block of the right panel: one entry per page that evokes the entity, by number of passages, written links and recognised words counted alike, each entry marked "Cited" when the page writes a link, six in view before the button naming the others; the note under the list says so. The first twenty mentions are in the served HTML; the rest loads from a JSON fragment specific to the entity.

## Neighbourhood

The neighbourhood map, folded behind the last line of the right panel, shows the six closest entities at one hop, each with its name in plain text, next to a list that carries the same information. The order is type-driven and comes from the profile: on an API the operations come first, on a screen the accessed objects, on a rule what it applies to; the types the profile does not list for the page's type, keyword pages among them, come after, and within a group the most confident neighbour leads. The truncation to six happens after this ordering, so the map shows the best of the priority order rather than the most confident overall. A type without a declaration keeps the order by confidence. A separator marks each change of group; the template knows no type and renders the list as the model gives it.

## Objects

- Reads: [entity](../../objects/inference/entity.md), [link](../../objects/inference/link.md), [source](../../objects/ingestion/source.md), [finding](../../objects/quality/finding.md)

## Actions

1. Open a page of the tree → [entity page](entity-page.md)
2. Open a folder of the tree or of the breadcrumb → [category](category.md)
3. Open the space → [space](space.md)
4. Open a neighbour → [entity page](entity-page.md)
5. Open a keyword → [keyword page](keyword-page.md)
6. Search, or open the type, the application or the domain → [search](search.md)

## Rules

- [Broken link](../../rules/links/broken-link.rule.md)
- [Ambiguous relation](../../rules/vocabulary/ambiguous-relation.rule.md)
