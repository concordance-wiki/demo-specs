---
aliases: [W-API-CONSUMER-MISMATCH]
severity: warning
---
# Consumer mismatch

An API declares a consumer that never cites it, or a note cites an API that does not list it. One of the two is out of date. A declared consumer is an identifier, written in full or relative to the source of the API note; a note cites the API when a `serves` link between the two was read in that note, the API's own `consumers` attribute and `## Consumers` section being declarations rather than citations.

Check `W-API-CONSUMER-MISMATCH`, severity warning by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/W-API-CONSUMER-MISMATCH.md). The severity can be overridden per project or per repository.

## Applies to

- [Entity](../objects/entity.md)
- [Link](../objects/link.md)
- [Build](../processes/build-pipeline.md)
