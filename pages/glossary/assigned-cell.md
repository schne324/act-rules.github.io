---
title: Assigned cell
key: assigned-cell
unambiguous: true
objective: true
input_aspects:
  - Accessibility tree
  - DOM tree
---

This definition of assigning table header cells to data cells is different to the [internal algorithm for scanning and assigning header cells][https://html.spec.whatwg.org/multipage/tables.html#internal-algorithm-for-scanning-and-assigning-header-cells] in the HTML. This definition focuses solely on the structure of the [table][] and [grid][] elements as they appear in the accessibility tree.

In order for an [accessible object][] with the [semantic role][] of [rowheader][] to be assigned to an element with the [semantic role][] of either [cell][], [gridcell][], or inheriting from [cell][], at least one of the following is true:

- there is at least one non-empty element with a [semantic role][] of either [cell][], or inheriting from [cell][], that has the `headers` attribute with the value that matches the `id` [attribute value][] of the [rowheader][] that is being evaluated, and it is an [owned element][] of the same [table][] or [grid][] as the [rowheader][]; or
- there is at least one non-empty element with a [semantic role][] of either [cell][], or inheriting from [cell][], that is a child an [accessible object][] with the [semantic role][] of [row][] that is also the parent of evaluated [rowheader][];

An [accessible object][] with the [semantic role][] of [columnheader][] is assigned to an element with a [semantic role][] of either [cell][], or inheriting from [cell][], at least one of the following is true:

- there is at least one non-empty element with a [semantic role][] of either [cell][], or inheriting from [cell][], that has the `headers` attribute with the value of the test target's `id` [attribute value][] and is an [owned element][] of the same [table][] or [grid][] element as the test target but it is not a child of the same [accessible object][] with the [semantic role][] of [row][]; or
- there is at least one non-empty element with a [semantic role][] of either [cell][], or inheriting from [cell][], that is a child of an [accessible object][] with the [semantic role][] of [row][], that is not the parent element of the [columnheader][] for which the assignment is evaluated; the [cell][]'s [row][] is an [owned element][] of the same [table][] or [grid][] to which the [columnheader][] belongs and has the same [child index][] as the [columnheader][] or it has a `colspan` attribute which together with the [cell][]'s [child index][] value spans over the [child index][] value of the [columnheader][];

[accessible object]: https://www.w3.org/TR/core-aam-1.1/#dfn-accessible-object
[html element]: https://html.spec.whatwg.org/#htmlelement
[included in the accessibility tree]: #included-in-the-accessibility-tree
[cell]: https://www.w3.org/TR/wai-aria-1.1/#cell 'ARIA cell role'
[gridcell]: https://www.w3.org/TR/wai-aria-1.2/#gridcell 'ARIA gridcell role'
[table]: https://www.w3.org/TR/wai-aria-1.1/#table 'ARIA table role'
[grid]: https://www.w3.org/TR/wai-aria-1.1/#grid 'ARIA grid role'
[columnheader]: https://www.w3.org/TR/wai-aria-1.1/#columnheader 'ARIA columnheader role'
[rowheader]: https://www.w3.org/TR/wai-aria-1.1/#rowheader 'ARIA rowheader role'