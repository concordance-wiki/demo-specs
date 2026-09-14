---
aliases: [about, about this wiki, about page]
roles: [roles/publication/reader]
url_pattern: /about
status: valid
---
# About this wiki

The page of trust: everything that lets a reader judge whether the site read is current. When it was built, from which repositories, at which version each was read, what the site leaves out and how a page is corrected. The footer of every page links to it, "See the sources and their versions".

## Today

The page at `about/index.html` opens on the breadcrumb "Home › About this wiki", the title and the sentence "This site is rebuilt at every change of the repositories. It is not edited here: every correction is made in the original file, and appears at the next publication." Three figures follow in one card: "Published on" with the build instant, "Pages" with the notes counted, "Indexed words" with every entry of the [alphabetical index](alphabetical-index.md) counted. No quality indicator stands among them, and no duration: the [model](../../objects/inference/model.md) records none, so that two builds of the same sources agree.

"Sources — each with the version exactly used" is one table, the repositories in the order of the [home](home.md), the most cited first: REPOSITORY (the name of the [source](../../objects/ingestion/source.md)), NATURE (`sources[].title` when the configuration gives one, else the labels of the dominant types of the space), VERSION (the commit the build read, shortened to seven characters, empty for a local source without a git history), CONTENT KEPT ("312 pages" or "205 documents", as the home page counts them) and LAST CHANGE (the newest change from the git history, worded relative to the build). A source past the freshness threshold shows its date in the accent colour, doubled by its value in days and by a hidden phrase for assistive technology, and is named under the table: "The versions are those read at publication: two publications on the same versions produce an identical site. The source framing exceeds the freshness threshold of 180 days, which is reported here and in the build report, never on the pages themselves." The threshold named is the one that flags the source, `staleness.warn_after_days`.

The page closes on two paragraphs over a rule: "What the site does not contain. The files the configuration excludes, the documents whose conversion failed, and the words used fewer than 3 times. The publication report lists them.", the threshold being `inference.keyword_pages.min_occurrences` and the report the [to-do page](todo-page.md); and "Correct a page. Every page carries at its foot the path of its file and a link to the forge. There is no other way to edit, and that is deliberate.", followed by the link "How to contribute" when `project.contribute_url` is set. A third paragraph, "What is pseudonymised.", says that the names of the participants are replaced by stable pseudonyms and that the mapping is never published, when `privacy.pseudonymize.enabled` is true.

The page is generated from the model and the configuration. The key `project.about` names a markdown file, relative to the configuration, whose sections are rendered after the generated content on the template of a note; a file named and missing stops the build as a missing profile would.

## Objects

- Reads: [model](../../objects/inference/model.md), [source](../../objects/ingestion/source.md)

## Actions

1. Open the spaces → [spaces](spaces.md)
2. Open the publication report → [to-do page](todo-page.md)

## Rules

- [Stale source](../../rules/sources/stale-source.rule.md)
