---
date: 2026-09-12
nature: technical
status: accepted
---
# Core, plugins, preset

The core reads markdown and produces JSON and depends on no office format nor system tool. Readers, converters, importers, viewers and heavy projections are plugins declared in the configuration. The unscoped `concordance` package is the preset that enables all of them.

## Affects

- [Resource](../../objects/ingestion/resource.md)
- [Build](../../processes/ingestion/build-pipeline.md)
- [Lint](../../processes/quality/lint.md)
