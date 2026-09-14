---
aliases: [dark mode, mode switch, light mode]
roles: [roles/publication/reader]
url_pattern: /{source}/{path}
status: valid
---
# Colour scheme

The switch of the bar of every page that takes the site from its light palette to its dark one and back. The dark scheme is a second palette, not an inversion of the light one: its colours are measured on their own, and nothing a reader does in one scheme is lost in the other. The choice follows the system preference, stays remembered once made, and the switch stands in the same place in both schemes.

## Today

The switch is a square button of 40 px at the right end of the bar, after the links, drawing the glyph of the scheme it switches to: a moon (☾) over a light page, a sun (☀) over a dark one. It is named "Dark mode" for assistive technology alone, in the language of the site, and is pressed while the dark scheme is displayed. Its script reads the scheme in force from the stylesheet, whatever decided it, the theme's default, the system preference or a remembered choice, and hears the system preference change while no choice is stored. Without JavaScript the theme's default and the system preference apply and no dead control is shown.

Pressing the switch displays the other scheme at once and remembers it in the local storage of the browser under `concordance-mode`, so that the next page and the next visit open in it without a flash of the other scheme: the only inline script of a page applies the remembered choice before the first paint. When the theme's default and the system preference already give the scheme asked for, nothing is stored and the page follows the system again.

The dark palette keeps the shape of the light one: the page ground goes under the surfaces of the bar, the tree of the space and the panel, the soft ground of the fields, the chips and the current entry of the tree stands above them, the rules and the grounds carry the hierarchy on their own, and no shadow is cast, where the light scheme casts a soft one under what floats over the page, the live results, the trail, the menus of the filters and the drawer. The accent rises in lightness so that a link holds 4.5:1 over every dark ground; it marks links and the current position only, as in the light scheme. The three underlines of the text, the written link, the recognised word with a note and the recognised word without one, the chips, a marked passage, the code blocks, the tables, the viewer of a document and the focus ring all take the dark palette from the same tokens; the paper of a document page alone stays white, since it is the document itself.

The contrasts of the dark scheme are measured separately: the [accessibility](../../rules/engine/accessibility.rule.md) rule lists every text and background pair of both palettes with its ratio, and no dark value is deduced from the light one. The [component gallery](../pages/gallery-index.md) shows the entity page and the home page in the dark scheme, forced on their root so that a viewer sees them dark whatever they prefer.

## Objects

- Reads: nothing of the corpus; the theme of the site

## Actions

1. Press the switch → the same page in the other scheme, remembered
2. Change the system preference while no choice is stored → the page follows it

## Rules

- [Accessibility](../../rules/engine/accessibility.rule.md)
