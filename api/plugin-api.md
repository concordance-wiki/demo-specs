---
protocol: internal
exposure: internal
version: "1"
contract: https://github.com/concordance-wiki/concordance/blob/main/schemas/plugin.schema.json
---
# Plugin API

The versioned interface through which a plugin contributes to the tool: readers for file formats, converters, sources of entities such as contract importers, inference methods, checks, projections and user interface components. A plugin exports a manifest validated by the published schema; it is declared in the configuration and loaded in order into a deterministic registry. A plugin whose system dependency is missing disables itself with a [finding](../objects/finding.md).

## Consumers

- [Build](../processes/build-pipeline.md)
- [Lint](../processes/lint.md)

## Objects

- [Resource](../objects/resource.md)
- [Entity](../objects/entity.md)
- [Link](../objects/link.md)
- [Finding](../objects/finding.md)
