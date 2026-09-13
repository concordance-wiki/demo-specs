---
aliases: [E-FM-INVALID]
severity: error
---
# Invalid frontmatter

The YAML frontmatter cannot be parsed. The body is still processed; every declared attribute is lost.

Check `E-FM-INVALID`, severity error by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/E-FM-INVALID.md). The severity can be overridden per project or per repository.

## Applies to

- [Entity](../../objects/inference/entity.md)
- [Build](../../processes/ingestion/build-pipeline.md)
- [Lint](../../processes/quality/lint.md)
