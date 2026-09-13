---
lifecycle: [inferred, combined, rendered]
---
# Link

A typed relation between two [entities](entity.md), carrying a confidence between 0 and 1 and at least one provenance: method, file, line, section, context. When several methods produce the same source, target and relation, the confidences combine and every provenance is kept. Links are sorted canonically by source, target and relation in the [model](model.md).
