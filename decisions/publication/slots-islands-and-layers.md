---
date: 2026-09-13
nature: technical
status: accepted
---
# Slots, islands and layers

The site is a set of named slots rendered at build by components, each with a typed view model that is the contract between the generator and a theme; the published HTML carries the full content of every page. Only interactive components are hydrated: an island is served as its static markup inside an element carrying its props, and one small bundle per island, named after a hash of its content, mounts the same component on it, loaded only by the pages that use it, so that a page loads no framework code unless one of its islands needs it. Styling is native CSS in four cascade layers, tokens, base, components and project, the project's stylesheet winning every cascade by construction. Without JavaScript the content stays reachable: mentions in native disclosure elements, the search field a plain form, the mode switch hidden. A budget of 150 kB per page is measured on every build.

## Affects

- [Entity page](../../screens/pages/entity-page.md)
- [Mentions panel](../../screens/panels/mentions-panel.md)
- [Search](../../screens/pages/search.md)
- [Gallery index](../../screens/pages/gallery-index.md)
- [Static first](static-first.md)
