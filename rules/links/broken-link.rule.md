---
aliases: [E-LINK-BROKEN]
severity: error
---
# Broken link

A markdown link written in a note points to a file that does not exist in its source. The link is not recorded and the reader lands on nothing.

Check `E-LINK-BROKEN`, severity error by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/E-LINK-BROKEN.md). The severity can be overridden per project or per repository.

## Applies to

- [Entity](../../objects/inference/entity.md)
- [Link](../../objects/inference/link.md)
- [Build](../../processes/ingestion/build-pipeline.md)
- [Lint](../../processes/quality/lint.md)
