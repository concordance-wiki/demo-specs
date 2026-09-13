---
aliases: [operation attachment, three rungs]
severity: warning
condition: an endpoint note written by hand and an operation imported from a contract describe the same operation
---
# Operation matching

An operation note attaches to the operation imported from the contract of its API on three rungs, tried in order, the first that matches winning: the `operation_id` of the frontmatter against the operation identifier of the contract; the `method` and `path` pair (or `port` and the title for a SOAP operation) against the operation's; the title of the note in comparison form, spaces and punctuation ignored, against the operation title or its identifier. The note names its API in the `api` attribute or through a markdown link; a note that names none is a candidate for every API of its source that declares a contract.

A matched note absorbs the operation: it keeps its identifier, its markdown and its frontmatter, takes the properties the contract declares (`method`, `path`, `summary`, `style`, `port`, `binding`) when it does not set them, lists the contract as a representation next to its own file, and the `exposes` link of the API points at it. The imported operation no longer exists as a separate entity. Two notes claiming one operation, or one note matching several operations, attach nothing and are reported by check `W-OPERATION-AMBIGUOUS`, severity warning by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/W-OPERATION-AMBIGUOUS.md). The [writing guide](https://github.com/concordance-wiki/concordance/blob/main/docs/guides/writing-notes.md#operation-notes) shows the frontmatter keys.

## Applies to

- [Model query API](../api/model-query.md)
- [Entity](../objects/entity.md)
- [Link](../objects/link.md)
- [Build](../processes/build.md)
