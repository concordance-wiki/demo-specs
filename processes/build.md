---
execution: service
triggers: [pipeline run, manual command]
---
# Build

`concordance build` chains eight deterministic steps. Each is testable in isolation and leaves an intermediate artefact in the cache. Two builds on unchanged sources produce byte-identical files.

## Steps

1. Validate the configuration and merge the profile; stop on any configuration error.
2. Ingest every source at depth 1, with cache and without writing anything into the repositories; record each file's commit and last-modified date.
3. Parse the markdown and frontmatter into sections, lists, links and code blocks.
4. Type every file through the cascade, compute identifiers, resolve application and domain; produce an [entity](../objects/entity.md) per note.
5. Convert office documents and transcripts through plugins, in parallel, cached by fingerprint; group twin resources into one [resource](../objects/resource.md).
6. Infer [links](../objects/link.md): written links, frontmatter references, section mentions, occurrences, co-occurrences; combine confidences; discover term candidates; compute the bounded neighbourhood.
7. Run every check of the registry and collect the [findings](../objects/finding.md).
8. Render the [model](../objects/model.md) into the site: one page per entity and per keyword, the JSON fragments, the search index, the previews.
