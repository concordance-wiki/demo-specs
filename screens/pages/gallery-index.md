---
aliases: [component gallery, gallery]
roles: [roles/publication/theme-author]
url_pattern: /gallery/
status: valid
---
# Gallery index

The page set `concordance gallery` writes so that a theme is styled and checked without building a corpus: every slot of the site rendered with fixture view models, one page per slot and state, under an index that says who renders each slot.

## Today

The command writes `index.html`, one page per slot and state, the stylesheet under `assets/site.css` and the island bundles next to it, in `./gallery` by default (`--output`). The index groups the states by board of the reference design, in the order of the boards: the [home](home.md), the [entity page](entity-page.md), the [search results](search.md), the accessibility board, which has no state of its own, the [keyword page](keyword-page.md), the [meeting page](meeting-page.md), the [API page](api-page.md), the [neighbourhood map](../panels/neighbourhood-map.md) open, the phone and the tablet, the [alphabetical index](alphabetical-index.md), the [spaces](spaces.md), the [page of a space](space.md), the [category list](category.md), the screen page, the [document page](document-page.md), then the [to-do page](todo-page.md), the two panels framed under a heading of their own and the chrome in its other shapes (a right-to-left locale, a header with a logo, a footer with a project text). Every board has its state in the corporate chrome on the fixtures corpus, named after it, beside the default state, an empty one where meaningful (no mention, no neighbour, no result, nothing to do) and the degraded cases: a corpus fed by one repository, a note without a property, a keyword page whose transcript passages carry no timecode, an API page whose contract could not be fetched, and, for every page that carries an island of its own, the page served without the scripts of its islands, captioned "server HTML only". Each board carries its caption and a link to its screen note here; each state its caption, its width, who renders its slot, the default theme or the plugin and theme that override it, and the page framed at the width its board is drawn at, 390 px for a phone, 834 px for a tablet, 1440 px for a desktop, the heading of the state opening the page alone. Three buttons above the boards, an island served hidden, set every frame to one width once the script runs; without it each frame keeps its own. A section then lists the eleven slots in order and who renders each, and a last one every registered type, the core ones, those the plugins contribute and those of the project profile, with one page each: the note template of the type rendered as a note of that type through the generic [entity page](entity-page.md) or, when a theme or the type's module provides one, through its dedicated component, which the index names. The pages use a neutral palette and the labels of the default theme; the stylesheet follows the system colour scheme, the switch in the header forces one, and `data-mode="dark"` on the root element previews the dark palette without JavaScript. One test per state pins the skeleton of its page, the elements with their classes, role and ARIA attributes, text and links left out, so that a change of structure is reviewed against its board.

The theme comes from the registry the build uses: `--theme` names a plugin package or the path of its module, repeated at will, the last one winning a slot; without it the `plugins:` of the configuration apply, and without any the default theme renders alone. The `theme.yaml` of the project replaces the neutral palette and the fixture chrome with the project's name, logo, favicon, palette, stylesheet, footer and credit. Every page is measured against the budget and run through the static accessibility checker; a page over budget or a finding fails the command with one line per problem, and a palette pair under its contrast minimum is printed as a warning. Continuous integration of the tool builds the gallery on every change and publishes it as an artifact of the run.

## Objects

- Reads: [model](../../objects/inference/model.md)

## Actions

1. Open a state through its heading → the page of that state, alone
2. Press a width → every frame at that width
3. Open the screen note of a board → the note of that page, here
4. Switch the colour scheme → the same page in the other palette

## Rules

- [Accessibility](../../rules/engine/accessibility.rule.md)
