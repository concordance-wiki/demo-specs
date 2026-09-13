---
aliases: [W-REF-UNRESOLVED]
severity: warning
---
# Unresolved reference

A value of a reference-typed frontmatter attribute (`reads`, `roles`, `rules`, `consumers`, `affects`, `broader` among others) matches no note by identifier, by path relative to the source root or by exact title, or matches several notes by title. No link is recorded for that value; the other values of the attribute are unaffected. The fix is to write the identifier, the path or the exact title of an existing note, the identifier or the path when a title is shared: this repository names its roles by path, `roles/reader`, because the glossary carries a term with the same title as one of them. A note found under a type the attribute does not accept is a [relation outside the matrix](relation-outside-the-matrix.md), not an unresolved reference.

Check `W-REF-UNRESOLVED`, severity warning by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/W-REF-UNRESOLVED.md). The severity can be overridden per project or per repository.

## Applies to

- [Entity](../objects/entity.md)
- [Link](../objects/link.md)
- [Build](../processes/build-pipeline.md)
