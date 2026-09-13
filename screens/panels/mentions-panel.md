---
roles: [roles/publication/reader]
url_pattern: /{source}/{path}#mentions-title
status: valid
---
# Mentions panel

The panel of the [entity page](../pages/entity-page.md) that answers one question: who cites this entity, and did a person write the citation or did the tool recognise it. Two sections that are never mixed: links written in notes, and files that merely cite the entity. Mentions are grouped by file, each group collapsible with its count. The first twenty are in the served HTML; the rest loads from a JSON fragment specific to the entity, never from a global index. The panel offers sorting, filtering and a collapse-all, and without JavaScript the first twenty stay readable and their links work. The threshold of twenty is configurable.

## Today

The panel sits after the neighbourhood, headed by the total number of mentions. Its first section, "Explicit mentions", holds the [links](../../objects/inference/link.md) an author wrote: a markdown link or a frontmatter reference. Its second, "Inferred mentions", holds what the tool recognised: a title or alias read in a mapped section or in prose. Each heading carries the count of its kind. Inside a section, one folding block per citing file in the order of the build, source then path, its summary giving the file path and the number of mentions in it; the first block of each section is open, the others closed. A mention links to its passage on the page of the citing file, as `line n` for a note and as `page n`, `slide n` or a timecode for a document, and shows the words around it, the words naming the [entity](../../objects/inference/entity.md) in bold when the scan kept them.

The build writes one fragment per cited entity, `fragments/<id>.mentions.json`, holding all its mentions. Up to `build.mentions_inline` mentions, twenty by default, every mention is in the page. Beyond, under two hundred in all, the rest also travels in the page inside a data block, and a button reveals it without any request. From two hundred on, a button fetches the fragment; over `file://`, where a page may not fetch, a link to the fragment stands, as it does in the served HTML before any script runs.

Once the script runs, a group of controls appears above the sections: a sort, by file, by count or by earliest line; a filter on the file path and on the words around the mention, with a line saying how many mentions are shown; and one button that collapses every block or, when all are closed, expands them all. Every control is a native element with a label, reachable with the keyboard; none exists without JavaScript, where the static list and its links stand on their own.

## Objects

- Reads: [entity](../../objects/inference/entity.md), [link](../../objects/inference/link.md)

## Actions

1. Open a passage → [entity page](../pages/entity-page.md)
2. Open the full list of mentions → the fragment of the entity

## Rules

- [Accessibility](../../rules/engine/accessibility.rule.md)
- [Broken link](../../rules/links/broken-link.rule.md)
