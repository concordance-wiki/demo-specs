---
date: 2026-09-12
nature: technical
status: accepted
---
# Declarative profile

The meta-model is a YAML profile validated by a schema. The engine knows only types, attributes, relations and scores. Adding a type or a relation pair is a profile change, never a code change.

## Affects

- [Entity](../objects/entity.md)
- [Link](../objects/link.md)
- [Build](../processes/build-pipeline.md)
- [Lint](../processes/lint.md)
