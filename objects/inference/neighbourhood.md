---
lifecycle: [accumulated, ranked, displayed]
---
# Neighbourhood

The entities around an [entity](entity.md), in two forms the [model](model.md) keeps apart. The bounded neighbourhood counts, per entity, the paragraphs it shares with every other, keeps the fifty best by count then by identifier, and feeds the co-occurrence [links](link.md) and the accompanying words of a keyword page. The displayed neighbourhood is the list of the one-hop neighbours a page shows: both ends of every link, each with the largest confidence and the relation of its most confident link, ranked by the order the profile declares for the type of the page, then by confidence, then by identifier, and cut at the configured size. Both are computed at build and written, never in the browser.
