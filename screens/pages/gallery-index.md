---
aliases: [component gallery, gallery]
roles: [roles/publication/theme-author]
url_pattern: /gallery/
status: valid
---
# Gallery index

The page set `concordance gallery` writes so that a theme is styled and checked without building a corpus: every slot of the site rendered with fixture view models, one page per slot and state, under an index that says who renders each slot.

## Today

The command writes `index.html`, one page per slot and state, the stylesheet under `assets/site.css` and the island bundles next to it, in `./gallery` by default (`--output`). The index lists the eleven slots in order and, for each, who renders it, the default theme or the plugin and theme that override it, and one link per state: the default state and, where meaningful, an empty one (no mention, no neighbour, no result, nothing to do), the [mentions panel](../panels/mentions-panel.md) with more than twenty mentions so that the island is served, the [home](home.md) page in a right-to-left locale, the header with a logo, the footer with a project text. The chrome slots are seen on every page; the two panels are framed under a heading of their own. A last section lists every registered type, the core ones, those the plugins contribute and those of the project profile, with one page each: the note template of the type rendered as a note of that type through the generic [entity page](entity-page.md) or, when a theme or the type's module provides one, through its dedicated component, which the index names. The pages use a neutral palette and the labels of the default theme; the stylesheet follows the system colour scheme, the switch in the header forces one, and `data-mode="dark"` on the root element previews the dark palette without JavaScript.

The theme comes from the registry the build uses: `--theme` names a plugin package or the path of its module, repeated at will, the last one winning a slot; without it the `plugins:` of the configuration apply, and without any the default theme renders alone. The `theme.yaml` of the project replaces the neutral palette and the fixture chrome with the project's name, logo, favicon, palette, stylesheet, footer and credit. Every page is measured against the budget and run through the static accessibility checker; a page over budget or a finding fails the command with one line per problem, and a palette pair under its contrast minimum is printed as a warning. Continuous integration of the tool builds the gallery on every change and publishes it as an artifact of the run.

## Objects

- Reads: [model](../../objects/inference/model.md)

## Actions

1. Open a slot in a state → the page of that state
2. Switch the colour scheme → the same page in the other palette

## Rules

- [Accessibility](../../rules/engine/accessibility.rule.md)
