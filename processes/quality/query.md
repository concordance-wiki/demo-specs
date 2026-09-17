---
execution: mixed
triggers: [a question at the terminal, an agent before it answers or edits]
---
# Query

`concordance query` reads the [model](../../objects/inference/model.md) a [build](../ingestion/build-pipeline.md) wrote and answers what it knows, without the site and without a source: the note an expression names, where it is used with file and line, what it is linked to and how sure the model is, the decisions and sessions among those links. The same command runs the search of the site with its ranking and facets, lists the entities, counts them, names the spaces and the domains, lists the recurring expressions nobody defined and where they were read, what changed and with what, the findings the build recorded, and where a phrase is written or spoken in the documents and the transcripts. It answers a person at a terminal and, in the same words, an agent that puts the answer in its context.

## Steps

1. Find the model: the file `--model` names; else the output of the configuration of the working directory, or of `--config`; else the published model the lint configuration names for the [lint](lint.md) in global scope. Say which in the first line, with the instant of the build and its age; never fetch, compute or write beyond that.
2. Resolve the expression as the recognition reads a note: the identifier, then a title or an alias as written, then the same without case, accents and inflections, then a prefix; a term wins among several notes; otherwise list the candidates and exit with 1.
3. Read the section asked for, or every section: the note, its occurrences grouped by the note whose files hold them, its links with relation, direction, confidence and methods, the decisions and sessions among them; or walk the links to another note, to what lies within a radius, or to the provenances of a link; or search the index of the site, read from its files when they stand next to the model, else built from the model and its fragments; or answer a question of the whole corpus.
4. Bound every list and count the rest; write the answer as text in canonical order, or as JSON under the published schema.
5. Exit with 0 when something answered, 1 when nothing did or several candidates could, 2 when no model could be read or the options do not go together.
