---
aliases: [W-DOMAIN-UNKNOWN]
severity: warning
---
# Unknown domain

A frontmatter `domain` names no domain declared under `domains:` of the configuration, by its identifier or by its identifier path. The frontmatter wins over the globs, so the value is kept as written on the entity and the site shows what the author meant, but nothing files the note under a declared domain. Distinct from the [unclassified domain](unclassified-domain.md), where the note names nothing and matches no glob.

Check `W-DOMAIN-UNKNOWN`, severity warning by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/W-DOMAIN-UNKNOWN.md). The severity can be overridden per project or per repository.

## Applies to

- [Entity](../objects/entity.md)
- [Build](../processes/build-pipeline.md)
