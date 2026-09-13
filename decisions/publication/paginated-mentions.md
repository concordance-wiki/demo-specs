---
date: 2026-09-12
nature: technical
status: accepted
---
# Paginated mentions

The first twenty mentions of an entity are in the served HTML; the rest loads from a JSON fragment specific to that entity. Never a global index.

The fragment is `fragments/<id>.mentions.json`, written for every entity another note cites. Under two hundred mentions in all, the rest also travels in the page inside a data block, so that revealing it costs no request; beyond, the page fetches the fragment on demand, and over `file://`, where a page may not fetch, it links to it. The threshold of twenty is `build.mentions_inline`.

## Affects

- [Entity](../../objects/inference/entity.md)
- [Mentions panel](../../screens/panels/mentions-panel.md)
- [Build](../../processes/ingestion/build-pipeline.md)
