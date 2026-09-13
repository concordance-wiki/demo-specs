---
date: 2026-09-12
nature: technical
status: accepted
---
# Links are authoritative

A markdown link to another note is the strongest relation the tool knows: confidence 1.00, above anything inferred, and a frontmatter reference comes next at 0.90. What an author wrote is never overturned by what the tool recognised: the relation of a mapped section or of a typed attribute stands, inference only fills what nobody declared, and the page tells a written link from a recognised word by the way it is drawn. A link to a missing file is an error, a link to a document attaches it, a link from a note to itself yields nothing, and several links to one target are one link with several provenances.

## Affects

- [Link](../objects/link.md)
- [Entity page](../screens/entity-page.md)
- [Mentions panel](../screens/mentions-panel.md)
- [Build](../processes/build-pipeline.md)
