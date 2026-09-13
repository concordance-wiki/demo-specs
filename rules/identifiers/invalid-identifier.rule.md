---
aliases: [E-ID-INVALID]
severity: error
---
# Invalid identifier

A frontmatter `id` does not follow the identifier pattern, lowercase letters, digits and hyphens in a first segment, then at least one more segment after a slash. The declared value is ignored and the identifier derives from the source name and the file path, as if no `id` had been written, so that the page still exists at a predictable address; the finding says which value was refused.

Check `E-ID-INVALID`, severity error by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/E-ID-INVALID.md). The severity can be overridden per project or per repository.

## Applies to

- [Entity](../../objects/inference/entity.md)
- [Build](../../processes/ingestion/build-pipeline.md)
- [Lint](../../processes/quality/lint.md)
