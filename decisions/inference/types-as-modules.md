---
date: 2026-09-13
nature: technical
status: accepted
---
# Types as modules

A type of the profile is a folder that carries everything the type needs: its declaration, its labels per interface language, its note template and, when the generic page is not enough, the components that render it. The core types are written that way and the default profile is assembled from them, so that the format the engine ships is the format a team extends it with: a project keeps its own modules in a folder its profile names, a plugin contributes modules through a contribution point of the [plugin API](../../api/plugin-api.md), and the build merges them before the keys of the project profile, plugins first, refusing a module of a core type, which is extended through the profile, and two modules of one type. The site never learns a type slug: the entity page exposes the declaration of the type and every attribute of the note, declared and not, and a dedicated component for a type, an attribute or a mapped section is resolved by name, the project theme first, then the module, then the generic page, which remains correct when nothing specific is said.

## Affects

- [Entity page](../../screens/pages/entity-page.md)
- [Gallery index](../../screens/pages/gallery-index.md)
- [Plugin API](../../api/plugin-api.md)
- [Build](../../processes/ingestion/build-pipeline.md)
- [Declarative profile](declarative-profile.md)
