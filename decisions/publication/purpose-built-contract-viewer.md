---
date: 2026-09-13
nature: technical
status: accepted
---
# Purpose-built contract viewer

The contract of an API is shown by a viewer the tool builds itself, rather than by the interactive API console the specification first named for OpenAPI contracts. That console weighs more than the page budget of the site, expects to fetch the specification over the network, and offers to call the API from the page; the site is static, works from the disk, keeps every page under its budget and never calls the systems it documents.

The viewer is an island of the default theme, the first user interface component it contributes through the plugin API, and reads a view the build writes from the cached contract: the operations with their parameters, request and responses, and the schemas or types they reference, in one shape for OpenAPI and WSDL alike. The page serves the operations as a plain list and a link to that view; the island fetches the view when the reader asks and renders an operation list and a schema explorer, read-only. The original contract stays downloadable at its URL or from a copy next to the page. What the console would have given beyond that, trying an operation against a server, is out of scope by design.

## Affects

- [Contract viewer](../../viewers/contract-viewer.md)
- [Entity page](../../screens/pages/entity-page.md)
- [Build](../../processes/ingestion/build-pipeline.md)
- [Static first](static-first.md)
