---
roles: [roles/publication/reader, roles/inference/glossary-owner]
url_pattern: /keywords/{word}
status: valid
---
# Keyword page

The page of a word nobody defined. Same template as the [entity page](entity-page.md), without the markdown and the declared properties. A banner says that no note exists and how many passages were recorded. Three numbers only: occurrences, files, sources. The passages follow, grouped by file in corpus order, with their context. Accompanying words are sized by co-occurrence, and expressions with a similar form are offered as a lead, worded to assert nothing.

A keyword page exists from three occurrences in at least two files. If a note is created later, the page keeps its address and fills in.

## Today

The page at `keywords/<slug>/index.html` stands on the shell of the [entity page](entity-page.md): the badge reads "Keyword" next to a "no note" mark, then the title, the display form of the expression. Where the entity page puts the note, a banner says the expression has no note and how many passages were recorded, and offers to create the note: a link to the new-file page of the glossary repository when it lives on GitHub or GitLab, plain text otherwise. Under it, three numbers only, occurrences, files and sources, then the passages grouped by file in corpus order, sources as the configuration declares them, then paths, then lines; each group links to the file's page, each passage to its line, and the expression is marked in the quoted context. Where the entity page keeps its properties, the page lists the accompanying words: the [entities](../../objects/inference/entity.md) and the other keyword pages named in the same paragraphs, the twelve most frequent, each sized by the rank of its count and followed by that count in text; then the expressions of a similar form, one contained in the other or half the words shared, five at most, under a wording that asserts nothing. The neighbourhood and the mentions follow, as on every page. There is no article, no properties panel and no source footer.

When a note defines an expression that recurs above the threshold, the address its keyword page had forwards to the note's page, so that a link written to the keyword page survives; the build counts these forwarding pages in its summary.

## Objects

- Reads: [entity](../../objects/inference/entity.md), [model](../../objects/inference/model.md)

## Actions

1. Open a passage's file → [entity page](entity-page.md)
2. Open an accompanying word → [keyword page](keyword-page.md)
3. Create the note → the forge of the glossary

## Rules

- [Undefined term](../../rules/vocabulary/undefined-term.rule.md)
