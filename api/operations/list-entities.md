---
api: api/model-query
operation_id: listEntities
method: GET
path: /entities
style: http
status: draft
---
# List the entities

Returns the entities of the last build, in identifier order, with the same fields as the [entities block](../../data/inference/entities-block.md) of the model; a screen that cannot read `model.json` directly will page through them here. The operation is declared by the OpenAPI contract of the [model query API](../model-query.md) and exists nowhere else in this version.

## Consumers

- [Entity page](../../screens/pages/entity-page.md)
