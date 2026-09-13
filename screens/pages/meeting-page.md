---
roles: [roles/publication/reader]
url_pattern: /{source}/{path}
status: valid
---
# Meeting page

The page of a working session that exists as a note, a transcript and a deck, read as one page. Same shell as the [entity page](entity-page.md): the tree of the space on the left, the title and the panel where a reader expects them. Where the entity page puts the note, the three files stand as tabs; what the meeting produced, a decision written elsewhere, is named in a callout rather than mixed into the text.

A meeting brings passages, not concepts: it enters the model only through the pages it cites and the decisions someone took the trouble to write as notes of their own.

## Today

The page stands on the shell of the [entity page](entity-page.md). When every note of the space carries a date, a `date` attribute or a file name that starts with one, the tree on the left groups the notes by year and month, newest first, each counting its notes, the year and the month of the page open and the page marked; a space with an undated note keeps its folder tree. The breadcrumb reads "space › March 2026 › title". Under the title, a line names the type, the duration, from the `duration` attribute of the note or the timecode of the last cue of the transcript, "1 h 12", and the participants: "Pseudonymised participants" when the configuration enables pseudonymisation, else how many the note declares.

The representations follow as tabs, one per file the build grouped into the page: the transcript, the notes, the slide deck or another converted document, with the mention "Grouped automatically" when the [twin-resource reconciliation](../../decisions/inference/minhash-for-twin-resources.md) merged them. The tabs are anchors and the page shows one panel at a time without any script: the panel of the tab followed, the one holding the position a citation lands on, else the first; a browser without the selector the stylesheet relies on shows them one under the other. The transcript reads as timestamped lines, "12:04 Participant-1 — …", the speaker of every cue carried from the transcript reader and pseudonymised with the text, each timecode an anchor at the position the [mentions panel](../panels/mentions-panel.md) cites, the file to download under the lines and, when pseudonymisation applied, the note that the names are replaced at publication by stable pseudonyms and that the mapping is never published. The notes are rendered as on the entity page, with the legend of written links and recognised words; a deck goes through the [document viewer](../../viewers/document-viewer.md), rail and viewer included.

After the tabs, the callout "Decision taken here" links the decisions the model ties to the meeting at either end of a link: the `decisions` reference of the note, a written link, or a decision whose note names the meeting; it is absent when nothing links them. The path of every file follows, with the edit link of the note.

The right panel lists the properties of the meeting, the date, the duration, the space linking to the file tree of the [home](home.md), and the files, "3 grouped", with why the build grouped them under the list, read from the pairs the reconciliation scored, "same folder, same base name, same commit, high textual overlap", else the criterion recorded on the [entity](../../objects/inference/entity.md). The related pages are the [mentions panel](../panels/mentions-panel.md) built from the passages of the meeting itself, the pages its minutes, its transcript and its deck evoke, most passages first, each excerpt leading to the cue or the line on this page, with the pages that cite the meeting, under the note that a meeting does not enter the model: it brings passages, and sometimes a decision someone took the trouble to write elsewhere. Last, the [neighbourhood map](../panels/neighbourhood-map.md) folded behind its line.

## Objects

- Reads: [entity](../../objects/inference/entity.md), [representation](../../objects/ingestion/representation.md), [link](../../objects/inference/link.md)

## Actions

1. Follow a tab → the panel of that representation
2. Open the decision → [entity page](entity-page.md)
3. Open a related page → [entity page](entity-page.md)
4. Download a file → the original file

## Rules

- [Duplicate candidate](../../rules/documents/duplicate-candidate.rule.md)
- [Document without markdown](../../rules/documents/document-without-markdown.rule.md)
