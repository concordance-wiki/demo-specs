---
aliases: [E-ENCODING]
severity: error
---
# Invalid encoding

A file is not valid UTF-8, a note saved in a single-byte encoding for instance. The file is skipped entirely: nothing of it enters the model, and every link that points to it is reported as a [broken link](../links/broken-link.rule.md). The linter reports it before the file is pushed, and an `.editorconfig` with `charset = utf-8` keeps the mistake from coming back.

Check `E-ENCODING`, severity error by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/E-ENCODING.md). The severity can be overridden per project or per repository.

## Applies to

- [Resource](../../objects/ingestion/resource.md)
- [Build](../../processes/ingestion/build-pipeline.md)
- [Lint](../../processes/quality/lint.md)
