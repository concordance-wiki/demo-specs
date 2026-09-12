---
execution: service
triggers: [pre-commit hook, merge request pipeline]
---
# Lint

`concordance lint` runs the same checks as the [build](build.md) on a single knowledge repository, before any site exists. In local scope it needs no network and writes nothing unless asked to fix. In global scope it downloads the latest published [model](../objects/model.md) to verify cross-source links.

## Steps

1. Read the configuration of the source being linted, or the default profile when none is given.
2. Parse and type the files of the current repository as the build would.
3. Run the checks of the registry that apply to an isolated repository, and the cross-source checks when a published model is available.
4. Print the [findings](../objects/finding.md) as text, JSON, SARIF or JUnit, each with the address of its documentation page.
5. Exit with 0 when no finding reaches the blocking severity, 1 otherwise, 2 on an execution error.
