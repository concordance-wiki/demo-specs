# Concordance specifications

The typed notes of Concordance itself: its screens (one per page of the generated site), its processes, its rules (one per check), its objects, its APIs (the canonical model, the plugin API, the model query API of the future service with its operations), its roles, its batch, the tables of its model and its structuring decisions. This repository is a demonstration corpus for the tool and part of the project's own wiki, published by [demo-wiki](https://github.com/concordance-wiki/demo-wiki) together with the [glossary](https://github.com/concordance-wiki/demo-glossary).

## Layout

The first folder level is the family of a note and gives its type; the routes are declared in the wiki's `concordance.yaml`, and each family uses a different one on purpose.

| Folder | Type | Route | Sections that produce relations |
|---|---|---|---|
| `screens/pages/`, `screens/panels/` | screen | folder glob `screens/**` | `## Objects`, `## Actions`, `## Rules` |
| `viewers/` | screen | file name pattern `viewers/*-viewer.md` | `## Objects`, `## Actions`, `## Rules` |
| `processes/` | process | folder glob | `## Steps` |
| `rules/` | rule | suffix `.rule.md`, stripped from the identifier | `## Applies to` |
| `objects/` | business_object | folder glob | — |
| `api/` | api | folder glob | `## Consumers`, `## Objects` |
| `api/operations/` | endpoint | folder glob, declared after `api/**` | `## Consumers`, `## Rules` |
| `roles/` | role | folder glob | — |
| `batches/` | batch | folder glob | `## Reads`, `## Writes` |
| `data/` | data_object | `type:` in the frontmatter of each table | — |
| `decisions/`, `notes/` | decision | the source's `default_type`: no rule names them | `## Affects` |

The second level is the domain of the note, `ingestion`, `inference`, `publication` or `quality`, which the wiki declares as folder domains, with `inference/recognition` a subdomain: `objects/inference/recognition/keyword-page.md` is filed under it. Two families deviate: `rules/` is grouped by check family (`links/`, `documents/`, `identifiers/`, `vocabulary/`, `contracts/`, `sources/`, `engine/`) and claimed whole by the `quality` domain; `screens/` is grouped by kind of page and claimed by `publication`. A note whose domain is not its folder's says so in its frontmatter, `domain: inference` on the relation typing rule among others.

Every note passes `concordance lint` without a finding. When a story changes a screen, a pipeline step or a check, the matching note changes in the same delivery; the repository of the tool verifies on every change that every check has a rule note, every page slot a screen note and every active type at least one note (`scripts/parity.mjs`). This repository lints itself on every push with the linter built from that repository (`.github/workflows/lint.yml`), then tells the wiki to rebuild. This README is not a note: the wiki's configuration excludes it.
