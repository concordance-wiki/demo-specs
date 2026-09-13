---
aliases: [W-SOURCE-UNREACHABLE]
severity: warning
---
# Unreachable source

A declared source could not be fetched or read: wrong URL, unknown ref, missing credentials or a missing local path. The build goes on without it; nothing from that source enters the model until it comes back.

Check `W-SOURCE-UNREACHABLE`, severity warning by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/W-SOURCE-UNREACHABLE.md). The severity can be overridden per project or per repository.

## Applies to

- [Resource](../../objects/ingestion/resource.md)
- [Build](../../processes/ingestion/build-pipeline.md)
