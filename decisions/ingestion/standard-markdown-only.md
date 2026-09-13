---
date: 2026-09-12
nature: technical
status: accepted
---
# Standard markdown only

Concordance reads CommonMark, GFM and optional YAML frontmatter, nothing else. No wikilink, no proprietary tag, no directive: every file stays readable without the tool, and structured information goes through frontmatter, headings and lists.

## Affects

- [Entity](../../objects/inference/entity.md)
- [Resource](../../objects/ingestion/resource.md)
- [Build](../../processes/ingestion/build-pipeline.md)
- [Lint](../../processes/quality/lint.md)
