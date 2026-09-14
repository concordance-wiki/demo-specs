---
roles: [roles/publication/reader, roles/ingestion/integrator]
url_pattern: /{source}/{path}#contract-title
status: valid
---
# Contract viewer

The block of the [API page](../screens/pages/api-page.md) of an API whose contract the build imported. It shows the contract next to the note without copying anything into the markdown: what the [model](../objects/inference/model.md) knows of the contract stands in the served HTML, and the signatures load as soon as the page runs its script.

## Today

The block sits after the operations table of the page and before the path of the file, under the heading "Interface contract". Its first line gives the format the import recorded (`openapi 3.1`, `wsdl 1.1`), the file the note names and, at its end, when the contract last changed relative to the build, "imported 9 days ago": the date of the last commit of the file in its repository, the file date outside one, and the instant of the import only for a contract fetched from a URL. Its last line is the link "Download the contract": the URL declared in the note when the contract is remote, or the copy of the file the build placed next to the page under the name the note points at, so that the original stays downloadable from the site as from its repository.

The operations are not listed in the block: the table above it matches them to the notes, one row per operation with its method, its path, its note and its callers, the operations the contract declares without a note and the notes the contract does not declare in italics, the other direction of the gap that the [operation unmatched](../rules/contracts/operation-unmatched.rule.md) rule reports. Those rows are text in the served page: without JavaScript nothing is lost, and the search index reads them with the rest of the page.

The viewer itself is an island, open in the page. Served, it holds one link, "Contract data (JSON)", to the view of the contract the build wrote next to the fragments of the page; as soon as its script runs it fetches that view, once, "Loading the contract…" standing in the meantime, and opens in the block without any button, as the document viewer opens on the document page. Loaded, it lists every operation in the order of the contract behind a disclosure button, its signature (method and path for an HTTP contract, operation, port and binding for a SOAP one) and its summary, opening on the parameters with their location, requirement and type, the type of the request body or input message, and one line per response with its status, description and body type; under the operations, a schema explorer offers one button per schema or type the operations reference and shows the selected one with its description and its fields, name, type, requirement and description. The note under the viewer says that no schema is copied into the text: the page shows the contract, it does not duplicate it. When the view cannot be fetched, from a page opened on the disk for instance, the link to the JSON comes back with a sentence saying so.

The same component renders an OpenAPI and a WSDL contract: the plugins that import them produce one common view, and the viewer never knows the format. It contains no form and no "Try it out": no request ever leaves the page towards the API described, and the only fetch of the whole site is the one of the view, once per page. The decision [purpose-built contract viewer](../decisions/publication/purpose-built-contract-viewer.md) says why no third-party viewer is embedded.

## Objects

- Reads: [model](../objects/inference/model.md), [entity](../objects/inference/entity.md), [link](../objects/inference/link.md)

## Actions

1. Open an operation → [entity page](../screens/pages/entity-page.md), from the table of the [API page](../screens/pages/api-page.md)
2. Download the contract → the declared URL or the copy next to the page
3. Open an operation of the viewer → its parameters, request and responses, fetched once with the view

## Rules

- [Operation matching](../rules/engine/operation-matching.rule.md)
- [Operation unmatched](../rules/contracts/operation-unmatched.rule.md)
- [Accessibility](../rules/engine/accessibility.rule.md)
