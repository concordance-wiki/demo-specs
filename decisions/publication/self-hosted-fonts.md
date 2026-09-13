---
date: 2026-09-13
nature: technical
status: accepted
supersedes: decisions/publication/fonts-from-a-third-party-host
---
# Self-hosted fonts

A font family named in `theme.yaml` is not a download: the project ships its font files itself under the assets of its theme and binds them with `@font-face` rules in its stylesheet, and the default theme emits no request to any other host. The two families of the default theme, Instrument Sans for the text and IBM Plex Mono for paths and identifiers, ship with the site under `assets/fonts/` with their licence, so that a project without a theme of its own reads in them from the disk. A test checks that no page and no stylesheet references a font host. The site therefore works from the disk, behind a proxy that reaches nothing, and without telling a third party who reads which page; the price is a folder of font files, in the site for the default families and in the configuration repository for a project's own, the [white label](white-label-by-default.md) fixture of the tool showing the layout.

## Affects

- [Home](../../screens/pages/home.md)
- [Entity page](../../screens/pages/entity-page.md)
- [Build](../../processes/ingestion/build-pipeline.md)
