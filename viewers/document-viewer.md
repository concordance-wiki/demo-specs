---
roles: [roles/publication/reader]
url_pattern: /{source}/{path}#document-1
status: valid
---
# Document viewer

The section of the [entity page](../screens/pages/entity-page.md) of a document that is not a note: a slide deck, a PDF, a transcript, or a note merged with one of them. It offers the file itself, its text and, on demand, the pages of its PDF, without ever loading the viewer with the page. The [document page](../screens/pages/document-page.md) of an office document opens the same viewer as soon as its script runs.

## Today

One section per file of the entity that is not its note, in path order, after the article of the note and before the side panel, headed "Document" followed by the file name. Its first line links the original file for download, at the copy the build placed next to the page, and, when the conversion produced a PDF, "Open the PDF", a plain link the browser follows on its own. A rail of positions comes next: one entry per page, slide or cue of the document, named `slide 3` or by its timecode, captioned by the first line of its extracted text, and leading to that text; once the viewer runs, the entry also shows that page in it and the entry of the page shown is marked. Under the rail, "Extracted text" gives the text of every position in a disclosure block, the first one open, each block anchored the way the [mentions panel](../screens/panels/mentions-panel.md) cites it, so that a mention read on slide three lands on slide three. A document without extracted text says so; the download stays.

The viewer itself is an island served inert: a hidden button and an empty container. Its script reveals "Open the viewer"; the first click imports the viewer bundle, a build of pdf.js the page never references in a script, and opens the PDF in the container: a toolbar with the counter, `3 / 12`, the zoom between its two signs, "−" and "+", over fixed steps, and the field "⌕ in the document" that searches the extracted text of the positions, jumps to the first matching page and says how many others match; under it, the page drawn on a canvas on its stage. The pages are reached through the rail, which drives the viewer once it is open. The button then closes and reopens the viewer. When the bundle cannot be imported, as on a page opened from the disk in a browser that refuses module scripts there, the container shows a sentence saying so with a link to the PDF instead. The viewer and its worker are built only for a site that shows a PDF, are announced in the build summary with their size, and change nothing in the scripts a page loads on its own.

The thumbnails of the slides are the captions of the rail for now: an image per slide will replace them when the converter produces thumbnails. The text shown and searched is the text the build extracted from the PDF, cut at `build.extracted_text_max_chars` in all; the download gives the rest.

## Objects

- Reads: [resource](../objects/ingestion/resource.md), [entity](../objects/inference/entity.md)

## Actions

1. Download the file → the copy next to the page
2. Open the PDF → the PDF as the browser shows it
3. Open the viewer → the pages of the PDF, page by page, with zoom and find
4. Open a position of the rail → its extracted text, and its page once the viewer runs

## Rules

- [Document without markdown](../rules/documents/document-without-markdown.rule.md)
- [Conversion failed](../rules/documents/conversion-failed.rule.md)
- [Accessibility](../rules/engine/accessibility.rule.md)
