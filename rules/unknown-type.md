---
aliases: [W-TYPE-UNKNOWN]
severity: warning
---
# Unknown type

The type cascade gave a note a type that neither the default profile nor the project profile declares: a source `type`, a typing rule or a frontmatter `type` names a slug that does not exist. The note is kept and treated as a document, and its type origin records where the unknown slug came from, so that the site shows it. The fix is a type of the profile, a declaration in the project profile, or a correction of the rule or the frontmatter.

Check `W-TYPE-UNKNOWN`, severity warning by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/W-TYPE-UNKNOWN.md). The severity can be overridden per project or per repository.

## Applies to

- [Entity](../objects/entity.md)
- [Build](../processes/build-pipeline.md)
