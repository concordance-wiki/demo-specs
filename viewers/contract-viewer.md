---
roles: [roles/publication/reader, roles/ingestion/integrator]
url_pattern: /{source}/{path}#contract-title
status: valid
---
# Contract viewer

The section of the [entity page](../screens/pages/entity-page.md) of an API whose contract the build imported. It shows the contract next to the note without copying anything into the markdown: what the [model](../objects/inference/model.md) knows of the contract stands in the served HTML, and the signatures load on demand.

## Today

The section sits after the article of the note and before the side panel, under the heading "Contract" followed by the title the contract declares. A line under it gives the version when the contract states one, the import instant, and the link "Download the contract": the URL declared in the note when the contract is remote, or the copy of the file the build placed next to the page under the name the note points at, so that the original stays downloadable from the site as from its repository.

The operations come next as a plain list with their count, one entry per operation the import attached to the API, linking to its page and followed by its summary; the title is the operation note's when a note describes the operation, the contract's (`GET /entities`, `notifyBuild (ForgeBridgePort)`) otherwise. An operation present in the contract without a note is flagged "no note yet", and the heading counts them ("Operations 3, 1 without a note"): the documentation debt of the API, readable on its page, the other direction of the gap that the [operation unmatched](../rules/contracts/operation-unmatched.rule.md) rule reports for notes the contract does not declare. This list is text in the served page: without JavaScript nothing is lost, and the search index reads it with the rest of the page.

The viewer itself is an island. Served, it holds one link, "Contract data (JSON)", to the view of the contract the build wrote next to the fragments of the page; once hydrated it shows the button "Show the contract" and fetches that view on that click only, never before. Loaded, it lists every operation behind a disclosure button, its signature (method and path for an HTTP contract, operation, port and binding for a SOAP one) and its summary, opening on the parameters with their location, requirement and type, the type of the request body or input message, and one line per response with its status, description and body type; under the operations, a schema explorer offers one button per schema or type the operations reference and shows the selected one with its description and its fields, name, type, requirement and description. "Hide the contract" returns to the button. When the view cannot be fetched, from a page opened on the disk for instance, the link to the JSON comes back with a sentence saying so.

The same component renders an OpenAPI and a WSDL contract: the plugins that import them produce one common view, and the viewer never knows the format. It contains no form and no "Try it out": no request ever leaves the page towards the API described, and the only fetch of the whole site is the one of the view, on demand. The decision [purpose-built contract viewer](../decisions/publication/purpose-built-contract-viewer.md) says why no third-party viewer is embedded.

## Objects

- Reads: [model](../objects/inference/model.md), [entity](../objects/inference/entity.md), [link](../objects/inference/link.md)

## Actions

1. Open an operation → [entity page](../screens/pages/entity-page.md)
2. Download the contract → the declared URL or the copy next to the page
3. Show the contract → the operations and schemas, fetched once

## Rules

- [Operation matching](../rules/engine/operation-matching.rule.md)
- [Operation unmatched](../rules/contracts/operation-unmatched.rule.md)
- [Accessibility](../rules/engine/accessibility.rule.md)
