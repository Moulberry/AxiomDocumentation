# Placement

Placements can be repositioned and rotated using the [Gizmo](gizmos.md).

Once the placement is in the correct position, you can use Enter or Ctrl+V to confirm it. To cancel a placement, use the Delete or Backspace key.

> Tip: The placement can be rotated clockwise along the X and Z axis by using `Ctrl+R`. Placements can be flipped in the direction of your mouse vector by using `Ctrl+F`.

 ## Placement Options

| Option           | Description                                                                  |
| ---------------- | ---------------------------------------------------------------------------- |
| Keep Existing    | Stops the placement from overriding pre-existing blocks                      |
| Paste Air        | Enables air to override pre-existing blocks                                  |
| Merge Blocks     | Merges new blocks with existing blocks based on the block shape.             |
| Unlock Rotation  | Allows the placement to be rotated at any angle rather than 90 degree steps. |
| Rotate/Scale     | Opens the [Rotate/Scale](placement.md#Rotate_and_Scale) window.              |
| Snap to ground   | Repositions the placement down to the nearest solid surface.                 |
| Paste Copy       | Places a copy of the placement without cancelling the placement.             |
| Paste and Select | Places the object and selects it, allowing for further modification.         |

## Rotate and Scale

The Rotate/Scale window allows for rotating and resizing by any amount. This window contains a drop-down with for multiple functions. Below are all options with a description.

| Option            | Description                                                                                                                                                                               |
| ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Nearest Neighbour | Nearest Neighbour has 6 translation inputs, one for each rotation axis and one for each scale axis. However the output may contain more artifacts than using the other translation types. |
| RotSprite         | RotSprite has 3 translation inputs, there is one input for each rotation axis.                                                                                                            |
| Scale2x           | Scale2x has no inputs. It scales your placement by two times its size.                                                                                                                     |
| Scale3x           | Scale3x has no inputs. It scales your placement by three times its size.                                                                                                                   |
