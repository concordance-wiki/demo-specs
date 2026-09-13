---
type: data_object
business_object: objects/inference/entity
fields: [id, type, title, locale, application, domain, type_origin, attributes, source, aliases, status, summary]
schema: model.schema.json
---
# Entities block

The `entities` block of the [canonical model](../../api/canonical-model.md): one object per [entity](../../objects/inference/entity.md), in identifier order, with its identifier, type, title, locale, the application and domain it is filed under when known, the origin of its type, the frontmatter keys that are not common attributes, and its source with the name, path and line of the note. The Cypher export writes one node per row.
