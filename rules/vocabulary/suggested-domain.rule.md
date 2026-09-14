---
aliases: [I-DOMAIN-SUGGESTED, emergent domain proposal]
severity: info
---
# Suggested domain

A note no frontmatter, folder or glob files lies within the radius of a pivot of the neighbourhood: a term with a note of its own whose distinct neighbours, over the typed links and the co-occurrence neighbourhood, reach the configured threshold. The note is a candidate for a domain named after the pivot, the last segment of its identifier, and is attached to the closest pivot, at equal distance to the one of highest degree, then to the first identifier in code-unit order. A stopword or a term the lock file rejects never pivots. The build proposes and files nothing: a growing corpus moves its pivots, and a note would swing from one domain to another between two builds. The proposal is promoted by declaring the domain in the configuration with the folders or globs that claim its notes, or by naming the note under `domains` in the lock file; the configuration may also let the build file every reached note itself, with the origin `inferred`.

Check `I-DOMAIN-SUGGESTED`, severity info by default, raised only when the configuration sets `inference.domains`, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/I-DOMAIN-SUGGESTED.md). The severity can be overridden per project or per repository. Distinct from the [unclassified domain](unclassified-domain.rule.md), which says that nothing files the note; the suggestion says where it could go.

## Applies to

- [Entity](../../objects/inference/entity.md)
- [Build](../../processes/ingestion/build-pipeline.md)
