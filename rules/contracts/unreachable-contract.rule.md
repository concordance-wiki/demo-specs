---
aliases: [W-CONTRACT-UNREACHABLE]
severity: warning
---
# Unreachable contract

The contract an API note declares in its `contract` attribute, a URL or a path relative to the note, could not be fetched, read or parsed: the server answered with an error, the build ran without network access, the file is missing, or the document is neither an OpenAPI 3.x document in JSON or YAML nor a WSDL 1.1 or 2.0 document. No operation is imported from it, the note keeps the operations written by hand, and the build goes on; the API page has no imported operations until a later build reads the contract. A project whose contracts must be present raises the severity to `error`.

Check `W-CONTRACT-UNREACHABLE`, severity warning by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/W-CONTRACT-UNREACHABLE.md). The severity can be overridden per project or per repository.

## Applies to

- [Source](../../objects/ingestion/source.md)
- [Model query API](../../api/model-query.md)
- [Build](../../processes/ingestion/build-pipeline.md)
