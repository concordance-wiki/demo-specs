---
roles: [roles/publication/reader, roles/ingestion/integrator]
url_pattern: /{source}/{path}
status: valid
---
# API page

The page of an interface whose contract the build imported. Same shell as the [entity page](entity-page.md), laid out at the grain an interface is worked at: its operations. The tree lists them under the interface, a table matches them to the contract and states the gaps between the contract and the notes, the contract stands in a block of its own, shown and never copied into the text, and the panel keeps five keys and lifts the operations to the top of the related pages. An API without an imported contract keeps the generic entity page.

## Today

The page of an `api` note at `<id>/index.html` stands on the three regions of the [entity page](entity-page.md). On the left, the tree of the space with the current interface ruled and bold and its operations listed under it, in the order of the contract as its reader lists it, the paths sorted for an OpenAPI document, whatever folder their notes are filed in. In the centre, the breadcrumb, the title and the line naming the type, when the note last changed and the space, without any highlighted property: the properties wait in the panel. The note follows at full column width, with its legend.

Under the note, "Operations", led by "Matched to the contract by operation name." One row per operation the import attached to a note, in the order of the contract, the same as the tree: the method as a chip, `DELETE` and `OPTIONS` abbreviated with their full name kept for assistive technology, the path in the monospace family, the title of the operation note linked to its page, and how many pages cite the operation, "N callers", the same count as the related pages of that operation. Then the gaps, in italics on the soft surface, and the lead says what the italics mean, a sentence present only when the table holds a gap: an operation the contract declares that no note describes, unlinked, marked "present in the contract, without a page"; and an operation note the contract does not declare, the notes the [operation unmatched](../../rules/contracts/operation-unmatched.rule.md) rule reports, linked, with a hollow chip and "unknown path" when the note declares neither, marked "described, absent from the contract". The rows are text in the served page; a contract without any operation says so.

"Interface contract" follows as a card: on its first line the format the import recorded (`openapi 3.1`, `wsdl 1.1`), the file the note names and, at its end, "imported N days ago", the last change of the contract file relative to the build, from the history of its repository, never the instant of the build; under it the [contract viewer](../../viewers/contract-viewer.md), open in the page as soon as its script runs, a link to its JSON view until then, and the note that no schema is copied into the text: the page shows the contract, it does not duplicate it; at the foot of the card the link that downloads the original. The path of the file and its edit link close the column.

The right panel keeps three blocks. "Properties" lists five keys, no more, the properties the profile highlights for the type first, in that order, then the declared ones, with the note that the operations come from the contract, not from the header. "Related pages" is the [mentions panel](../panels/mentions-panel.md) with the operations first whatever their passage count, since the notes describing them name the interface at the top of their file, then the other pages by number of passages, and the note "On an interface the operations rise to the top: that is the grain we work at." Last, the neighbourhood map folded behind its line. There is no table of contents.

## Objects

- Reads: [entity](../../objects/inference/entity.md), [link](../../objects/inference/link.md), [model](../../objects/inference/model.md), [finding](../../objects/quality/finding.md)

## Actions

1. Open an operation → [entity page](entity-page.md)
2. Open a related page → [entity page](entity-page.md)
3. Download the contract → the declared URL or the copy next to the page
4. Read the contract → [contract viewer](../../viewers/contract-viewer.md), open in the page

## Rules

- [Operation unmatched](../../rules/contracts/operation-unmatched.rule.md)
- [Ambiguous operation](../../rules/contracts/ambiguous-operation.rule.md)
