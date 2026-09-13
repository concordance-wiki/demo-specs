---
protocol: rest
exposure: internal
version: "1"
status: valid
---
# Canonical model

`dist/model.json`, the single file that describes the whole [model](../objects/inference/model.md): every later step reads it and none re-reads the sources. It is described by `model.schema.json`, published with the core package, and holds five blocks plus the two neighbourhoods: `build`, the only dated block, with the tool version, the timestamp, the fingerprint of the merged profile, one entry per source with its commit, whether links across sources were resolved and the contracts imported; `entities`, one object per note with its identifier, type, title, locale, application, domain, type origin, attributes and source; `links`, one object per source, target and relation triple with its combined confidence and every provenance; `findings`, the same array as the build log; `candidates`, the recurring expressions, the schemas of the imported contracts and the pairs of twin resources; `neighbours`, the best co-occurrence neighbours per entity; `displayed_neighbourhood`, the one-hop neighbours shown on every page. Keys are sorted at every depth, and a model read back refuses anything the schema does not describe.

The file is the interface between the build and everything after it: the rendering, the linter in global scope, which fetches the published model of the wiki with the validators the server gave, the Cypher export, and the future service. Its schema is part of what a version of the tool commits to.

## Consumers

- [Build](../processes/ingestion/build-pipeline.md)
- [Lint](../processes/quality/lint.md)
- [Home](../screens/pages/home.md)
- [Entity page](../screens/pages/entity-page.md)
- [Search](../screens/pages/search.md)

## Objects

- [Build](../objects/ingestion/build.md)
- [Entity](../objects/inference/entity.md)
- [Link](../objects/inference/link.md)
- [Finding](../objects/quality/finding.md)
- [Candidate](../objects/inference/candidate.md)
- [Neighbourhood](../objects/inference/neighbourhood.md)
