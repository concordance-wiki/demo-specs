---
date: 2026-09-12
nature: technical
status: accepted
---
# Locale per source

Each source declares its locale, English or French, defaulting to the project locale. The locale selects normalisation, plural rules, stopwords, type prefixes and collation. Other languages come as plugins.

## Affects

- [Entity](../objects/entity.md)
- [Build](../processes/build.md)
- [Lint](../processes/lint.md)
