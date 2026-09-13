---
api: api/model-query
operation_id: searchModel
method: GET
path: /search
style: http
status: draft
---
# Search the model

Returns the entities matching a query, scored as the search island of the site scores them, for a client that does not load the search index. Declared by the OpenAPI contract of the [model query API](../model-query.md); the static [search](../../screens/pages/search.md) of the site does not depend on it.

## Consumers

- [Entity page](../../screens/pages/entity-page.md)
