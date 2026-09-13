---
date: 2026-09-12
nature: technical
status: accepted
---
# Static first

The build is a pipeline command that produces a static site. The main content of every page is in the served HTML, the site works over `file://`, and fragments load on demand from JSON files. An optional service will consume the same model later; nothing in the site depends on it.

## Affects

- [Model](../../objects/inference/model.md)
- [Build](../../processes/ingestion/build-pipeline.md)
