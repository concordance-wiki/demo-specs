---
date: 2026-09-13
nature: technical
status: accepted
---
# Single extraction path

The text of an office document comes from the PDF the converter produced, never from the document's own format. A reader still opens the original file, for its native properties, but the words that enter the search index, the recognition and the comparison of twin resources are read from the PDF, page by page, with one PDF library; a PDF given as a source goes through the same reading, and a transcript, which no converter touches, gives its cues.

One path means one behaviour to test and one place to fix: the position of every word is a page or a slide of the PDF the reader will open in the [document viewer](../screens/document-viewer.md), so a mention cites what the reader sees, and a format is supported for text as soon as it is supported for conversion. The price is accepted: without the converter, or when a conversion fails, an office document has no text and stays a download, and the count of such documents is what the fail-on policy of the build watches.

## Affects

- [Document viewer](../screens/document-viewer.md)
- [Build](../processes/build-pipeline.md)
- [Resource](../objects/resource.md)
- [Document without markdown](../rules/document-without-markdown.md)
