---
aliases: [related pages]
roles: [roles/publication/reader]
url_pattern: /{source}/{path}#mentions-title
status: valid
---
# Mentions panel

The block of the [entity page](../pages/entity-page.md) headed "Related pages", which answers one question: which pages evoke this entity, and did a person write a link or did the tool recognise the words. One entry per related page, ordered by number of passages, written links and recognised words counted alike; an entry is marked "Cited" when its page writes a link. A page that nothing links to, a keyword page, a meeting or a document, lists the pages its own passages evoke instead. The first twenty mentions are in the served HTML; the rest loads from a JSON fragment specific to the entity, never from a global index. The block offers a text filter and a type filter, and without JavaScript the served pages stay readable and their links work. The threshold of twenty is configurable.

## Today

The block sits in the right panel after the table of contents, headed "Related pages" with the number of related pages. Each entry gives the title of the page as a link, its type, its number of passages and one excerpt linking to the passage: the sentence around the written link, prefixed "Cited ·", when the page holds a [link](../../objects/inference/link.md) an author wrote, a markdown link or a frontmatter reference; the first recognised one otherwise, a title or alias read in a mapped section or in prose; a passage read from a document is prefixed by its page, slide or timecode. The words naming the [entity](../../objects/inference/entity.md) are in bold when the scan kept them. The entries are ordered by number of passages, written and recognised together, the order of the build breaking ties; six stand in view, then a button, "Show the N others"; a note under the list says how they are ordered and what "cited" marks. On a tablet the panel condenses to three titles and the count of the others; on a phone two entries stand before the button. Without a related page, the block says that no other page evokes this one yet.

The related pages of a note of the model are the pages that cite it. A keyword page, a meeting and a document page stand outside the model, nothing links to them: their block lists the pages their own passages evoke, the words of a keyword read in the notes, the titles recognised in the minutes, the transcript or the slides, each entry counted and quoting the first passage, which leads to its place on the page itself; the note under the list says what kind of page this is.

The build writes one fragment per entity with a related page, `fragments/<id>.mentions.json`, holding all its mentions. Up to `build.mentions_inline` mentions, twenty by default, every mention is in the page, the first passage of each of the six pages listed first so that their entries are served whatever the count, the pages beyond six behind a disclosure worded as the button, readable without any script. Beyond, under two hundred in all, the rest also travels in the page inside a data block, and the button reveals it without any request. From two hundred on, the button fetches the fragment; over `file://`, where a page may not fetch, a link to the fragment stands, as it does in the served HTML before any script runs.

Once the script runs, a group of controls appears above the list: a filter on the title, the type and the passages, and a "Types" disclosure with one ticked checkbox per type among the pages and its count, a line saying how many pages are shown, "19 of 35 pages", and "Clear all". Every control is a native element with a label, reachable with the keyboard; none exists without JavaScript, where the static list and its links stand on their own.

## Objects

- Reads: [entity](../../objects/inference/entity.md), [link](../../objects/inference/link.md)

## Actions

1. Open a related page → [entity page](../pages/entity-page.md)
2. Open a passage → [entity page](../pages/entity-page.md)
3. Open the full list of mentions → the fragment of the entity

## Rules

- [Accessibility](../../rules/engine/accessibility.rule.md)
- [Broken link](../../rules/links/broken-link.rule.md)
