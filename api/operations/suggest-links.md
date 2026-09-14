---
api: api/model-query
operation_id: suggestLinks
status: draft
---
# Suggest links

Proposes the links a note could write, from the [candidates](../../objects/inference/candidate.md) of the last build: the objects a contract names without a note and the expressions the scan recognised without a definition. The [model query API](../model-query.md) does not declare the operation yet: this note is ahead of its contract, which the [operation unmatched](../../rules/contracts/operation-unmatched.rule.md) rule reports until the contract catches up, and the [API page](../../screens/pages/api-page.md) lists it among the gaps, described, absent from the contract.

## Consumers

- [Entity page](../../screens/pages/entity-page.md)
