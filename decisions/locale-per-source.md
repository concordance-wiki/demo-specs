---
aliases: [BCP 47 locales, locale as a BCP 47 tag]
date: 2026-09-12
nature: technical
status: accepted
---
# Locale per source

Each source declares its locale as a BCP 47 tag, defaulting to the project locale. A language is described by data, never by code: a pack holding its name, its apostrophes, its collation options, its plural suffix rules and its stopwords, which the locale selects together with the type prefixes of the profile for that language; word segmentation and collation come from the platform's Unicode implementation. The engine ships `en` and `fr`; a regional variant such as `fr-CA` uses the pack of its language until a plugin registers a more specific one, other languages are packs shipped by plugins, and a tag with no pack is a build error. The [adding a language pack](../processes/adding-a-language-pack.md) process is the path.

## Affects

- [Entity](../objects/entity.md)
- [Source](../objects/source.md)
- [Build](../processes/build-pipeline.md)
- [Lint](../processes/lint.md)
- [Adding a language pack](../processes/adding-a-language-pack.md)
