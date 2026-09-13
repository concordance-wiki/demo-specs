---
execution: service
triggers: [a push to the main branch of a content repository, a push to the configuration repository, the nightly schedule, a manual dispatch]
---
# Publishing the wiki

The loop that keeps this wiki alive: a change in the glossary or in the specifications is linted where it is written, then the configuration repository rebuilds the site of the three repositories and publishes it. Nothing is copied from one repository to another and nothing is written into a content repository. Until the first release of the tool, every workflow builds the command line from a checkout of the tool's repository, the interim form of the [pipelines the guide gives](https://github.com/concordance-wiki/concordance/blob/main/docs/guides/pipelines.md) with the published package.

## Steps

1. An author pushes a note to the main branch of the glossary or of the specifications, after the [lint](lint.md) of the merge request.
2. The lint workflow of that repository runs the [linter](lint.md) again on the main branch and stops there on an error finding.
3. When the lint is green and the repository holds the dispatch token, the workflow sends a `content-updated` dispatch to the configuration repository; without the token it stops, and the nightly schedule or a manual dispatch takes over.
4. The wiki workflow of the configuration repository starts, on that dispatch, on a push to its own main branch, on its schedule or by hand: it checks out the configuration, builds the command line, validates the configuration and runs the [build](build-pipeline.md), which clones the two content repositories at their `main` ref at depth 1.
5. The build writes the site, the [model](../objects/model.md) and the build log; an error finding fails the workflow as `build.fail_on` says and nothing is published.
6. The site is uploaded as the Pages artifact and deployed; the published site names the commit of every source in the `build` block of its model.
7. The repository of the tool verifies on every change that the wiki still covers it: every check has a rule note, every page slot a screen note, every active type a note, every configuration key and check family a glossary term.
