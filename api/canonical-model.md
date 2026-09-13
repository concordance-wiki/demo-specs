---
protocol: rest
exposure: internal
version: "1"
status: valid
---
# Canonical model

`dist/model.json`, the single file that describes the whole [model](../objects/model.md): every later step reads it and none re-reads the sources. It is described by `model.schema.json`, published with the core package, and holds five blocks plus the two neighbourhoods: `build`, the only dated block, with the tool version, the timestamp, the fingerprint of the merged profile, one entry per source with its commit, whether links across sources were resolved and the contracts imported; `entities`, one object per note with its identifier, type, title, locale, application, domain, type origin, attributes and source; `links`, one object per source, target and relation triple with its combined confidence and every provenance; `findings`, the same array as the build log; `candidates`, the recurring expressions, the schemas of the imported contracts and the pairs of twin resources; `neighbours`, the best co-occurrence neighbours per entity; `displayed_neighbourhood`, the one-hop neighbours shown on every page. Keys are sorted at every depth, and a model read back refuses anything the schema does not describe.

The file is the interface between the build and everything after it: the rendering, the linter in global scope, which fetches the published model of the wiki with the validators the server gave, the Cypher export, and the future service. Its schema is part of what a version of the tool commits to.

## Consumers

- [Build](../processes/build-pipeline.md)
- [Lint](../processes/lint.md)
- [Home](../screens/home.md)
- [Entity page](../screens/entity-page.md)
- [Search](../screens/search.md)

## Objects

- [Build](../objects/build.md)
- [Entity](../objects/entity.md)
- [Link](../objects/link.md)
- [Finding](../objects/finding.md)
- [Candidate](../objects/candidate.md)
- [Neighbourhood](../objects/neighbourhood.md)
