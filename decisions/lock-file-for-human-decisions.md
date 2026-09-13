---
date: 2026-09-13
nature: technical
status: accepted
---
# Lock file for human decisions

`concordance.lock.yaml`, in the configuration repository, records what a person decided and the tool must not reconsider: accepted and rejected links, merged and separated twin resources, rejected term candidates. The keyword discovery honours `rejected_terms` and the reconciliation of twin resources the `merged` and `separated` pairs it is given, but the build does not read the file yet: the configuration validator warns that `lock` is accepted and ignored. Nothing is ever written into a knowledge repository, and a decision lives next to the configuration, versioned, reviewed like any change.

## Affects

- [Candidate](../objects/candidate.md)
- [Link](../objects/link.md)
- [Build](../processes/build-pipeline.md)
