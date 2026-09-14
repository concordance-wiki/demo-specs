---
aliases: [I-TERM-HOMONYM]
severity: info
---
# Term homonym

Two entities share a title or an alias once spellings are compared: same form after lower-casing, accent stripping and singularisation. The recognition dictionary keeps both, every occurrence of the form links to each entity at half the confidence it would have with a single target, glossary entities first, and the finding names the form and the entities. When the two are different things, distinct titles or aliases settle it; when they are one concept seen from two sides, as the glossary term and the business object called "Entity" in this wiki, both stay and a `## Not to be confused with` section tells the reader which is which. The linter reports the same finding in global scope for a local title that an entity of another type carries in the published model. A twin folded into its note is no homonym: the twin resources are reconciled before the dictionary is built, and the titles and aliases of the folded twin name the entity it became, once.

Check `I-TERM-HOMONYM`, severity info by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/I-TERM-HOMONYM.md). The severity can be overridden per project or per repository.

## Applies to

- [Entity](../../objects/inference/entity.md)
- [Build](../../processes/ingestion/build-pipeline.md)
- [Lint](../../processes/quality/lint.md)
