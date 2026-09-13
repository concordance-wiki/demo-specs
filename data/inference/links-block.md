---
type: data_object
business_object: objects/inference/link
fields: [from, to, relation, attributes, confidence, provenance]
schema: model.schema.json
---
# Links block

The `links` block of the [canonical model](../../api/canonical-model.md): one object per source, target and relation triple, in that order, with the attributes of the relation, the combined confidence and the complete list of what every method recorded, each provenance with its method, file, line, section and context. The Cypher export writes one relationship per row with its confidence and its distinct methods.
