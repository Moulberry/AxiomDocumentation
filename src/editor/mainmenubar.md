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
    
The Select submenu lets users perform a variety of functions related to selections.
    
| Function | Description                  |
|----------|------------------------------|
| Clear    | Clears the current selection |
| Mask     | Selects blocks within the current selection that match the chosen block |
| Expand   | Expands the current selection by a specified number of blocks |
| Shrink   | Shrinks the current selection by a specified number of blocks |
| Distort  | Distorts the current selection with simplex noise by a specified radius and distance. Radius is the scale of the noise and the distance is the amount it gets distorted by |
| Smooth   | Applies a Gaussian blur on the selection to smooth out the selection. StdDev is the intensity of the smoothing operation and the threshold is the ‘cut-off’ of how much input weight is needed to affect the output |
| Bounding Box | Creates a cuboid selection around the furthest points of the selection, encapsulating the entire selection |

## View

The View submenu lets you configure options related to viewing and rendering certain elements in your world.

| Function       | Default Shortcut | Description |
|----------------|------------------|-------------|
| New View       | None             | Create a new [View](views.html) |
| Show Selection | None             | Lets you toggle the rendering of your selections |
| Show Biomes    | Ctrl+B           | Enables the biome overlay[^note1] |
| Min Brightness | None             | A slider ranging from 0 to 1. This lets you change how dark unlit places look in your world. A value of 1 means all blocks are fully lit, this is also known as fullbright 
| Fluid Opacity  | None             | A slider ranging from 0 to 1. This lets you change the opacity of transluscent[^note2] fluids to make it easier to look through. A value of 0 will make the fluid invisible |
| Show Key Presses| None            | This shows your inputs including mouse clicks on the bottom right of the viewport. This is useful for making tutorials. |

[^note1]: Be aware that biomes in Minecraft are defined in a 4x4x4 grid. However, in order to make biomes feel more natural, vanilla warps the biomes visually. The biome overlay shows the "real" position of biomes, while biome blending and the f3 screen show the "warped" position of biomes.
    
[^note2]: Lava and other non-translucent fluids (if the game is modded) are not affected by opacity due to performance and mod compatibility concerns.

## Create
    
The **Create** submenu lets you make geometric shapes with your active block. Since these shapes are computed mathematically, they can adjust to any angle and transformation, giving you a lot of control over their look. When you 'place' these objects, you can use the [gizmo](gizmos.md) to reposition them and rotate them at arbitrary angles.
    
Each shape lets you tweak their XZ or XYZ dimensions, as well as having a toggle for individual sliders. In addition to controling rotation using the gizmo, you can also input specific angles for yaw, pitch, and roll in the 'advanced options' dropdown. Plus, there are options for making the shapes hollow, placing only the outer layer.
    
The current available shapes are:    
 - Sphere
 - Cuboid
 - Cylinder
 - Cone
 - Pyramid

## Operations
    
The **Operations** submenu has a lot of features for modifying the selected part of your world 
    
| Function             | Default Shortcut | Description  |
|----------------------|------------------|--------------|
| Fill                 | Ctrl+F           | Fill a selection with the chosen block |
| Fill Nearest         | None             | Fills an area with the closest neighbor blocks, useful to repair areas or fill in gaps |
| Replace              | Ctrl+R           | Replace specific blocks in the selection with the chosen block |
| Set Biome            | None             | Sets the selection to the chosen biome |
| Drain                | None             | Drains an area of all fluids, including waterlogged blocks |
| Waterlog             | None             | Floods an area with water, including turning waterloggable blocks into their waterlogged counterpart |
| Simulation > Gravity | None             | Gravity simulation makes all blocks with air below 'fall' as if they were affected by gravity |
| Analyze              | None             | Analyzes the blocks in the selection, giving information on counts and distribution |

## Tool Masks
    
Clear and open the tool mask editing window. See [Tool Masks](toolmasks.md)

## Window
    
The **Windows** submenu lets the user toggle the visibility of important windows. If you ever close a window and want it back, this submenu allows you to reenable it.
    
## Help
    
The **Help** submenu contains useful information and configuration options.

Users can configure keybinds, find useful links to Axiom related resources and view this documentation.
