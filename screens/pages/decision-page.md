---
roles: [roles/publication/reader]
url_pattern: /{source}/{path}
status: valid
---
# Decision page

The page of an architecture decision: short, dated, with its consequences. Same shell as the [entity page](entity-page.md): the tree of the space on the left, the title and the panel where a reader expects them. A reader comes to check two things, whether the decision holds and since when, and finds them at the head of the panel; the rest of the page says what the decision changed.

A decision affects pages without being affected by them: its relations are almost all written, since a decision cites what it changes, and the page lists them as such.

## Today

The page stands on the shell of the [entity page](entity-page.md). When every note of the space carries a date, a `date` attribute or a file name that starts with one, the tree on the left groups the notes by year, newest first, each year counting its notes and leading to its list, the year of the page open on its notes in date order and the page marked; a space with an undated note keeps its folder tree. The breadcrumb reads "space › 2026 › title". Under the title, one chip reads the type and the status, "Decision · accepted", the status worded when it is one of the three the profile declares, proposed, accepted or superseded, and kept as written otherwise; then the identifier of the note and the day of the decision, from its `date` attribute, each left out when the note has none. Nothing else stands on the line: neither the change date nor the space.

The note follows as written, section by section, the three sections the convention asks for, context, decision and consequences, coming from the file itself. Under the note, one callout per session the model ties to the decision at either end of a [link](../../objects/inference/link.md), the `decisions` reference of a [meeting](meeting-page.md), a written link, or a decision whose note names the meeting: "Decided in session on 12 March. The exact passage is in the minutes, at 13:02.", the day being that of the meeting's note, the link leading to the last cue of the transcript of the meeting that names the decision, at the timecode the sentence quotes, or to the page of the meeting when no cue names it, "See the minutes."; the day is left out for a meeting without one. The callout points at the passage and never copies what was said. The foot of the article carries the path of the file with its edit link, without the legend of the marks, which the page does not draw.

The right panel opens on the properties of the decision, the status and the date first, the two things a reader comes to verify; then "Supersedes" and "Superseded by", from the `supersedes` links of the model at either end, so that a superseded decision names the one that replaces it and the replacing one names the one it replaces, whichever note wrote the reference, the `superseded_by` key of the note standing in when no note says `supersedes`; then "Session", naming the meetings. Under the rows, "4 keys: the status and the date are authoritative.", the count being that of the rows shown. The related pages are the [mentions panel](../panels/mentions-panel.md) built from the passages of the decision itself, the pages its text cites, with the pages that cite it, most passages first, under the note that a decision affects pages without being affected by them: its relations are almost all written. Last, the [neighbourhood map](../panels/neighbourhood-map.md) folded behind its line.

## Objects

- Reads: [entity](../../objects/inference/entity.md), [link](../../objects/inference/link.md)

## Actions

1. Open the minutes → [meeting page](meeting-page.md), at the cue that names the decision
2. Open the decision it supersedes, or the one that supersedes it → decision page
3. Open a related page → [entity page](entity-page.md)

## Rules

- [Broken link](../../rules/links/broken-link.rule.md)
- [Accessibility](../../rules/engine/accessibility.rule.md)
