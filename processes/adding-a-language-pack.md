---
execution: human
triggers: [a source written in a language the engine does not ship]
---
# Adding a language pack

A language is described by data, never by code: a folder holding `pack.yaml` (the name of the language, its apostrophes, its collation options, its plural suffix rules, validated by the language pack schema) and `stopwords.txt`. The engine ships `en` and `fr`; a regional variant such as `fr-CA` uses the pack of its language until a more specific one is registered; any other language comes as a pack shipped by a plugin, registered when the plugin loads, and a locale with no pack is a build error. Every [source](../objects/source.md) selects its pack through its BCP 47 locale, which decides its comparison form, its default stopwords, its word segmentation and the collation of its indexes. The [architecture guide](https://github.com/concordance-wiki/concordance/blob/main/docs/guides/architecture.md#locale-per-source) states the design.

## Steps

1. Write the pack: a folder with `pack.yaml` naming the language, its apostrophe characters, its collation options and its plural suffix rules, and `stopwords.txt`, one word per line, `#` opening a comment; validate the file against `language-pack.schema.json`.
2. Ship it in a plugin that registers the pack under its locale tag when it loads, and declare the plugin under `plugins:` of the configuration; a project that also wants type prefixes in that language adds them to its profile under `type_prefixes`, per locale, without touching the pack.
3. Declare the locale on the source, `locale: <tag>`, or on the project when it is the default; a tag with no pack registered fails the build with the tag named.
4. Build, and read the summary and the [findings](../objects/finding.md): the dictionary of that locale is built from the titles and aliases of its entities and the pack's stopwords, its occurrences are scanned with the pack's normalisation, and its index collates with its rules.
5. Give the interface its labels: the site takes every label from a message catalogue per locale; a locale without one falls back to English until the catalogue exists.
