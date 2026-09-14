---
aliases: [not found, missing page, empty states, page not found]
roles: [roles/publication/reader]
url_pattern: /404.html
status: valid
---
# Edge cases

What shows when something is missing. A static site has no support desk: the page is the only recourse. It names the cause in plain words, says what stays reachable despite the lack, and offers at least two ways out; no partial lack hides the rest of the page, and the navigation is always kept. A notice is allowed on these states alone, nowhere else in the site.

The rule common to every one of them: name the cause in everyday words, never a code alone, the code coming second when there is one; say what remains reachable; offer two exits at least, one of them assuming nothing; keep the navigation, never a bare page.

## Today

**Page not found.** The build writes `404.html` at the root of the site, the page GitHub Pages and GitLab Pages serve for any missing address under it, with the bar and the footer of every page. The eyebrow reads "Page not found", the title "This address matches no page of the last publication.", the sentence under it names the likely causes and what remains: "The file may have been renamed or moved, or its word fell under the publication threshold. The content stays in the repository and its text stays searchable." An identifier derives from the path, so renaming a file breaks the links already shared; a word that fell under the threshold lost its page, its occurrences staying in the index. Two exits close the page, "Search “publication treshold”", the search on the last segment of the address, and "Browse the spaces". Between the sentence and the exits, "Nearby addresses" lists the three pages at most whose address stands closest, each with its title and its address: the name of the page, its last segment, compared by edit distance with the last segment of the address asked for, so that a renamed file stands a character away and a moved file none, the nearest folder first among namesakes, none proposed beyond half the length of the name. The table of the pages is written at publication, in the entity table of the [search](search.md) index; the comparison runs in the browser, which alone knows the address asked for. The host serves this page at any address, so its links cannot be relative: its head names its own address as a base, from the path of `site.url` in the configuration, the root of the host without it. Without JavaScript the nearby addresses stay hidden and the search exit reads "Search the documentation": the cause, what remains and the two exits stand in the served HTML.

**Zero results.** The [search](search.md) tells two causes apart. The filters left every match out: the notice reads "No result for “staleness” with the filter Screen." (the filters listed when several), the sentence "The word exists in the documentation, but on none of the pages the filter keeps.", and one exit per filter, "Remove the filter “Screen”", with the count of results that lifting it alone gives back. No file uses the word: the notice reads "No result for “thresold”", the sentence "No file uses this word.", the closest form of the dictionary stands beside, and a line explains that "The search matches the start of words: a typo gives zero results and no suggestion.", the page saying it in one line rather than staying silent. Either way "See the page of the word", drawn dashed, leads to the page whose title or alias is the query, with its occurrences or its citations, when the corpus has one.

**Preview unavailable.** The most frequent lack, and the least serious. A [document page](document-page.md) whose conversion failed, the finding [conversion failed](../../rules/documents/conversion-failed.rule.md) recorded for its path, shows in place of its rendering the notice "The preview of this document could not be generated." with, when its text was read all the same, "The text was extracted all the same: it is indexed, cited on the other pages, and readable below.", else "Its text could not be extracted either: the original stays downloadable, and the note that describes it stands among its files."; two exits, "Download the original" and "Why this failure?", which unfolds the cause as the build worded it, "conversion of decks/scan.pptx failed: timed out after 120 s", and the check identifier after it; then the extracted text position by position under "Extracted text — 24 pages · indexed and searchable". The panel adds "State of the representations": `.pptx` available, `.pdf preview` failed, the word written and not only coloured, `text` extracted or missing, with the note that the same finding stands in the publication report and in the linter output: the failure is reported to whoever can fix it. A document without a preview and without a finding shows nothing of it.

**Contract unreachable.** The page of an interface whose declared contract the build could not read, the finding [unreachable contract](../../rules/contracts/unreachable-contract.rule.md) recorded for it, keeps the generic layout of the [API page](api-page.md) and says so under its title with the same notice: "The contract of this interface could not be read.", "The note stands on its own meanwhile: its text and the operations it describes are indexed and cited like any page.", the exit "Open the contract address" when the declared location is one, and "Why this failure?" unfolding the finding. The notice is one component, the only banner of the site, which the failed conversion shares.

**Ageing publication.** If a publication fails, nothing is deployed: the former site stays online, unchanged and silent, and can only tell its own age. Its publication date is written in it, and the expected cadence is declared in the configuration as `site.publish_every_days`; past three times that cadence, every page shows between the bar and its content the notice "Notice · This version was published 12 days ago. Publications are declared daily in the configuration. A recent change of the repositories may therefore be missing here. See the sources and their versions or consult the repositories directly.", the first exit leading to the [spaces](spaces.md), the second to the repository of a source. It appears by itself, without a server or a request, the days counted in the browser; a button closes it, and it comes back only after a later publication grows old in its turn. Without JavaScript it stays hidden: no page knows the day it is read. What the site cannot know: that a publication failed, since it wrote nothing; the pipeline alerts the team, not the site the reader, which is why the linter runs before the build.

Two cases remain to frame: a page whose file is empty, and a repository that became unreachable, whose pages vanish while the links pointing at them do not know it.

## Objects

- Reads: [finding](../../objects/quality/finding.md), [build](../../objects/ingestion/build.md), [entity](../../objects/inference/entity.md)

## Actions

1. Search the last segment of a missing address → [search](search.md)
2. Browse the spaces → [spaces](spaces.md)
3. Download the original of a document whose conversion failed → [document page](document-page.md)

## Rules

- [Conversion failed](../../rules/documents/conversion-failed.rule.md)
- [Unreachable contract](../../rules/contracts/unreachable-contract.rule.md)
- [Stale source](../../rules/sources/stale-source.rule.md)
