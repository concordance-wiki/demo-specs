---
roles: [roles/publication/reader]
url_pattern: /{source}/{path}
status: valid
---
# Document page

The page of an office document, a slide deck, a report, a spreadsheet or a PDF, alone or merged with its note. Same shell as the [entity page](entity-page.md): the tree of the space on the left, the title and the panel where a reader expects them. Where the entity page puts the note, the document itself stands, its text and its notes one tab away, the original one click away.

A document brings passages, like a meeting: it enters the model through the pages that cite it and through the note someone wrote next to it.

## Today

The page stands on the shell of the [entity page](entity-page.md). When the space is a space of dated documents, more documents than notes among its pages and every one stating a date, the tree on the left groups the pages by year, the newest year first and the newest page first in it, the year of the page open and the page ruled and bold; a space with an undated page or mostly notes keeps its folder tree. The breadcrumb reads "space › 2026 › title". Under the title, a line names the kind of the file, read from its extension, "Presentation", the page count, the size of the original and the date, "24 pages · 4.2 MB · 12 March 2026"; the date is the one the file states when its reader read one, else the date of the last change in the repository, and a datum the corpus lacks is simply absent.

Three views follow behind the tabs "Document", "Extracted text" and "Related notes", with "Download the original" at the end of the bar, the original file placed next to the page as the previews are. The tabs are anchors and the page shows one view at a time without any script: the view of the tab followed, the one holding the position a citation lands on, else the document. The document view puts the strip of pages beside the rendering: numbered thumbnails, "01" to "24", the current one ruled in the accent, each leading to the text of its page and, once the viewer runs, showing that page; the [document viewer](../../viewers/document-viewer.md) opens as soon as its script runs, with its counter, its zoom and its find field over the extracted text, and the strip follows the page shown. Without JavaScript the browser shows the PDF itself in the same place, first page in view. Under the rendering, two notes: "Converted at publication, cached by fingerprint" and "The original stays downloadable". The extracted text view gives the text of every page in a disclosure block, anchored the way the [mentions panel](../panels/mentions-panel.md) cites it. The notes view renders the note merged with the document as on the entity page, with its legend, or says that no note describes the document yet. The path of every file follows, with the edit link of the note.

The right panel opens on "Properties": the type, the author as the file states it, the pages and the date, with the note "Read from the file, distinct from the repository date." when the date was; a property the file does not state keeps its row, empty. "Same document, three files" lists the files that make the page, the original by its extension, the PDF as the preview, the note as the session notes, under the note "Grouped by folder, date and textual overlap — a single entry in the index." The related pages are the [mentions panel](../panels/mentions-panel.md). Last, the [neighbourhood map](../panels/neighbourhood-map.md) folded behind its line.

## Objects

- Reads: [entity](../../objects/inference/entity.md), [representation](../../objects/ingestion/representation.md), [resource](../../objects/ingestion/resource.md), [link](../../objects/inference/link.md)

## Actions

1. Follow a tab → the view of the document, its text or its notes
2. Open a page of the strip → its text, and its page in the viewer once it runs
3. Download the original → the copy next to the page
4. Open a related page → [entity page](entity-page.md)

## Rules

- [Document without markdown](../../rules/documents/document-without-markdown.rule.md)
- [Conversion failed](../../rules/documents/conversion-failed.rule.md)
- [Duplicate candidate](../../rules/documents/duplicate-candidate.rule.md)
