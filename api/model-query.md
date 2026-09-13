---
protocol: rest
exposure: internal
version: "1"
status: draft
contract: contracts/model-query.openapi.json
---
# Model query API

The HTTP face of the future long-running service: it answers questions about the [model](../objects/inference/model.md) of the last build for the screens that cannot read `model.json` directly. Nothing of it exists in the command line of this version; the [contract](contracts/model-query.openapi.json), an OpenAPI 3.1 document kept next to this note, declares three operations, `listEntities` (`GET /entities`), `getEntity` (`GET /entities/{id}`) and `searchModel` (`GET /search`), and four schemas, `Entity`, `Link`, `Finding` and `SearchHit`. The build imports the operations as operations of this API and attaches to each one the operation note that describes it, following the [operation matching](../rules/engine/operation-matching.rule.md) rule; an operation left without a note keeps the properties of the contract only, and the [API page](../screens/pages/api-page.md) shows the contract in its viewer.

## Consumers

- [Entity page](../screens/pages/entity-page.md)
- [Search](../screens/pages/search.md)

## Objects

- [Entity](../objects/inference/entity.md)
- [Link](../objects/inference/link.md)
- [Finding](../objects/quality/finding.md)
