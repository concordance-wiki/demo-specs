---
date: 2026-09-13
nature: technical
status: accepted
---
# ICU message catalogues

Every label of the generated site goes through a message catalogue per locale in ICU MessageFormat, plurals, selections, numbers and dates expressed in the message itself, stored as JSON in the format translation platforms exchange. Message identifiers are typed from the source catalogue, so that a missing key or variable fails the build, and a test checks that every locale carries every key. Messages are resolved at build: the published HTML contains final strings and no localisation library runs in the browser; dates and numbers use the platform formatters. A project overrides any message through the `labels` of its `theme.yaml`.

## Affects

- [Home](../../screens/pages/home.md)
- [Entity page](../../screens/pages/entity-page.md)
- [Build](../../processes/ingestion/build-pipeline.md)
