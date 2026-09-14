---
aliases: [parity, local check parity]
severity: error
condition: a finding of a local check differs between the linter and the build on the same repository
---
# Linter and build parity

The local lint says the same thing as the build. For the checks the linter computes in `--scope repo`, listed as `LOCAL_CHECKS` by the lint package (`E-ENCODING`, `E-FM-INVALID`, `E-ID-DUP`, `E-ID-INVALID`, `E-LINK-BROKEN`), `concordance lint` on a repository and `concordance build` on a configuration that declares it as a source produce the same [findings](../../objects/quality/finding.md): same check, source, path, line and entity, same severity, message and remediation. The build reports more, never less: the checks that need the whole [model](../../objects/inference/model.md) only exist there.

The rule holds because both sides call the same functions to list the files of a repository (the globs `privacy.exclude` and the repository's own `exclude` name and the files git ignores are left out on both sides), read a note, derive its identifier and resolve its links, and take severities and remediations from the same catalogue. A parity test in the repository copies each fixture corpus, the golden ones and the faulty ones, lints every source of the copy and builds the same copy, then compares the findings of the local checks one by one, and checks that the excluded folder and the git-ignored file of the faulty corpora, which hold faults, are reported by neither side; any divergence fails continuous integration. The JSON report of the linter carries `scope` and `checks` so that a forge report states which checks the guarantee covers. The [getting started guide](https://github.com/concordance-wiki/concordance/blob/main/docs/guides/getting-started.md#parity-with-the-build) and the [architecture guide](https://github.com/concordance-wiki/concordance/blob/main/docs/guides/architecture.md#linter-and-build-parity) describe it.

## Applies to

- [Finding](../../objects/quality/finding.md)
- [Build](../../processes/ingestion/build-pipeline.md)
- [Lint](../../processes/quality/lint.md)
