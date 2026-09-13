---
execution: service
triggers: [pre-commit hook, merge request pipeline]
---
# Lint

`concordance lint` runs the same checks as the [build pipeline](build-pipeline.md) on a single knowledge repository, before any site exists. In local scope it needs no network and writes nothing unless asked to fix. In global scope it reads the latest published [model](../objects/model.md) to check what one repository cannot see alone: links into other sources, frontmatter relations across sources and homonyms with the glossary; it never rebuilds the model.

## Steps

1. Read the configuration of the source being linted, or the default profile when none is given, and the `concordance-lint.yaml` of the repository.
2. Parse and type the files of the current repository as the build would.
3. Run the checks of the registry that apply to an isolated repository.
4. In global scope, read the published model named by `global.model`: from its local cache while it is younger than `global.max_age_hours`, else fetched again with the validators the server gave, else from the path given; when no model can be read, print one line saying why and go on with the local findings alone.
5. In global scope, check the notes against the remote entities: a link with a `source:` prefix or climbing into a sibling source must reach a known note (`E-LINK-BROKEN`), or is flagged when the model was built with cross-source links off (`W-LINK-CROSS-SOURCE`); every frontmatter reference that declares a relation must join a pair of types the profile allows (`E-META-REL`); a title or alias shared with a remote entity of another type is a homonym (`I-TERM-HOMONYM`). Each finding names the remote entity and the build timestamp of the model.
6. Print the [findings](../objects/finding.md), local and global merged without repetition, as text, JSON, SARIF or JUnit, each with the address of its documentation page; the JSON and SARIF reports name the scope and say when the global scope was degraded.
7. Exit with 0 when no finding reaches the blocking severity, 1 otherwise, 2 on an execution error; an unreachable model is never an execution error.
