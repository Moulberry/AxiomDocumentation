# Clipboard and Placements

## Clipboard

A selection can be copied to the clipboard using Ctrl+C. 

With blocks in your clipboard, you can paste back into the world by hovering over the desired location using your cursor position and pressing Ctrl+V. Pasting like this will initiate a [Placement](/editor/gizmos.md#Placement).

The clipboard can be cleared by right-clicking the icon and choosing the 'clear' option. 

## Rotation and Scaling

While the placement is initiated and the [Gizmo](/editor/gizmos.md) is visible, some options will appear on your [View](views.md) window[^note1]. 

## Placement Options

| Option          | Description                                                                  |
| --------------- | ---------------------------------------------------------------------------- |
| Keep Existing   | Stops the placement from overriding pre-existing blocks                      |
| Paste Air       | Enables air to override pre-existing blocks                                  |
| Merge Blocks    | Merges new blocks with existing blocks based on the block shape.             |
| Unlock Rotation | Allows the placement to be rotated at any angle rather than 90 degree steps. |
| Rotate/Scale    | Opens the [Rotate/Scale](clipboard.md#Rotate_and_Scale) window.              |
| Snap to ground  | Repositions the placement down to the nearest solid surface.                 |

## Rotate and Scale

The Rotate/Scale window allows for rotating and resizing by any amount. This window contains a drop-down with for multiple functions. Below are all options with a description.

| Option            | Description                                                                                                                                                                               |
| ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Nearest Neighbour | Nearest Neighbour has 6 translation inputs, one for each rotation axis and one for each scale axis. However the output may contain more artifacts than using the other translation types. |
| RotSprite         | RotSprite has 3 translation inputs, there is one input for each rotation axis.                                                                                                            |
| Scale2x           | Scale2x has no inputs. It scales your placement by two times its size.                                                                                                                     |
| Scale3x           | Scale3x has no inputs. It scales your placement by three times its size.                                                                                                                   |

> Tip: Left-clicking the 'Empty' clipboard icon opens up the [Blueprint Browser](blueprints.md).

## Notes

[^note1]: For versions 3.0.0 and below, the options will appear inside the clipboard window.