---
aliases: [W-TITLE-SHARED]
severity: warning
---
# Shared title

At least three entities of one source carry the same title, case and spaces set aside: the trace of a template heading that every file kept, such as a word processor export whose first section reads "Purpose of the document". Nothing tells the pages apart in the search results, the trees or the related pages.

A note with several H1s never reaches the rule: its H1s head its sections and its file name titles it. The rule catches a template with a single H1 that is a section, and documents whose title property the template filled in once for all; `headings: sections` on the [source](../../objects/ingestion/source.md) settles the first case.

Check `W-TITLE-SHARED`, severity warning by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/W-TITLE-SHARED.md). The severity can be overridden per project or per repository.

## Applies to

- [Source](../../objects/ingestion/source.md)
- [Resource](../../objects/ingestion/resource.md)
- [Build](../../processes/ingestion/build-pipeline.md)
