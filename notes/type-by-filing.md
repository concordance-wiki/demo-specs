---
date: 2026-09-13
nature: technical
status: accepted
domain: typing
---
# Type by filing

The type of a note comes from where it is filed, not from what is written in it. The integrator declares the routes once in the configuration: the type of a whole source, a default for what no rule names, rules on a folder, a file suffix, an extension or the presence of a frontmatter key, evaluated in order with the last match winning. An author writes a file in the right folder and it is typed; frontmatter is the exception, for the note whose place and type disagree, and it wins. Every entity records the route that typed it, so that a page can say whether its type came from the source, a rule, a suffix or the note itself, and a type the profile does not declare is reported rather than guessed.

## Affects

- [Entity](../objects/inference/entity.md)
- [Type conflict](../rules/identifiers/type-conflict.rule.md)
- [Unknown type](../rules/identifiers/unknown-type.rule.md)
- [Build](../processes/ingestion/build-pipeline.md)
- [Lint](../processes/quality/lint.md)
