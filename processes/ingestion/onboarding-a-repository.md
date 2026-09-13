---
execution: mixed
triggers: [a new knowledge repository, a first evaluation of the tool]
---
# Onboarding a repository

The path from a folder of markdown files to a published wiki, and the one every new knowledge repository follows to join an existing wiki. The integrator does the declaration and the two settings a forge asks for; the [build pipeline](build-pipeline.md) and the [lint](../quality/lint.md) do the rest. On the golden corpus the whole path takes under thirty minutes, and the repository of the tool replays every command of it on each change so that the guide never promises a step that fails.

## Steps

1. Install the command line: the published package with npm, the container image with a container engine, or a checkout of the repository built once; all three run the same `concordance` command.
2. Create the configuration repository: `concordance init --templates` writes a commented `concordance.yaml` and the note templates, `validate-config` confirms the file is valid before anything is cloned. The configuration repository holds the configuration, the theme and the stopwords, never the content.
3. Declare the sources: one entry per knowledge repository, a `git` URL cloned at depth 1 or a local `path`, a glossary source marked `glossary: true` so that its titles win when a word could mean two things, and typing rules where the filing of a repository already says what a note is. Credentials stay in the git environment of the machine or of the pipeline; the configuration never carries a token.
4. Build: `concordance build` validates, ingests, parses, types, recognises, infers, checks and renders in one run, prints every [finding](../../objects/quality/finding.md) and a summary, and writes the site with the [model](../../objects/inference/model.md) and the log; a content anomaly is a finding, never a crash, and the exit code follows `build.fail_on` alone.
5. Open `dist/index.html` from the file manager: the site works over `file://` as behind a server, and the [home page](../../screens/pages/home.md), the [alphabetical index](../../screens/pages/alphabetical-index.md) and the [to-do page](../../screens/pages/todo-page.md) show what the corpus already gives before any note is rewritten.
6. Publish: commit the configuration repository, add the pipeline of the forge that builds on every push and every morning and publishes `dist/` on GitHub Pages or GitLab Pages; on GitHub, set the Pages source to the workflow once. Two builds of unchanged sources are byte-identical, so a published site can be diffed against the previous one.
7. Let each knowledge repository check itself: `concordance lint` in its merge requests, with the SARIF log on GitHub or the JUnit report on GitLab so that every finding lands in the margin of the diff, and `--source` with `--config` when the rules of the configuration must apply.
8. Read the to-do page and the findings, then improve the corpus at its own pace: a note for a word everybody uses, a link where a mention was only recognised, a frontmatter key where a relation must be certain. Nothing is required before the first build, and nothing added stops working when it is removed.
