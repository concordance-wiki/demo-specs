---
execution: human
triggers: [a set of changesets ready to ship]
---
# Release

How a version of the tool is cut and what it publishes: the npm packages under one shared version number and the preset, the container image tagged with the version and `latest`, a git tag `v<major>.<minor>.<patch>` on the main branch, a release whose notes are the changelog entries with the tarball of every package and the standalone binaries as assets, and the mirrors of the GitHub action and the GitLab component at the same version. Every form of one version names the same commit: the tag, the packages on npm, the image, the action, the component and the pre-commit hook. Versions follow semantic versioning; before `1.0.0` a minor version may break compatibility and says so, a patch never does. The [release guide](https://github.com/concordance-wiki/concordance/blob/main/docs/guides/releasing.md) is the contract; the one decision that stays human is the merge of the version pull request, and the publications to the registries stay disabled until the maintainer enables them.

## Steps

1. Every pull request that changes a published package carries a changeset: the packages it touches, the bump and one sentence for the changelog; the pipeline refuses a pull request without one.
2. On every push to the main branch that carries a changeset, the pipeline opens or refreshes the version pull request: the versions are bumped, every changelog is updated from the sentences the pull requests wrote, the consumed changeset files are deleted, the lock file and the version pins of the action, the component and the hook are rewritten; a changelog entry a user would not understand is rewritten in its changeset on the main branch, never in the pull request.
3. The maintainer reads the version pull request and merges it: this is the decision to release.
4. The release workflow tags the merge commit `v<x.y.z>`, builds the standalone binaries on three platforms, packs every published package, verifies the licence inventory, writes the checksums and creates the release from the tag with the changelog entries of the version as its notes and the binaries, the tarballs, the checksums and the inventory as its assets; the manifest of every package has been checked on every change to ship neither its sources, nor its tests, nor its fixtures.
5. The image workflow builds the container image from the tag, compares a [build](../ingestion/build-pipeline.md) inside the container with one outside and measures the image; once its publication is enabled it pushes the image under the version and `latest`, and the maintainer copies its size into the release notes.
6. Once the npm publication is enabled, the publish job takes the tarballs attached to the release, verifies them against the checksums and publishes them in dependency order with provenance, under the tag `latest` for a plain version and `next` or `rc` for a prerelease; it then lints the faulty corpus through the published command line from an empty folder and through the binary of the release, and the two reports must match.
7. The release notes are completed with the npm page of every package and the digest of the image when it is on the registry; the action repository and the component project receive the version, each when its token exists, the action with its major tag moved to the version.
