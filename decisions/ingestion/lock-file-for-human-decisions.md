---
date: 2026-09-13
nature: technical
status: accepted
---
# Lock file for human decisions

`concordance.lock.yaml`, in the configuration repository, records what a person decided and the tool must not reconsider: accepted and rejected links, merged and separated twin resources, rejected term candidates. The build reads the file the `lock` key names, validates it against its schema and stops on a missing or invalid one, as on a configuration error: a decision is never dropped in silence. The keyword discovery honours `rejected_terms`, compared on the normalised form of the language pack, and the reconciliation of twin resources the `merged` and `separated` pairs, whatever the score; the links are recorded for a later version, and the configuration validator says so. The build log counts the decisions applied. Nothing is ever written into a knowledge repository, and a decision lives next to the configuration, versioned, reviewed like any change.

## Affects

- [Candidate](../../objects/inference/candidate.md)
- [Link](../../objects/inference/link.md)
- [Build](../../processes/ingestion/build-pipeline.md)
