# Selections

A **Selection** is a set of highlighted blocks that affect the functionality of other systems.

There are many selection tools in Axiom that you can use to make selections. Each of these tools feature several options to further fine-tune what and how you might want to select something. See [Selection Tools](/tools/selection/intro.md) for more info.

- With a selection, you can constrain the brush strokes of [Tools](/tools/intro.md).

- [Operations](/editor/mainmenubar/operations.md) rely on selections to affect blocks within a region.

## Selection Options

|Option|Default Keybind|Description|
|--|---|---|
|Clear Selection|`enter`|Clears the active selection, shortcut for '[Select](/editor/mainmenubar/select.md) > Clear' |
|Move Selection||Moves the selection but not the blocks within|
|Fill|`Ctrl+F`|Fills the active selection with a specified block. [^note1] |
|Replace|`Ctrl+R`|Replaces specified blocks in your active selection with a block [^note1]|
|Copy|`Ctrl+C`|Copies the selection to the [Clipboard](/editor/windows/clipboard.md)|
|Copy With...||Copies the selection to the [Clipboard](/editor/windows/clipboard.md) including entities, air, or both|
|Cut|`Ctrl+X`|Cuts the selection, allowing you to move it anywhere you'd like using the [Gizmo](gizmos.md)|
|Duplicate|`Ctrl+J`|Duplicates the selection, similar to cut, but doesn't remove the blocks in the process|
|Operations...||[Operations](/editor/mainmenubar/operations.md)|


[^note1]: To be able to specify block properties for the block you are working with, use [Operations](/editor/mainmenubar/operations.md)

>Tip: Using 'Move Selection' reveals [Scale Nodes](/editor/gizmos.md#gizmo-properties) at the tip of axis arrows for the gizmo, allowing for scaling selections.