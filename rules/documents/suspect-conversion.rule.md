---
aliases: [W-CONV-SUSPECT]
severity: warning
---
# Suspect conversion

A converted PDF holds no extractable text although the document is large; it is probably made of images. Nothing of it enters search or the occurrence scan.

Check `W-CONV-SUSPECT`, severity warning by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/W-CONV-SUSPECT.md). The severity can be overridden per project or per repository.

## Applies to

- [Resource](../../objects/ingestion/resource.md)
- [Build](../../processes/ingestion/build-pipeline.md)
