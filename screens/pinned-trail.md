---
roles: [reader]
url_pattern: /{source}/{path}#trail={id},{id}
status: valid
---
# Pinned trail

The list, under the header of every page, of the pages a reader visited, in order, each a link, so that an investigation can be resumed or shared. The trail travels in the URL, is kept in the browser once pinned, and folds its oldest entries beyond twelve. Nothing is fetched and nothing leaves the browser.

## Today

The trail is an island of the header, served empty: without JavaScript the region holds nothing and takes no space. Once its script runs, it renders a navigation region named "Trail" with an ordered list of links, one per page visited, the current page marked as such, and a "Pin" button. The page of an [entity](../objects/entity.md) enters the trail when it is opened, once: reloading a page does not repeat it. The home page, the [alphabetical index](alphabetical-index.md) and the [to-do page](todo-page.md) carry the trail without entering it. A page the browser never saw is named by its identifier until it is visited.

The trail travels in the fragment of the URL, `#trail=` followed by the identifiers of the pages, each URL-encoded and separated by commas. Copying the address of a page shares the path followed; reloading restores it; following a link of the site carries it along, the fragment being appended to the link when it is followed. A link to a passage keeps its own fragment: the trail of the tab is kept in the session storage of the browser as well, and a page without a fragment trail reads it from there. The fragment is read first, then the tab, then the pinned trail.

Pressing "Pin" keeps the trail, titles included, in the local storage of the browser under `concordance-trail`; the button reads "Unpin" and is pressed while the trail shown is the pinned one, and every page then opened joins the stored trail. A later visit, or a new tab, without a fragment trail starts from the pinned trail. "Unpin" forgets it. A shared trail that differs from the pinned one is shown unpressed and leaves the stored one alone.

Beyond twelve entries the oldest fold into one "… N earlier pages" entry, a disclosure that lists them when opened, so that the region stays one or two lines; beyond fifty the oldest are dropped. The list is made of plain links and the pin is a button, all reachable with the keyboard; the audit of the [accessibility](../rules/accessibility.md) rule runs on a page with the trail rendered.

## Objects

- Reads: [entity](../objects/entity.md)

## Actions

1. Open a page of the trail → [entity page](entity-page.md)
2. Open a keyword page of the trail → [keyword page](keyword-page.md)

## Rules

- [Accessibility](../rules/accessibility.md)
