---
domain: quality
protocol: internal
exposure: internal
version: "1"
contract: https://github.com/concordance-wiki/concordance/blob/main/schemas/plugin.schema.json
---
# Plugin API

The versioned interface through which a plugin contributes to the tool: readers for file formats, converters, sources of entities such as contract importers, inference methods, checks, projections and user interface components. A plugin exports a manifest validated by the published schema; it is declared in the configuration and loaded in order into a deterministic registry. A plugin whose system dependency is missing disables itself with a [finding](../objects/quality/finding.md).

## Consumers

- [Build](../processes/ingestion/build-pipeline.md)
- [Lint](../processes/quality/lint.md)

## Objects

- [Resource](../objects/ingestion/resource.md)
- [Entity](../objects/inference/entity.md)
- [Link](../objects/inference/link.md)
- [Finding](../objects/quality/finding.md)
