# Display Entities

**Display Entities** were added to Minecraft in 1.19.4[^note1], introducing the ability to display blocks, items and text in the form of entities. This means you can essentially create structures at any scale. However, they are hard to use, especially for players inexperienced with commands.

Axiom takes advantage of this difficulty and has a feature for precise display entity editing.

In the [Context Menu](contextmenu.md), the "Create Display Entity" button will open a menu similar to the creative inventory. Use the tabs to switch between item, block and text displays.

The tables below cover the settings for the **Create Display** Entity menu.

## Item Display

| Setting             | Description                                                                                                                                                  |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Item                | This represents the item that will be displayed. Clicking the icon will display all items in a grid. The CustomModelData filter only displays custom blocks. |
| Item Display        | This setting is similar to Blockbench's display options[^note2]. This determines how the item will be displayed.                                             |
| Additional Settings | Refer to [Additional Settings](displayentities.md#additional-settings).                                                                                      |

## Block Display

| Setting             | Description                                                                                                  |
| ------------------- | ------------------------------------------------------------------------------------------------------------ |
| Block               | This represents the block that will be displayed. Clicking the stone icon will display all blocks in a grid. |
| Additional Settings | Refer to [Additional Settings](displayentities.md#additional-settings).                                      |

## Text Display

| Setting             | Description                                                                                                                                                   |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Text                | The black box provides space to enter text for the text display.                                                                                              |
| Background Color    | The background colour determines the colour surrounding the text. The colour fomat for the background colour is ARGB in Hexadecimal.                          |
| Line Width          | The line width determines the amount of space required to start a new line.                                                                                   |
| Alignment           | The alignment determines the offset relative to the gizmo.                                                                                                    |
| Shadow              | Adds a shadow effect to the text.                                                                                                                             |
| Additional Settings | Refer to [Additional Settings](displayentities.md#additional-settings)                                                                                        |

## Additional Settings

The **Additional Settings** submenu provides further options for the display entity. However, these are much more advanced and are generally used for mapmaking.

> After pressing "done", the display entity will be spawned at the player position with the selected settings.

## Display Entity Manipulation

Left-clicking the white node at the centre of the Display Entity will display a [Gizmo](/editor/gizmos.md). Using the gizmo, you can move, rotate and scale the Display Entity in any direction.

## Keybinds

There are many key combinations that can be used while the gizmo is active. Listed below are all key combinations alongside their description.

| Key                | Description                                                                                                                                                                                               |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Right Click        | Moves the Display Entity to the block you're facing. However, while looking at the white cube on the gizmo, it opens the [Editing Menu](displayentities.md#editing-menu) for the selected display entity. |
| Scroll             | Nudges the display by the default step size[^note3].                                                                                                                                                      |
| Control            | Used alongside Left Click to increase the step size. The movement step is changed to 1 block, the rotation step is set to 15 degrees and the scale is set to affect all axes rather than one.             |
| Shift              | Lowers the step size for movement and scale to 0.0001 blocks and sets the rotation step size to 1 degree.                                                                                                 |
| Control + C        | Copies the display entity to the clipboard. This can be pasted using `Control + V`.                                                                                                                       |
| Delete / Backspace | Deletes the selected Display Entity.                                                                                                                                                                      |
| Control + Z        | Undo the previous edit.                                                                                                                                                                                   |
| Control + Y        | Redo the undone edit.                                                                                                                                                                                     |
| Middle-Click       | Copies the Display Entity to an item. This works the same as spawn eggs and can be snapped to different rotation steps by using control or shift while placing.                                           |

## Editing Menu

The **Editing Menu** has many useful features. Listed below are all features with a description.

| Modifier               | Description                                                                                                                                                                                                                                                                                                    |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Edit Properties        | Opens the original menu to set the display entity properties.                                                                                                                                                                                                                                                  |
| Edit Transformation    | Opens a menu to manually enter precise translation, rotation and scale.                                                                                                                                                                                                                                        |
| Reset Translation      | Resets the offset set in the Edit Transformation menu.                                                                                                                                                                                                                                                         |
| Reset Rotation         | Resets the rotation to 0 on all angles.                                                                                                                                                                                                                                                                        |
| Reset Scale            | Resets all scale values to 1.                                                                                                                                                                                                                                                                                  |
| Gizmo Mode             | Switches between [local](/editor/gizmos.md) and [global gizmos](/editor/gizmos.md).                                                                                                                                                                                                                            |
| Duplicate              | Duplicates the Display Entity in the same position.                                                                                                                                                                                                                                                            |
| Grouping               | Pressing this button will reveal the grouping settings. Changing the range slider will affect the area of grouping. The "Group with nearby in range" will group all Display Entities within the provided range. The "Ungroup children" button ungroups all display entities that have previously been grouped. |
| Remove                 | Deletes the Display Entity.                                                                                                                                                                                                                                                                                    |
| Copy Summon Command    | Copies the display entity to the clipboard. This can be pasted using `Control + V`.                                                                                                                                                                                                                            |
| Copy Coordinates       | Copies the exact coordinates to the clipboard.                                                                                                                                                                                                                                                                 |
| Copy Transform Command | Copies the transformation to the clipboard as a command.                                                                                                                                                                                                                                                       |

## Notes

[^note1]: [Display Entities](https://minecraft.wiki/w/Display) are a vanilla Minecraft feature.

[^note2]: Blockbench uses [display settings](https://mcreator.net/wiki/blockbench-blockitem-display-settings) for different perspecives of a model. 

[^note3]: The default step size is 1/16th of a block (0.0625).