---
date: 2026-09-13
nature: technical
status: accepted
---
# Type-driven neighbour order

The neighbourhood panel of a page lists neighbour types in a priority order declared per type in the profile: operations first on an API, accessed objects on a screen, what it applies to on a rule. Every displayed neighbour carries the rank of its type; unlisted types and keyword pages share the last rank, confidence decides within a group, and the panel is truncated after this ordering. A type without a declaration keeps the order by decreasing confidence. The order is profile data, never a condition in a template: the panel renders the list as received and separates the groups by rank alone.

## Affects

- [Entity page](../../screens/pages/entity-page.md)
- [Model](../../objects/inference/model.md)
- [Build](../../processes/ingestion/build-pipeline.md)
