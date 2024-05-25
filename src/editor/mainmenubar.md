# Main Menu Bar
The main menu bar gives users access to crucial functionality of the mod. Here you can find menu items for accessing windows, manipulating selections, performing operations and viewing helpful information.

## File
    
| Function | Description                  |
|----------|------------------------------|
| Import Schematic    | Imports schematic files to your clipboard |
| Export Schematic     | Exports a selection as a schematic file |
| Open Reference Image   | Adds a window with an image of your choice |
| Load Bedrock Packs   | Allows you to import Bedrock Edition textures or models. |
| Save Selection as CSV  | Exports a selection to a CSV[^note1] format. |
| Save Clipboard as JSON Model   | This allows you to take blocks and convert them to an item model. Models can be used in resource packs or imported into Blockbench. |

## Edit
    
| Function       | Default Shortcut | Description                                              |
|----------------|------------------|----------------------------------------------------------|
| Undo           | Ctrl+Z           | Reverses the most recent action                          |
| Redo           | Ctrl+Y           | Reverses the most recent undo                            |
| Cut            | Ctrl+X           | Removes the selection and stores it in the clipboard     |
| Copy           | Ctrl+C           | Copies the selected item to the clipboard                |
| Save Blueprint | Ctrl+P           | Saves the current selection as a blueprint for later use |

## Select
    
The Select submenu lets users perform a variety of functions related to selections.
    
| Function | Description                  |
|----------|------------------------------|
| Clear    | Clears the current selection |
| Expand   | Expands the current selection by a specified number of blocks |
| Shrink   | Shrinks the current selection by a specified number of blocks |
| Distort  | Distorts the current selection with simplex noise by a specified radius and distance. Radius is the scale of the noise and the distance is the amount it gets distorted by. |
| Smooth   | Applies a Gaussian blur on the selection to smooth out the selection. StdDev is the intensity of the smoothing operation and the threshold is the ‘cut-off’ of how much input weight is needed to affect the output. |
| Bounding Box | Creates a cuboid selection around the furthest points of the selection, encapsulating the entire selection. |

## View

The View submenu lets you configure options related to viewing and rendering certain elements in your world.

| Function       | Default Shortcut | Description |
|----------------|------------------|-------------|
| New View       | None             | Create a new [View](views.html) |
| Show Selection | None             | Lets you toggle the rendering of your selections |
| Show Biomes    | Ctrl+B           | Enables the biome overlay[^note2] |
| Show Key Presses| None            | This shows your inputs including mouse clicks on the bottom right of the viewport. This can be useful for making tutorials. |
| UI Scale       | None             | A slider ranging from 0.5 to 2. This lets you change the size of all graphical elements in the editor mode. |
| Min Brightness | None             | A slider ranging from 0 to 1. This lets you change how dark unlit places look in your world. A value of 1 means all blocks are fully lit, this is also known as Fullbright. |
| Fluid Opacity  | None             | A slider ranging from 0 to 1. This lets you change the opacity of transluscent[^note3] fluids to make it easier to look through. A value of 0 will make the fluid invisible. |

## Operations
    
The **Operations** submenu contains various useful features for building. All operations require and affect selections.
    
| Function             | Default Shortcut | Description  |
|----------------------|------------------|--------------|
| Fill                 | Ctrl+F           | Fill a selection with the chosen block |
| Fill Nearest         | None             | Fills an area with the closest neighbour blocks, useful to repair areas or fill in gaps. |
| Replace              | Ctrl+R           | Replace specific blocks in the selection with the chosen block |
| Set Biome            | None             | Sets the selection to the chosen biome |
| Autoshade            | None             | Shades your selection using a sun angle, either at the player position or at a set value. Different blocks can be set for the appropriate shading. |
| Drain                | None             | Drains an area of all fluids, including waterlogged blocks. |
| Waterlog             | None             | Floods an area with water, including turning water-loggable blocks into their waterlogged counterpart. |
| Smoothsnow           | None             | Creates a smooth area of snow based on the existing terrain. |
| Simulate Gravity     | None             | Gravity simulation makes all blocks with air below 'fall' as if they were affected by gravity. |
| Trigger Updates      | None             | Updates blocks by simulating a random tick on every block that doesn't have a valid surface or neighbouring block.  |
| Hollow               | None             | Hollows solid objects by filling them with air. |
| Fill Gaps            | None             | Fill Gaps does the opposite of the hollow operation, empty space within an object is filled with your active block. |
| Generate Colour Field| None             | Generates a CIELAB[^note4] colour field using all non-transparrent blocks. |
| Analyze              | None             | Analyzes the blocks in the selection, giving information on counts and distribution |
| Animated Rebuild     | None             | The Animated Rebuild operation allows creators to present their build in a timelapse-style rebuild of the selected structure. |

## Tool Masks
    
Clear and open the tool mask editing window. See [Tool Masks](toolmasks.md)

## Window
    
The **Windows** submenu lets the user toggle the visibility of important windows. If you ever close a window and want it back, this submenu allows you to reenable it.
    
## Keybinds

The **Keybinds** button opens a window to edit and set keybinds for tools and operations.

## Help
    
The **Help** submenu contains useful information and configuration options.

The dropdown contains links to information and resources. The style editor can be accessed through this window, allowing you to change and import custom colours for the UI. 

## References
[^note1]: comma-separated values (CSV) is a plaintext format that uses commas to separate values in a table-like manner.

[^note2]: Be aware that biomes in Minecraft are defined in a 4x4x4 grid. However, to make biomes feel more natural, vanilla warps the biomes visually. The biome overlay shows the "real" position of biomes, while biome blending and the f3 screen show the "warped" position of biomes.
    
[^note3]: Lava and other non-translucent fluids (if the game is modded) are not affected by opacity due to performance and mod compatibility concerns.

[^note4]: [CIELAB](https://en.wikipedia.org/wiki/CIELAB_color_space) is a type of colour space that can utilise the XYZ coordinates to display colours. 