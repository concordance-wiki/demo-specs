---
aliases: [W-OPERATION-AMBIGUOUS]
severity: warning
---
# Ambiguous operation

At the rung of the [operation matching](operation-matching.md) where a match is found, two operation notes claim the same operation imported from a contract, or one note matches several operations of its API. Nothing is attached: the finding names every candidate, the imported operation stays a separate entity with the properties of the contract only, and the other notes and operations of the API are matched as usual. The `operation_id` of exactly one operation in each note settles it; a note that names no API and matches several contracts of its source names its API in the `api` attribute.

Check `W-OPERATION-AMBIGUOUS`, severity warning by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/W-OPERATION-AMBIGUOUS.md). The severity can be overridden per project or per repository.

## Applies to

- [Model query API](../api/model-query.md)
- [Entity](../objects/entity.md)
- [Link](../objects/link.md)
- [Build](../processes/build-pipeline.md)
