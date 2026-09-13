---
business_object: objects/finding
fields: [check, severity, source, path, line, entity, message, remediation]
schema: model.schema.json
---
# Findings block

The `findings` block of the [canonical model](../api/canonical-model.md), the same array as the build log: one object per [finding](../objects/finding.md), sorted by check, source, path, line and message, with the identifier of its check, its severity, the file and line when there is one, the entity concerned, the message and the remediation.
