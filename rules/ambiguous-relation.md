---
aliases: [I-REL-AMBIGUOUS]
severity: info
---
# Ambiguous relation

A link between two entities fell back to the generic relation because no section, no typed attribute and no single allowed relation decided it. It is kept at a capped confidence. The finding points at the note the link was read in, on the line of its first located provenance.

Check `I-REL-AMBIGUOUS`, severity info by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/I-REL-AMBIGUOUS.md). The severity can be overridden per project or per repository.

## Applies to

- [Link](../objects/link.md)
- [Build](../processes/build-pipeline.md)
