---
aliases: [W-PLUGIN-DISABLED]
severity: warning
---
# Disabled plugin

A declared plugin needs a system tool that is not installed on the machine that builds: the build ran the detection command of every system dependency of the manifest, one answered nothing, and the plugin was not registered, so that none of its readers, converters, sources, inference methods, checks, projections or components took part in the build. An optional dependency yields the same finding as `info` and the plugin stays registered. The fix is the tool on the `PATH` of the build, or the plugin removed from `plugins:`; a project whose conversions must run raises the severity to `error`.

Check `W-PLUGIN-DISABLED`, severity warning by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/W-PLUGIN-DISABLED.md). The severity can be overridden per project or per repository.

## Applies to

- [Plugin API](../api/plugin-api.md)
- [Build](../processes/build-pipeline.md)
- [Lint](../processes/lint.md)
