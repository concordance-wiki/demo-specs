---
aliases: [I-REL-AMBIGUOUS]
severity: info
---
# Ambiguous relation

A link between two entities fell back to the generic relation because no section, no typed attribute and no single allowed relation decided it. It is kept at a capped confidence. The finding is raised by the relation typing step and points at the note the link was read in, on the line of its first located provenance; a link that co-occurrences alone know raises nothing, since a co-occurrence names no file and is unnamed by nature.

Check `I-REL-AMBIGUOUS`, severity info by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/I-REL-AMBIGUOUS.md). The severity can be overridden per project or per repository.

## Applies to

- [Link](../../objects/inference/link.md)
- [Build](../../processes/ingestion/build-pipeline.md)
