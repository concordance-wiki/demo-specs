---
aliases: [collapsible panel, panel handle]
roles: [roles/publication/reader]
url_pattern: /{source}/{path}
status: valid
---
# Side panel

Each of the two columns beside the text of the [entity page](../pages/entity-page.md), the tree of the space on the left and the panel of what the tool computed on the right, and the handle on its edge that folds it. Folding gives the room to the wide content of the note, tables, figures, code and documents, while the prose keeps its measure; the browser remembers what a reader folded, page after page, and nothing of it enters the address.

## Today

On a desk, from 1100 px, a handle stands at the middle of the edge of each panel: a tab of paper half slid behind the panel, of which 13 px show, without any label or border on the panel side, drawing ‹ or › the way the panel goes. It stays at the middle of the viewport as the page scrolls, always at the same place. It is a button named after its panel, "Tree of the space" or "Right panel", titled "Fold or unfold", and it announces whether the panel is unfolded; the `[` key folds and unfolds the tree, the `]` key the right panel, outside a field and without a modifier. Under 1100 px the layouts of the tablet and the phone already fold the panels, and the handle does not exist.

Folded to 44 px, the tree keeps its initials badge and the name of the space written upwards, so that the reader knows what they reopen; the right panel keeps the heading of each of its blocks with its count, "Properties", "On this page", "Related pages", written the same way, its content hidden and out of the tab order, the line of the [neighbourhood map](neighbourhood-map.md) with it. The room goes to the text: the centre column widens up to 1200 px for the tables, the figures, the code and the documents of the note, while its paragraphs, lists and headings keep their measure, because beyond it the eye loses the line.

The folded panels are a preference, not a content to share: they live in the local storage of the browser under `concordance-panels`, as the names of the folded panels, and are applied to the root of the page before the first paint by a short inline script, so that a folded panel never opens and folds again on the next page. Without JavaScript every panel stands open and no handle shows: the page stays whole. Every page laid out as the entity page folds the same way, the [keyword page](../pages/keyword-page.md), the [meeting page](../pages/meeting-page.md), the [API page](../pages/api-page.md), the [document page](../pages/document-page.md) and the [category](../pages/category.md) list.

## Objects

- Reads: [entity](../../objects/inference/entity.md)

## Actions

1. Fold or unfold the tree → [entity page](../pages/entity-page.md)
2. Fold or unfold the right panel → [entity page](../pages/entity-page.md)

## Rules

- [Accessibility](../../rules/engine/accessibility.rule.md)
