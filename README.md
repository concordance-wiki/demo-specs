# Concordance specifications

The typed notes of Concordance itself: its screens, its two processes, its rules (one per check), its objects, its plugin API, the model query API of the future service and its structuring decisions. This repository is a demonstration corpus for the tool and part of the project's own wiki, published by [demo-wiki](https://github.com/concordance-wiki/demo-wiki) together with the [glossary](https://github.com/concordance-wiki/demo-glossary).

| Folder | Type | Sections that produce relations |
|---|---|---|
| `screens/` | screen | `## Objects`, `## Actions`, `## Rules` |
| `processes/` | process | `## Steps` |
| `rules/` | rule | `## Applies to` |
| `objects/` | business_object | — |
| `api/` | api | `## Consumers`, `## Objects` |
| `decisions/` | decision | `## Affects` |

Every note passes `concordance lint` without a finding. When a story changes a screen, a pipeline step or a check, the matching note changes in the same delivery.
