---
date: 2026-09-12
nature: technical
status: superseded
---
# Fonts from a third-party host

The first draft of the theme named its font families by loading them from a public font host, as most static sites do: one stylesheet link, no file to ship. Superseded by [self-hosted fonts](self-hosted-fonts.md): a page that fetches a font from another host does not work from the disk, leaks the address of every reader to that host, and contradicts the rule that the site emits no request the project did not choose.

## Affects

- [Build](../processes/build-pipeline.md)
