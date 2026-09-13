---
roles: [roles/publication/reader, roles/inference/glossary-owner]
url_pattern: /keywords/{word}
status: valid
---
# Keyword page

The page of a word nobody defined. Same template as the [entity page](entity-page.md), without the markdown and the declared properties. A banner says that no note exists and how many passages were recorded. Three numbers only: occurrences, files, sources. The passages follow, grouped by file in corpus order, with their context. The words that accompany the expression are its neighbourhood map, drawn from its co-occurrences, and expressions with a similar form are offered as a lead, worded to assert nothing.

A keyword page exists from three occurrences in at least two files. If a note is created later, the page keeps its address and fills in.

## Today

The page at `keywords/<slug>/index.html` stands on the shell of the [entity page](entity-page.md), so that a reader meets the same three regions. On the left, the tree of the space the word is filed in: the glossary when the configuration names one, else the source of the first passage, the word inserted at its place among the notes as the current page, ruled and bold. In the centre, the breadcrumb "space › Terms › word", then the title, dotted underneath the way a word without a note is drawn on the map and in the results, then a line carrying the dashed mark "No definition" and, when a citing file has a git date, "Used since <month year>", the month of the oldest one. Where the entity page puts the note, a notice says that nobody has written a definition but that N passages use the word, that the page is built from those passages alone and that a note created later will take its place without changing the rest, and offers to propose a definition: a button leading to the new-file page of the glossary repository when it lives on GitHub or GitLab, plain text otherwise. Under it, "The passages, in corpus order" with the sentence "N files.", then the passages grouped by file, sources as the configuration declares them, then paths, then lines; each group carries the type chip and the title of its page and its count, each passage links to where it stands, the timecode of a transcript cue, the page or the slide of a converted document, else its line, and quotes its context with the expression marked.

The right panel stacks its blocks in a fixed order. "What we know" lists the occurrences, the files and the names of the spaces the passages come from, then says that the word has no declared property because there is no file for it. "Maybe the same thing" offers the expressions of a similar form, one contained in the other or half the words shared, five at most, each with its occurrence count when it is a keyword page, under a note that calls them a lead, not a claim. The related pages are the [mentions panel](../panels/mentions-panel.md) built from the passages of the word, the pages where it is used, most passages first, with the note that none of them is cited since the word has no note to carry links; last, the [neighbourhood map](../panels/neighbourhood-map.md) folded behind its line, drawn from the co-occurrences of the word since it carries no link: the [entities](../../objects/inference/entity.md) and the other keyword pages named in the same paragraphs, the six most frequent, a page as a full node and a word without a note as a dashed one, each counted by the paragraphs it shares with the word. There is no article, no properties block and no source footer.

When a note defines an expression that recurs above the threshold, the address its keyword page had forwards to the note's page, so that a link written to the keyword page survives; the build counts these forwarding pages in its summary.

## Objects

- Reads: [entity](../../objects/inference/entity.md), [model](../../objects/inference/model.md)

## Actions

1. Open a passage's file → [entity page](entity-page.md)
2. Open a word of the neighbourhood map → [keyword page](keyword-page.md)
3. Open an expression that may be the same thing → [keyword page](keyword-page.md)
4. Propose a definition → the forge of the glossary

## Rules

- [Undefined term](../../rules/vocabulary/undefined-term.rule.md)
