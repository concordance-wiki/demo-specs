---
date: 2026-09-12
nature: technical
status: accepted
---
# Core, plugins, preset

The core reads markdown and produces JSON and depends on no office format nor system tool. Readers, converters, importers, viewers and heavy projections are plugins declared in the configuration. The unscoped `concordance` package is the preset that enables all of them.

## Affects

- [Resource](../objects/resource.md)
- [Build](../processes/build.md)
- [Lint](../processes/lint.md)
