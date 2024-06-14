# Main Menu Bar
The main menu bar gives users access to crucial functionality of the mod. Here you can find menu items for accessing windows, manipulating selections, performing operations and viewing helpful information.

## Edit
    
| Function       | Default Shortcut | Description                                              |
|----------------|------------------|----------------------------------------------------------|
| Undo           | Ctrl+Z           | Reverses the most recent action                          |
| Redo           | Ctrl+Y           | Reverses the most recent undo                            |
| Cut            | Ctrl+X           | Removes the selection and stores it in the clipboard     |
| Copy           | Ctrl+C           | Copies the selected item to the clipboard                |
| Save Blueprint | Ctrl+P           | Saves the current selection as a blueprint for later use |

## Select
    
The Select submenu lets users perform a variety of functions related to [Selections](/tools/selection/intro.md).
    
| Function     | Description                                                                                                                                                                                                          |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Clear        | Clears the current selection                                                                                                                                                                                         |
| Expand       | Expands the current selection by a specified number of blocks                                                                                                                                                        |
| Shrink       | Shrinks the current selection by a specified number of blocks                                                                                                                                                        |
| Distort      | Distorts the current selection with simplex noise by a specified radius and distance. Radius is the scale of the noise and the distance is the amount it gets distorted by.                                          |
| Smooth       | Applies a Gaussian blur on the selection to smooth out the selection. StdDev is the intensity of the smoothing operation and the threshold is the 'cut-off' of how much input weight is needed to affect the output. |
| Bounding Box | Creates a cuboid selection around the furthest points of the selection, encapsulating the entire selection.                                                                                                          |

## Tool Masks

Clear and open the tool mask editing window. See [Tool Masks](toolmasks.md)

## Window

The **Windows** submenu lets the user toggle the visibility of [Windows](windows/intro.md). If you ever close a window and want it back, this submenu allows you to reenable it.

## Keybinds

The **Keybinds** button opens a window to edit and set keybinds for tools and operations.

## Help
    
The **Help** submenu contains useful information and configuration options.

The dropdown contains links to information and resources. The [style editor](windows/themes.md) can be accessed through this window, allowing you to change and import custom colours for the UI. 
