# Concordance specifications

The typed notes of Concordance itself: its screens (one per page of the generated site), its processes, its rules (one per check), its objects, its APIs (the canonical model, the plugin API, the model query API of the future service with its operations), its roles, its batch, the tables of its model and its structuring decisions. This repository is a demonstration corpus for the tool and part of the project's own wiki, published by [demo-wiki](https://github.com/concordance-wiki/demo-wiki) together with the [glossary](https://github.com/concordance-wiki/demo-glossary).

| Folder | Type | Sections that produce relations |
|---|---|---|
| `screens/` | screen | `## Objects`, `## Actions`, `## Rules` |
| `processes/` | process | `## Steps` |
| `rules/` | rule | `## Applies to` |
| `objects/` | business_object | — |
| `api/` | api | `## Consumers`, `## Objects` |
| `api/operations/` | endpoint | `## Consumers`, `## Rules` |
| `decisions/` | decision | `## Affects` |
| `roles/` | role | — |
| `batches/` | batch | `## Reads`, `## Writes` |
| `data/` | data_object | — |

Every note passes `concordance lint` without a finding. When a story changes a screen, a pipeline step or a check, the matching note changes in the same delivery; the repository of the tool verifies on every change that every check has a rule note, every page slot a screen note and every active type at least one note (`scripts/parity.mjs`). This repository lints itself on every push with the linter built from that repository (`.github/workflows/lint.yml`), then tells the wiki to rebuild.
