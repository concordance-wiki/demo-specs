---
aliases: [W-ATTRIBUTE-UNKNOWN]
severity: warning
---
# Unknown attribute

A frontmatter key is declared neither by the type of the note nor among the common attributes of the profile. The value is kept as written in the model and shown in the side panel of the page, but nothing interprets it: it produces no relation and no typed display. Most often a typo in a key, or an attribute the project profile has yet to declare.

Check `W-ATTRIBUTE-UNKNOWN`, severity warning by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/W-ATTRIBUTE-UNKNOWN.md). The severity can be overridden per project or per repository.

## Applies to

- [Entity](../../objects/inference/entity.md)
- [Build](../../processes/ingestion/build-pipeline.md)
