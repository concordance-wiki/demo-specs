---
date: 2026-09-13
nature: technical
status: accepted
---
# Purpose-built search index

The search index is built by the tool itself, with no dependency, rather than by the static search engine the specification first named. That engine's runtime fetches the chunks of its index over HTTP, and a page opened from the disk cannot fetch: it could not honour the requirement that the search works over `file://`, which the site as a whole honours.

The index is a set of classic scripts under `search/`, the one kind of resource every browser loads from a `file://` page as from a server: an entity table and one shard per two-character prefix, each calling a global with its name and its data when it runs. The search island exposes that global, adds a script tag for the file it needs and takes the callback; the same files serve both regimes, and no JSON is fetched. The island itself is a classic script for the same reason, where the other islands are modules. What the engine would have given is kept: an index generated at build, fragmented by prefix, loaded in pieces as the reader types, matching by prefix without typo correction, deterministic from one build to the next.

## Affects

- [Search](../screens/search.md)
- [Build](../processes/build-pipeline.md)
- [Static first](static-first.md)
