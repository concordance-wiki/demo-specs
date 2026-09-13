---
aliases: [E-META-REL]
severity: error
---
# Relation outside the matrix

A declared relation joins two types the profile does not allow for it. The link is dropped from the model.

Check `E-META-REL`, severity error by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/E-META-REL.md). The severity can be overridden per project or per repository.

## Applies to

- [Link](../objects/link.md)
- [Build](../processes/build-pipeline.md)
- [Lint](../processes/lint.md)
