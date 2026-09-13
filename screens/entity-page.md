---
roles: [reader]
url_pattern: /{source}/{path}
status: valid
---
# Entity page

The page of a note. One template serves every type; only the highlighted properties and the order of neighbours change, and both come from the profile.

The order is fixed: a type badge with two qualifying properties, the title, then the rendered markdown at full column width. Declared metadata sits in the side panel, never between the title and the text, and at most five properties are highlighted. Written links and recognised words are distinguished in the text, with a legend. The footer shows the source path and an edit link to the forge.

## Mentions

The mentions panel has two sections that are never mixed: links written in notes, and files that merely cite the entity. Mentions are grouped by file, each group collapsible with its count. The first twenty are in the served HTML; the rest loads from a JSON fragment specific to the entity.

## Neighbourhood

The neighbourhood map shows the six closest entities at one hop, each with its name in plain text, next to a list that carries the same information. The order is type-driven and comes from the profile: on an API the operations come first, on a screen the accessed objects, on a rule what it applies to; the types the profile does not list for the page's type, keyword pages among them, come after, and within a group the most confident neighbour leads. The truncation to six happens after this ordering, so the map shows the best of the priority order rather than the most confident overall. A type without a declaration keeps the order by confidence. A separator marks each change of group; the template knows no type and renders the list as the model gives it.

## Objects

- Reads: [entity](../objects/entity.md), [link](../objects/link.md), [finding](../objects/finding.md)

## Actions

1. Open a neighbour → [entity page](entity-page.md)
2. Open a keyword → [keyword page](keyword-page.md)
3. Search → [search](search.md)

## Rules

- [Broken link](../rules/broken-link.md)
- [Ambiguous relation](../rules/ambiguous-relation.md)
