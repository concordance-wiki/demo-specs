---
lifecycle: [ingested, converted, reconciled]
---
# Resource

A file read from a source: a markdown note, a document, a slide deck, a transcript, a contract. A resource carries its path, commit and date, and, for documents, the metadata extracted by a reader, the preview produced by a converter and the text extracted from it. Twin resources of the same document are grouped into one [entity](entity.md) with several representations when their reconciliation score is high enough.
