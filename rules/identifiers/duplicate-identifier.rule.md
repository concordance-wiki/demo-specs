---
aliases: [E-ID-DUP]
severity: error
---
# Duplicate identifier

Two files resolve to the same identifier, because identifiers strip the extension and the type suffix, or because two notes declare the same `id`. The first in canonical order is kept.

Check `E-ID-DUP`, severity error by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/E-ID-DUP.md). The severity can be overridden per project or per repository.

## Applies to

- [Entity](../../objects/inference/entity.md)
- [Build](../../processes/ingestion/build-pipeline.md)
- [Lint](../../processes/quality/lint.md)
