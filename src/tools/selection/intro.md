# Selection Tools

This section covers selection tools and their options. An option that is generic to all selection tools a concept known as **boolean operations**. The default option is ‘add’

| Boolean Operation | Description |
| --- | --- |
| Add | Adds the selected area to the current selection |
| Subtract | Subtracts the selected area from the current selection |
| Replace | Replaces the current selection with the selected area |
| Intersect | Selects only the area that overlaps with the current selection |

> Note: At very large scales non-cuboid selections become less performant due to the complexity in keeping track of the entire region. If you need to perform an operation on a very large area it is recommended to use a cuboid selection and encompass the entire build.
