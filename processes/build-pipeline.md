---
execution: service
triggers: [pipeline run, manual command]
---
# Build pipeline

`concordance build` chains its steps in a fixed order and produces one [build](../objects/build.md). Each step is a pure function of the outputs of the previous ones and reports its anomalies as [findings](../objects/finding.md); no content anomaly stops the chain. Two builds on unchanged sources produce byte-identical files.

## Steps

1. Validate the configuration, merge the profile and load the declared plugins; stop on a configuration error, an invalid profile or a plugin that cannot be loaded.
2. Ingest every source at depth 1, with cache and without writing anything into the repositories; record each file's commit and last-modified date.
3. Parse the markdown and frontmatter into sections, lists, links and the text units the recognition reads.
4. Read every other file a reader or a converter of the plugins accepts, in parallel: the reader gives its metadata and, for a transcript, its cues with their timecodes; the converter gives its PDF, cached by the fingerprint of the file, and the text of every page of that PDF, the only text an office document ever contributes. A conversion that fails is a [finding](../objects/finding.md) and the document stays a download.
5. Type every note and every document through the cascade, compute identifiers (a document keeps its extension), resolve application and domain; produce an [entity](../objects/entity.md) per note and per document, the metadata of a document as its attributes.
6. Run the source plugins on the typed entities: the contract importers read the contract each API note declares and add its endpoints, their `exposes` [links](../objects/link.md), the candidate objects and one contract record per contract.
7. Build one recognition dictionary per locale from the titles and aliases of the entities, glossary sources first, stopwords excluded; flag the homonyms.
8. Scan every note and every page of every document with the dictionary of its locale and record each occurrence with its line, position, section and context; in a document the line is the number of the page, slide or cue and the section its label, so that a mention cites `slide 3` or a timecode.
9. Produce the [links](../objects/link.md): written links, frontmatter references, mentions in mapped sections and in prose, co-occurrences per paragraph with the bounded neighbourhood.
10. Combine the confidences of every link into one link per source, target, relation and attributes, every provenance kept.
11. Type the relations: keep a declared relation the profile allows between the two types and drop the others, name a `related` link from its type pair or leave it `related`, capped and reported unless co-occurrence alone knows it.
12. Discover the recurring expressions without a note in the notes and in the pages of the documents, headings and section labels left out as titles rather than usage, flag the undefined terms and publish the keyword pages above the threshold as entities.
13. Reconcile the notes and documents that look like twin [resources](../objects/resource.md), by declaration, base name, the title a reader reports against the heading of a note, or their texts: merge the groups above the merge threshold into one entity with several representations, the note's identifier when it has one, report the pairs above the candidate threshold; report every document left without a markdown representation.
14. Run every check of the registry on the model, enrich the findings of every step with the same registry and sort them once.
15. Write the [model](../objects/model.md) and the build log, then one fragment per entity next to them: the note rendered to sanitised HTML section by section, its written links turned into page links, its plain text and the text of every page of its documents for the search index, the original file and the PDF of each document kept for the page, or the passages of a keyword page. Nothing after this step reads a source.
16. Resolve the theme: the components the plugins contribute and the project's `theme.yaml`, whose labels override the message catalogue of the project locale.
17. Render the site from the model, the fragments, the profile and the theme, as `concordance render` does alone: the [home page](../screens/home.md), one page per entity and per keyword page at the address of its identifier, the [document viewer](../screens/document-viewer.md) on the page of a document with its files placed next to it, the [alphabetical index](../screens/alphabetical-index.md), the [to-do page](../screens/todo-page.md), the search index and the assets, every link relative to its page so that the site works over `file://`.
18. Measure every page against the 150 kB budget and run the static accessibility checks; print the pages written, the size of each island bundle, the largest page and the findings, as warnings that never fail the build.
