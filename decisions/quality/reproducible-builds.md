---
date: 2026-09-13
nature: technical
status: accepted
---
# Reproducible builds

Two builds of the same sources write the same bytes. Every list is sorted canonically before it is written, findings by check, source, path, line and message, entities by identifier, links by their triple, provenances by method, path and line; a step that runs in parallel sorts its results before writing them; nothing random is ever written, and the only timestamp is the `at` field of the build log, also the `at` of the `build` block of the model, pinned by `SOURCE_DATE_EPOCH` following the reproducible-builds convention. A double-build test and a continuous-integration step compare every file of two builds of the golden corpus, so that a published site can be diffed against the previous one.

## Affects

- [Build](../../objects/ingestion/build.md)
- [Model](../../objects/inference/model.md)
- [Build pipeline](../../processes/ingestion/build-pipeline.md)
