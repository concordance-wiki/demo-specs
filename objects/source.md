---
lifecycle: [declared, fetched, ingested]
---
# Source

A repository or a local folder declared in `sources:` of the configuration: a unique name that prefixes every identifier from it, a `git` URL cloned at depth 1 on its `ref` or a local `path`, its locale, its default application, whether it is a glossary, and its typing rules. The build fetches it into the pipeline cache without ever writing into it, records the commit of the ingestion in the `build` block of the [model](model.md), and goes on without it when it cannot be reached. Every [resource](resource.md) and every [entity](entity.md) knows its source.
