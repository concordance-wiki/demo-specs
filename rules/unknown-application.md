---
aliases: [W-APP-UNKNOWN]
severity: warning
---
# Unknown application

The application cascade (the `application` of the source, the `set.application` of a typing rule, the frontmatter `application`) produced an identifier that `applications:` does not declare. The value is kept as written on the entity and the finding says where it came from; nothing composes the entity into a declared application. Distinct from the [missing application](missing-application.md), where the cascade produced nothing at all.

Check `W-APP-UNKNOWN`, severity warning by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/W-APP-UNKNOWN.md). The severity can be overridden per project or per repository.

## Applies to

- [Entity](../objects/entity.md)
- [Build](../processes/build-pipeline.md)
