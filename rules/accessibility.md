---
aliases: [a11y, accessibility guarantees]
severity: error
condition: a page of the generated site breaks one of the five accessibility guarantees
---
# Accessibility

Every screen of the generated site gives a screen reader or keyboard user the same information as everyone else. Five guarantees hold on every page, and the build and the test suite verify them without a browser.

1. **Contrast.** Body, muted and link text reach 4.5:1 over the page background and over a surface; headings and the focus ring reach 3:1. The ratio is computed from the palette of `theme.yaml` in both colour schemes, and a project palette under the minimum is reported as a warning.
2. **Keyboard.** Every interactive element shows the same visible focus ring; no rule removes an outline without a replacement; the skip link comes first and appears on focus; the tab order is the document order, without any forced `tabindex`.
3. **Textual equivalent.** Every graphical view ships the same information as structured text in the served HTML, where the search index reads it: the neighbourhood map is followed by the list of neighbours with their type, relation and weight, and the list is authoritative.
4. **ARIA roles and states.** Collapsibles carry `aria-expanded` and `aria-controls`, a `details` starts with a named `summary`, fields carry a label, search forms are named landmarks, and a tab strip uses the tablist pattern. A static checker enforces these on every page, next to the structural rules (one `h1`, headings in order, landmarks, alternatives, unique ids, skip link).
5. **Automated audit.** axe-core runs over every page of the component gallery in continuous integration and fails on any violation of impact serious or critical.

The [theming guide](https://github.com/concordance-wiki/concordance/blob/main/docs/guides/theming.md#accessibility) states what a theme author must keep when overriding a slot.

## Applies to

- [Home](../screens/home.md)
- [Entity page](../screens/entity-page.md)
- [Keyword page](../screens/keyword-page.md)
- [Alphabetical index](../screens/alphabetical-index.md)
- [Search](../screens/search.md)
- [To-do page](../screens/todo-page.md)
- [Build](../processes/build-pipeline.md)
