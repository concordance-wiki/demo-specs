---
date: 2026-09-13
nature: product
status: accepted
---
# White label by default

The generated site carries the organisation's identity and nothing of the tool's. The name, logo, favicon, font families, corner radius, light and dark palettes, footer and additional stylesheet all come from `theme.yaml`, validated by the theme schema; a faulty key is reported by its path like a configuration error. The footer credits the tool only when the project asks for it (`footer.credit: true`, a plain link to the repository); by default nothing a reader sees names it. Font files are shipped by the project itself and bound with `@font-face` rules: the site emits no request to any other host. Light and dark modes follow the system preference, the reader can force one with the mode switch and the choice is remembered; without JavaScript the theme's default applies. The accent colour never carries information on its own: wherever the default theme uses it, an underline, an outline, a weight or a text carries the same meaning.

The project's own wiki asks for the credit, because it is the tool documenting itself.

## Affects

- [Home](../../screens/pages/home.md)
- [Entity page](../../screens/pages/entity-page.md)
- [Keyword page](../../screens/pages/keyword-page.md)
- [Alphabetical index](../../screens/pages/alphabetical-index.md)
- [Search](../../screens/pages/search.md)
- [To-do page](../../screens/pages/todo-page.md)
- [Build](../../processes/ingestion/build-pipeline.md)
