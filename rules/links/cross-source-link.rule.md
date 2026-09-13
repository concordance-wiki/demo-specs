---
aliases: [W-LINK-CROSS-SOURCE]
severity: warning
---
# Cross-source link

A markdown link leaves its source, with the `<source>:<path>` prefix or with a relative path that climbs above the source root into a sibling source, while `inference.cross_source_links` is off. The link is not recorded: the model keeps no relation between the two notes until the configuration allows links across sources, or the author links to a note of the same source. The linter in global scope reports the same finding from one repository when the link reaches a note of the published model and that model says it was built with cross-source links off; a link that leaves the source for a file that does not exist is a [broken link](broken-link.rule.md) once such links are allowed.

Check `W-LINK-CROSS-SOURCE`, severity warning by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/W-LINK-CROSS-SOURCE.md). The severity can be overridden per project or per repository.

## Applies to

- [Entity](../../objects/inference/entity.md)
- [Link](../../objects/inference/link.md)
- [Build](../../processes/ingestion/build-pipeline.md)
- [Lint](../../processes/quality/lint.md)
