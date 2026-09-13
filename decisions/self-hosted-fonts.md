---
date: 2026-09-13
nature: technical
status: accepted
supersedes: decisions/fonts-from-a-third-party-host
---
# Self-hosted fonts

A font family named in `theme.yaml` is not a download: the project ships its font files itself under the assets of its theme and binds them with `@font-face` rules in its stylesheet, and the default theme emits no request to any other host. A test checks that no page and no stylesheet references one. The site therefore works from the disk, behind a proxy that reaches nothing, and without telling a third party who reads which page; the price is a folder of font files in the configuration repository, the [white label](white-label-by-default.md) fixture of the tool showing the layout.

## Affects

- [Home](../screens/home.md)
- [Entity page](../screens/entity-page.md)
- [Build](../processes/build-pipeline.md)
