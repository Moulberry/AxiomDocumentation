# Gizmos

Gizmos are a common UI element which allows positioning within the 3D world.

![Gizmo With All Elements](/src/img/gizmo.png)

## Gizmo Properties

A gizmo can contain the following elements:
- **Axis Arrows** These coloured arrows correspond to XYZ coordinates. The red, green and blue arrows allow the gizmo to be dragged along the X, Y and Z axis respectively.
- **Center Node** The center node can be dragged to move the gizmo on all 3 axis. While dragging, the gizmo will maintain the same distance to the camera.
- **Plane Nodes** The 
- **Rotation Rings** The three Rotation rings allow you to perform rotations on objects. The red, green and blue rings allow the gizmo to be rotated on the X, Y and Z axis respectively. 
- **Scale Nodes** The Scale nodes are used for [Display Entities](/builder/displayentities.md). Dragging one of the three Scale Nodes will stretch along the X, Y and Z axis respectively.
- **Global Gizmos** When a gizmo is set to global, the **Axis Arrows**, **Centre Node** and **Rotation Rings** are locked to the world's rotation.
- **Local Gizmos** A local gizmo is when the **Axis Arrows**, **Centre Node** and **Rotation Rings** are locked to the gizmo's rotation.

## Gizmo Controls

### Builder Mode Gizmo Controls

When using [Display Entities](/builder/displayentities.md) or [Marker Entities](/builder/marker.md), a gizmo is used to move and modify the entity. There are multiple keys you can use to alter how the gizmo is used to modify the entity. To select a gizmo, use left-click on the **Center Node**.

| Key                | Description                                                                                                                                                                                                                            |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Right-Click        | Used to adjust any of the gizmo elements such as the Axis Arrows.                                                                                                                                                                      |
| Left-Click         | Relocates the entity to the block the player is facing.                                                                                                                                                                                |
| Scroll             | Nudges the entity along the axis you're facing. Holding the Center Node while scrolling will push and pull the entity relative to the player.                                                                                          |
| Control            | While adjusting gizmo elements, the movement snapping size is increased to one block and the rotation snapping is set to 15 degrees. When using control while adjusting the scale nodes, all three axis will be scaled simultaneously. |
| Shift              | Removes all snapping when adjusting gizmo elements.                                                                                                                                                                                    |
| Control + C        | Copies the entity data to the clipboard.                                                                                                                                                                                               |
| Delete / Backspace | Permanently removes the selected entity.                                                                                                                                                                                               |
| Control + V        | Pastes the entity in the clipboard.                                                                                                                                                                                                    |

### Editor Mode Gizmo Controls

The Editor utilises gizmos for many features such as [Selections](selections.md) and the [Path Tool](/tools/other/path.md). However, each tool or feature may have a different gizmo type depending on its usage. This means one tool could have less gizmo features than another.

> Tip: You can use the arrow keys to nudge gizmos on the X and Z axis.