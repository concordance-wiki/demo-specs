---
date: 2026-09-13
nature: technical
status: accepted
---
# No database

The graph is built in memory and serialised to `model.json`, canonically sorted and validated by a published schema; `concordance render` reads it without touching the sources, and a Cypher export is provided for those who want the graph elsewhere. No server, no database and no state between two builds other than the pipeline cache: the model is a file that a pipeline writes, commits, diffs and serves.

## Affects

- [Model](../../objects/inference/model.md)
- [Canonical model](../../api/canonical-model.md)
- [Build](../../processes/ingestion/build-pipeline.md)
