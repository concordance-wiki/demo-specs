---
lifecycle: [ingested, converted, reconciled]
---
# Resource

A file read from a source: a markdown note, a document, a slide deck, a transcript, a contract. A resource carries its path, commit and date, and, for documents, the metadata extracted by a reader, the PDF produced by a converter and the text extracted from that PDF, page by page, or the cues of a transcript with their timecodes; an office document never gives its text any other way, so that one extraction path serves every format. Twin resources of the same document are grouped into one [entity](../inference/entity.md) with several representations when their reconciliation score is high enough.
