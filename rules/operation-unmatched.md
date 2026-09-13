---
aliases: [W-OPERATION-UNMATCHED, note ahead of the contract]
severity: warning
condition: an endpoint note names an API whose contract was imported and matches none of its operations
---
# Operation unmatched

An operation note that names an API with an imported contract, in its `api` attribute or through a markdown link, and that none of the three rungs of the [operation matching](operation-matching.md) attaches to an operation of that contract. One of two things is true: the operation disappeared from the contract and the note describes something that no longer exists, or the note is ahead of the contract and describes an operation the next version will declare. The build cannot tell which, so the finding says both, and the author decides: retire the note or point it at the operation that replaced its own, or keep it with the `operation_id` to come until the contract catches up. A note that names no API is not reported: it is a candidate for every contract of its source and may describe an API without a contract. A note taken in an ambiguity is reported by the matching rule instead.

The gap is measured in the other direction on the page of the API: the [contract viewer](../screens/contract-viewer.md) lists every operation of the contract and flags the ones no note describes yet, with their count. Together, the finding and the flag give the documentation debt of an API: what the notes say that the contract does not, and what the contract declares that the notes do not.

Check `W-OPERATION-UNMATCHED`, severity warning by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/W-OPERATION-UNMATCHED.md). The severity can be overridden per project or per repository.

## Applies to

- [Model query API](../api/model-query.md)
- [Entity](../objects/entity.md)
- [Link](../objects/link.md)
- [Build](../processes/build-pipeline.md)
