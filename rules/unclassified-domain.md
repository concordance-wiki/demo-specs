---
aliases: [W-DOMAIN-UNCLASSIFIED]
severity: info
---
# Unclassified domain

A note sits under no folder a declared domain claims, matches no domain glob and declares none in frontmatter. It lands in the unclassified domain. A domain claims a folder with `folder: true`, the folder named after its identifier, or `folder: <name>`, anywhere on the path of a note in any source; a subdomain declared by folder claims only the notes under its parent's folder, or anywhere on a path the parent's globs match when the parent is declared by globs. Folders and globs combine, the deepest domain winning, then the last declared.

Check `W-DOMAIN-UNCLASSIFIED`, severity info by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/W-DOMAIN-UNCLASSIFIED.md). The severity can be overridden per project or per repository.

## Applies to

- [Entity](../objects/entity.md)
- [Build](../processes/build-pipeline.md)
- [Lint](../processes/lint.md)
