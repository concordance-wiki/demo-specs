---
aliases: [neighbourhood, neighbourhood panel]
roles: [roles/publication/reader]
url_pattern: /{source}/{path}#neighbourhood-title
status: valid
---
# Neighbourhood map

The small map of the [entity page](../pages/entity-page.md) that shows the closest entities at one hop, all labelled, and never stands alone: a list next to it carries the same information in text. Deliberately modest, six nodes by default and twelve at most; beyond the cap the map is not shown and a pointer to the [mentions panel](mentions-panel.md) takes its place.

## Today

The map sits after the side panel of the page, under the heading "Neighbourhood" followed by the title of the entity. The entity is the centre; its neighbourhood comes from the [model](../../objects/inference/model.md), computed at build and never in the browser, in the order the profile gives: the neighbours stand on a ring around the centre in that order, clockwise from the top. Every node carries its name in plain text next to it, on the outer side of the ring so that names never sit over the edges, and a name longer than twenty-eight characters is cut with an ellipsis, the full title staying in the list below. The layout is deterministic and the same labels never overlap: the tool estimates the width of every label, pushes apart any two that would touch, and widens the drawing to hold the longest ones.

The type of a neighbour is told by shape and glyph, not by colour. A typed [entity](../../objects/inference/entity.md) is a filled circle holding the glyph of its type, a shape the theme maps to the glyph name the profile declares (a hexagon for an API or an endpoint, a rectangle for a screen, a shield for a rule, a book for a term, and so on) or the initial of the glyph name when the theme has no shape for it. A [keyword page](../pages/keyword-page.md), a word without a note, is a hollow dashed square, and the edge that leads to it is dashed too. Colour follows the theme and carries nothing on its own.

The map is drawn for at most the configured number of nodes, `site.neighbourhood.size`, six by default and twelve at most. When the model holds more neighbours than that, the map gives way to one sentence, "n neighbours in total, more than the map shows: see the mentions panel", linking to the panel where every citation is listed; the list of the neighbours that were kept stays under it.

The map is hidden from assistive technologies and the list right under it, inside the same section, is authoritative: the same neighbours in the same order, each entry naming the entity by its title, its type by the label the profile gives it in the site language ("Keyword" for a word without a note), and the nature of the [link](../../objects/inference/link.md) by the relation label read from the page, so that a screen reads "accesses" and the object it reaches reads "is accessed by". The figure points at the list, the list is never hidden, and the page writes no wording of its own into it: what the profile and the project's labels say reaches the reader unchanged. The list is plain text in the served HTML, where the search index reads it with the rest of the page, so a neighbour found there leads to the page as any other word does.

## Objects

- Reads: [model](../../objects/inference/model.md), [entity](../../objects/inference/entity.md), [link](../../objects/inference/link.md)

## Actions

1. Open a neighbour → [entity page](../pages/entity-page.md)
2. Open a noteless word → [keyword page](../pages/keyword-page.md)
3. Beyond the cap, see every citation → [mentions panel](mentions-panel.md)

## Rules

- [Accessibility](../../rules/engine/accessibility.rule.md)
