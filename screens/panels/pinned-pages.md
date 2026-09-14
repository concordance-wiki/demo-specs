---
aliases: [pins, pinned page, pin button]
roles: [roles/publication/reader]
url_pattern: /{source}/{path}
status: valid
---
# Pinned pages

The row of tabs under the bar of every page of the generated site, holding the pages a reader chose to keep: pinned from the header of a page, unpinned by hand, kept in the browser from page to page and from one visit to the next. Tabs, but chosen: nothing preloads, nothing closes by mistake, and the selection survives a reload. The exploration trail that once followed the pages visited is gone, because it had no rule to start over; the one breadcrumb left is the filing of the page.

## Today

The header of an [entity page](../pages/entity-page.md), a [keyword page](../pages/keyword-page.md), a [meeting page](../pages/meeting-page.md), an [API page](../pages/api-page.md) or a [document page](../pages/document-page.md) carries, after the title, a "Pin" button drawn as a chip with a pin: pressing it pins the page at the end of the row, and the button, pressed and reading "Pinned", unpins it. A page is never pinned twice. Without JavaScript neither the button nor the row exists, and the page stays whole: both are drawn by the script of the island under the bar, which is served empty.

The row exists only once a page is pinned. It reads "Pinned", then one chip per page in the order of pinning, an order that never changes on its own, the page being read filled in the ink and marked as the current page, every chip a link to its page with a cross that removes it, and the count, "3 pinned", at the end. Moving to another page leaves the row as it is; a reload, a new tab, a new session find it again. There is no cap: the row shows the chips that fit and folds the others behind "+N", a summary that opens the full list: the heading "All pinned" with the count, a filter on the title and the space, every pin as a row with its title, the space its identifier starts with and its cross, and "Remove all" at the foot, the one destructive action, asked for a confirmation. The chips are measured again when the window resizes.

The pins live in the local storage of the browser under `concordance-pins`, as the identifier of each page and its title at the time it was pinned, so that a chip still reads once a later publication removed the page; they never expire on their own, having been set on purpose, and never enter the address: nothing is fetched and nothing leaves the browser. The back button of the browser stays the way to step back: a pin serves to keep, not to return.

## Objects

- Reads: [entity](../../objects/inference/entity.md)

## Actions

1. Pin or unpin the page being read → [entity page](../pages/entity-page.md)
2. Open a pinned page → [entity page](../pages/entity-page.md)
3. Open a pinned keyword page → [keyword page](../pages/keyword-page.md)

## Rules

- [Accessibility](../../rules/engine/accessibility.rule.md)
