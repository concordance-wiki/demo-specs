---
roles: [roles/publication/reader]
url_pattern: /{source}/{path}
status: valid
---
# Entity page

The page of a note. One template serves every type; only the highlighted properties, the labels of the attributes and the order of neighbours change, and all of them come from the profile. A type may have a page of its own: a component a theme or the type's module provides for it is rendered instead of the generic template, which stays the fallback of every type.

The order is fixed: a type badge with two qualifying properties, the title, then the rendered markdown at full column width. Declared metadata sits in the side panel, never between the title and the text, and at most five properties are highlighted; the attributes the profile does not declare for the type follow in a panel of their own, as written. Written links and recognised words are distinguished in the text, with a legend. The footer shows the source path and an edit link to the forge.

## Today

The page at `<id>/index.html` opens with the type badge and the first two properties the profile highlights for the type, a second line for the next three when it names that many, then the title. The note follows as an article at full column width, one section per heading, with its headings, lists, tables, quotes, code blocks and the images of its repository, which the build copies next to the page; an external image keeps its URL and is never fetched. In the text, a markdown link whose target is a page of the site is marked as written, and every recognised word is a dotted link to the page of the [entity](../../objects/inference/entity.md) it names; a legend under the article names the two marks. The declared properties sit in a side panel after the article, never between the title and the text: the common properties, then the attributes the type declares in the order of its declaration, each labelled as the profile says in the language of the site; the keys of the frontmatter the profile declares for no type follow in a second panel, "Other attributes", kept as written, so that a note of any type shows everything its author wrote. The same template serves every type, and only the badge, the highlighted properties, the labels and the order of the neighbours change with it. The footer names the source file as `source: <name>/<path>` and, when the source is a GitHub or GitLab repository or the configuration gives an edit pattern, links to its edit page on the declared ref.

## Per type

The page of a type is resolved before it is rendered: a component named `EntityPage@<type>` by a theme, or the `EntityPage` a type module ships, replaces the generic template for every entity of that type, and receives the same view model, the declaration of the type included, so that it lays the page out from the declaration rather than from a list of keys. The same goes for one attribute (`Attribute@<name>`) and one mapped section (`Section@<key>`), which the generic template renders through the resolved component when there is one. The priority is fixed: the project theme, then the type module, then the default theme; the build summary lists every resolved component. The runbook of the example plugin, a procedure for operating the tool, has such a page.

## Contract

The page of an API whose contract the build imported carries the [contract viewer](../../viewers/contract-viewer.md) between the article and the side panel: the operations as a plain list, the download link and the viewer that loads the signatures on demand. The markdown of the note is untouched.

## Documents

The page of a slide deck, a PDF or a transcript, or of a note merged with one, carries the [document viewer](../../viewers/document-viewer.md) after the article: the download link of each file, its PDF, a rail of its pages, slides or cues, their extracted text in disclosure blocks, and the viewer that opens the PDF on demand. The markdown of the note is untouched.

## Mentions

The [mentions panel](../panels/mentions-panel.md) has two sections that are never mixed: links written in notes, and files that merely cite the entity. Mentions are grouped by file, each group collapsible with its count. The first twenty are in the served HTML; the rest loads from a JSON fragment specific to the entity.

## Neighbourhood

The neighbourhood map shows the six closest entities at one hop, each with its name in plain text, next to a list that carries the same information. The order is type-driven and comes from the profile: on an API the operations come first, on a screen the accessed objects, on a rule what it applies to; the types the profile does not list for the page's type, keyword pages among them, come after, and within a group the most confident neighbour leads. The truncation to six happens after this ordering, so the map shows the best of the priority order rather than the most confident overall. A type without a declaration keeps the order by confidence. A separator marks each change of group; the template knows no type and renders the list as the model gives it.

## Objects

- Reads: [entity](../../objects/inference/entity.md), [link](../../objects/inference/link.md), [finding](../../objects/quality/finding.md)

## Actions

1. Open a neighbour → [entity page](entity-page.md)
2. Open a keyword → [keyword page](keyword-page.md)
3. Search → [search](search.md)

## Rules

- [Broken link](../../rules/links/broken-link.rule.md)
- [Ambiguous relation](../../rules/vocabulary/ambiguous-relation.rule.md)
