---
lifecycle: [built, validated, rendered]
---
# Model

The single serialised result of a build: the `build` block with the tool version, timestamp, profile fingerprint and per-source commits; every [entity](entity.md); every [link](link.md) with its provenances; every [finding](../quality/finding.md); the term candidates and duplicate candidates; the bounded neighbourhoods. Canonically sorted, validated by a published schema, byte-identical from one build to the next on unchanged sources. The site is rendered from it without reading the sources again, and a Cypher export is provided.
