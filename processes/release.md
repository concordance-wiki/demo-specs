---
execution: human
triggers: [a set of changesets ready to ship]
---
# Release

How a version of the tool is cut and what it publishes: the npm packages under one shared version number and the `concordance` preset, the container image tagged with the version and `latest`, a git tag `v<major>.<minor>.<patch>` on the main branch and a release whose notes are the changelog entry. Versions follow semantic versioning; before `1.0.0` a minor version may break compatibility and says so, a patch never does. The [release guide](https://github.com/concordance-wiki/concordance/blob/main/docs/guides/releasing.md) is the contract the maintainer follows until the publication pipelines are enabled.

## Steps

1. Start from a clean main branch that passed the full pipeline, on a machine with the Node.js version the repository pins.
2. Run the full check, licence inventory included; it must pass.
3. Apply the changesets: the versions are bumped, every changelog is updated from the sentences the pull requests wrote, the consumed changeset files are deleted; a changelog entry a user would not understand is rewritten in the changeset, never in the changelog.
4. Open a pull request titled `chore(release): v<x.y.z>` with that diff and merge it once the pipeline is green.
5. Tag the merge commit `v<x.y.z>` and push the tag.
6. Publish: install from the lock file, build, and publish every package whose version is not on the registry yet, from the tagged commit, so that the tag and the packages point at the same commit.
7. Let the image workflow build the container image from the tag, compare a [build](build-pipeline.md) inside the container with one outside, measure the image and push it under the version and `latest`; copy its size into the release notes.
8. Create the release from the tag, with the changelog entries of the version as its notes.
