---
domain: inference
aliases: [relation type determination, four rungs]
severity: info
condition: a link between two notes needs a relation of the profile
---
# Relation typing

Every link between two notes ends up with a relation of the profile, decided on four rungs, the first that applies winning: a mapped section (a business object under `## Objects` of a screen is `accesses`), a typed frontmatter attribute (`reads` is `accesses` in `read` mode), a type pair that admits a single relation (a markdown link or a plain mention between a rule and a screen is `constrains`, marked `relation_origin: pair` and turned around when the profile only allows it the other way), then `related`, kept with its confidence capped at 0.60 and reported by the [ambiguous relation](../vocabulary/ambiguous-relation.rule.md) check. The first two rungs come from what the author wrote and are never overturned; a declared relation the profile does not allow between the two types is dropped by the [relation outside the matrix](../identifiers/relation-outside-the-matrix.rule.md) check. The labels shown for a relation, in either direction, come from the profile alone. The [architecture guide](https://github.com/concordance-wiki/concordance/blob/main/docs/guides/architecture.md#relation-typing) and the [writing guide](https://github.com/concordance-wiki/concordance/blob/main/docs/guides/writing-notes.md#how-a-relation-gets-its-name) describe it.

## Applies to

- [Link](../../objects/inference/link.md)
- [Build](../../processes/ingestion/build-pipeline.md)
