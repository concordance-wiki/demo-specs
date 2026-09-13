---
date: 2026-09-13
nature: technical
status: accepted
---
# MinHash for twin resources

The text similarity that helps recognise the forms of one document works on extracted text, never on binary content, and never compares every pair. Each text goes to its comparison form, then to shingles of five words, then to a MinHash signature of 128 functions under a fixed seed; LSH banding, four rows per band, enumerates the candidate pairs, two signatures that share no band being never compared, so that the full matrix is never built. In `auto` mode the pairs estimated at 0.5 or more have their exact Jaccard index recomputed on the full shingle sets, and the finding gives the share of lines in common; a pair whose word counts differ by more than half is an inclusion rather than a duplicate and its content signal is capped. Resources are sorted by identifier before anything else, so two runs give the same result.

## Affects

- [Resource](../objects/resource.md)
- [Representation](../objects/representation.md)
- [Duplicate candidate](../rules/duplicate-candidate.md)
- [Build](../processes/build-pipeline.md)
