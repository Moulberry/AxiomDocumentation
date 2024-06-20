# Main Menu Bar
The main menu bar gives users access to crucial functionality of the mod. Here you can find menu items for accessing windows, manipulating selections, performing operations and viewing helpful information.

## File

The 'File' drop-down provides many useful features regarding loading and saving files to use within Axiom. 

### Import Schematic

When pressed, a file explorer window will be opened. Here you can select a schematic to import into Axiom. Both `.schem` and `.schematic` are supported, however only one schematic can be loaded at a time.

After you've opened a schematic in your file explorer, it will be loaded into your [Clipboard](/editor/windows/clipboard.md).

### Export Schematic

The Export Schematic option allows you to export a schematic using your clipboard. Once you have something in your clipboard, you'll be able to export it as a schematic.

For users with a [Commercial License](https://axiom.moulberry.com/commercial), you'll be able to export to any version from 1.7 to 1.19.

### Open Reference Image

Opens a file explorer window for you to select an image to be loaded into Axiom. Once opened, you can drag and resize the image window to wherever you want. 

Right-Clicking on an image window will display some options to adjust the reference image.

- **Close Window** removes the image.
- **Set Filtering: Nearest** "smoothes" out sharp pixels to reduce the blocky look. 
- **Set Filtering: Linear** stops it from smoothing out pixels, leaving the sharp edges.
- **Show In Game UI** makes it so the image is always shown. When disabled, the image is hidden when outside of the [Editor](/editor/intro.md).
- **Borderless** removes the outer padding and resizing tab.

### Load Bedrock Packs

This is a [Commercial License](https://axiom.moulberry.com/commercial) feature.

The 'Load Bedrock Packs' option allows you to replace existing models with Bedrock Edition models. 

This would be most used by Bedrock Marketplace creators who would want to see their models on Java.

### Save Selection as CSV

Exports a [Selection](/editor/selections.md) to a Comma-Seperated Value (CSV) format.

### Save Clipboard as JSON Model

This allows you to convert your clipboard to an item model. Models can be used in resource packs or imported into Blockbench.

## Edit
    
| Function       | Default Shortcut | Description                                                                       |
| -------------- | ---------------- | --------------------------------------------------------------------------------- |
| Undo           | Ctrl+Z           | Reverses the most recent action                                                   |
| Redo           | Ctrl+Y           | Reverses the most recent undo                                                     |
| Cut            | Ctrl+X           | Removes the selection and stores it in the clipboard                              |
| Copy           | Ctrl+C           | Copies the selected item to the [Clipboard](/editor/windows/clipboard.md)         |
| Save Blueprint | Ctrl+P           | Saves the clipboard as a [Blueprint](/editor/windows/blueprints.md) for later use |

## Select
    
The Select submenu lets users perform a variety of functions to modify [Selections](/tools/selection/intro.md).
    
| Function     | Description                                                                                                                                                                                                          |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Clear        | Clears the current selection                                                                                                                                                                                         |
| Expand       | Expands the current selection by a specified number of blocks                                                                                                                                                        |
| Shrink       | Shrinks the current selection by a specified number of blocks                                                                                                                                                        |
| Distort      | Distorts the current selection with simplex noise by a specified radius and distance. Radius is the scale of the noise and the distance is the amount it gets distorted by.                                          |
| Smooth       | Applies a Gaussian blur on the selection to smooth out the selection. StdDev is the intensity of the smoothing operation and the threshold is the 'cut-off' of how much input weight is needed to affect the output. |
| Bounding Box | Creates a cuboid selection around the furthest points of the selection, encapsulating the entire selection.                                                                                                          |

## View

The View submenu lets you configure options related to viewing and rendering certain elements in the Editor Menu.

### New View

Creates a new [View](/editor/windows/views.md) located at the current position.

### Show Selection

Toggles the rendering of [Selections](/editor/selections.md).

### Show Biomes

Toggles the visualisation of biomes. Each biome is represented with its own colour.

Be aware that biomes in Minecraft are defined in a 4x4x4 grid. However, to make biomes feel more natural, vanilla warps the biomes visually. The biome overlay shows the "real" position of biomes, while biome blending and the f3 screen show the "warped" position of biomes.

The default shortcut for this view is `Ctrl+B`.

### Show Key Presses

This shows your keyboard and mouse inputs in the bottom-right corner of the screen. This can be useful for making tutorials or debugging problems.

### UI Scale

This slider ranges from 0.5 to 2. This lets you change the size of all graphical elements in the editor mode.

### Min Brightness

The 'Min Brightness' slider ranges from 0 to 1. This lets you change how dark unlit places look in your world. A value of 1 means all blocks are fully lit, this functions similar to night vision.

### Fluid Opacity

The 'Fluid Opacity' slider ranges from 0 to 1. This lets you change the opacity of water to alter its visibility. A value of 0 will result in water being invisible.

Lava and modded fluids are not affected due to performance concerns.

## Operations

The **Operations** submenu contains various useful 'operations' to modify blocks within [Selections](/editor/selections.md).

> IMPORTANT: Operations only affect [Selections](/editor/selections.md).

### Fill

The 'Fill' operation fills the selected area of blocks with a specified block. A small [Window](/editor/windows/intro.md) will open, allowing you to choose which block by clicking the block icon. This will open the 'Select Block' Window.

The default keybind for this operation is `Ctrl+F`.

### Fill Nearest

The 'Fill Nearest' operation doesn't use a specified block. Rather, it uses the nearest block that isn't air for each block within the selection.

### Replace

The 'Replace' operation is similar to 'Fill'. However, instead of filling every block in the selection, you can replace a specific block with another.

The default keybind for this operation is `Ctrl+R`. Note that this shortcut is overridden when a [Placement](/editor/placement.md) is active.

### Set Biome

The 'Set Biome' Operation sets the biome within the selection with a specified biome.

### Autoshade

The 'Autoshade' operation shades your selection using a sun angle, either at the player position or at a set value. Different blocks can be set for the appropriate shading.

The Autoshade Window has many options to control how blocks are lit.

| Option              | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Sun                 | When enabled, lighting is used to shade blocks. When disabled, blocks are shaded with Ambient Occlusion.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| From                | The 'From' drop-down controls how the selection is lit. The different lighting modes include: **Player Position**, **Custom Positions** and **Sun Angle**. When the **Player Position** is selected, the light source is centred to the player position. With **Custom Positions**, you can set multiple fixed light sources. Pressing 'Add Position' will add a new light source at your current position. Each source is marked with a yellow 'sun' and the intensity can be changed to alter how bright the light source is. The **Sun Angle** creates a 'sun' light source at a set angle. This is similar to a 'spot' light source, however, sun light sources affect everything at the same angle. |
| Ambient Occlusion   | Ambient Occlusion determines how exposed the block is to the light source. The less exposed a block is, the darker it'll be shaded.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Global Illumination | Global Illumination is the effect of light 'bouncing' off multiple objects. Increasing this slider will result in more 'bounces'.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Dither              | Adds a blending effect to reduce the sharp texture changes.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Palette Options     | The 'Palette Options' section is used to determine what blocks are used when shading. When the 'Type' drop-down is set to **Automatic**, blocks will be chosen depending on the surface. You will be provided with a set of toggles to filder out blocks you don't want. When the 'Type' drop-down is set to **Custom**, You'll be able to input your own blocks. The list is ordered from dark to light and you can influence the amount of a specific block by using the slider adjacent to the block icon.                                                                                                                                                                                            |

You can save and load [Presets](/editor/toolpresets.md) for the Autoshade operation in the 'Presets' section.

To confirm the Autoshade, press the 'Autoshade' button at the bottom of the window.

### Drain

Removes all water in your selection. This operation also removes the 'waterlogged' property from blocks.

### Waterlog

Replaces all air blocks with water and replaces all water-loggable blocks with their waterlogged variant.

### Smoothsnow

Adds a layer of snow between one and eight layers above existing terrain. No blocks are replaced as existing terrain is prioritised.

The operation attempts to generate snow as smooth as possible.

### Simulate Gravity

The 'Simulate Gravity' operation processes simulates the effect of gravity to all blocks, regardless of whether they normally float or not.

### Trigger Updates

The 'Trigger Updates' operation removes any blocks that are incorrectly positioned.

For example, a floating sign within the selection will be removed.

### Hollow

Fills the inside of the selected object with air, leaving the a shell of the original object.

The 'Hollow' operation also considers transparent/non-solid blocks so having an exterior that includes glass will be accounted for.

### Fill Gaps

The 'Fill Gaps' does the opposite of the 'Hollow' operation, empty space within an object is filled with your active block.

Again, transparent and non-solid blocks are considered.

### Generate Colour Field

The 'Generate Colour Field' operation Generates a colour field using the [CIELAB colour space](https://en.wikipedia.org/wiki/CIELAB_color_space) within a selection.

A colour field (colour space) is a way to organise colours. CIELAB was chosen as it utilises XYZ coordinates to represent LAB. LAB represents three components of the colour space:
#### **L - (Lightness)**
- Brightness is mapped to positive X
- Darkness is mapped to negative X
#### **A - (Red/Green)**
- Red is mapped to positive Y
- Green is mapped to negative Y
#### **B - (Yellow/Blue)**
- Yellow is mapped to positive Z
- Blue is mapped to negative Z

All blocks within the colour field used are full, non-transparent blocks to reduce overlapping.

If two blocks are similar enough, Axiom will attempt to place them in the same position. However, Axiom prevents this by offsetting blocks until there is no overlap. This means there's little chance for blocks to be excluded.

### Analyze

Displays each block type within a selection ordered by the count of each block. A total for both the count and distribution is shown in the last row.  

### Animated Rebuild

The 'Animated Rebuild' option allows for creating cinematics of a build being built block-by-block.

> IMPORTANT: Animated Rebuild should be used with caution, as it may permanently break your structure.

Below are all settings in the Animated Rebuild window. All settings for refer to the delay between block placement.

| Delay Setting         | Description                                                                                          |
| --------------------- | ---------------------------------------------------------------------------------------------------- |
| Start Delay           | The time until the first block is placed.[^note1]                                                    |
| Max Delay             | Determines the maximum delay for all delays.                                                         |
| Air Block Delay       | The time it takes to place an air block within your selection.                                       |
| Same Block Delay      | The time taken to place the same adjacent block (excluding air).                                     |
| Different Block Delay | The time it takes to place different adjacent blocks.                                                |
| Random Extra Delay    | A random delay added to each block delay. The extra delay is randomised for each block placed.       |
| Horizontal Multiplier | Muliplies the delay with the provided value for all blocks placed with an offset on the Y axis.      |
| Vertical Multiplier   | Muliplies the delay with the provided value for all blocks placed with an offset on the X or Z axis. |

By default, the starting point for the Animated Rebuild operation is located at the centre of the selection. To Change this, place a structure block at the position you'd like the rebuild to start. You can place multiple structure blocks to have more than one starting point.

Pressing 'Do Animated Rebuild' will start the animation. To cancel mid-animation, press `Ctrl+Z` to revert to the original structure.

## Tool Masks

Clear and open the tool mask editing window. See [Tool Masks](toolmasks.md)

## Window

The **Windows** submenu lets the user toggle [Windows](windows/intro.md). If you ever close a window and want it back, this submenu allows you to re-enable it. With this window, you can also save and restore a default layout.

To store a layout, pressing the 'Store Current Layout as Default' will save your current window layout. To restore the saved layout, press the 'Restore Default Layout' button. You can export and import layouts to and from your clipboard.

## Keybinds

The **Keybinds** button opens a window to edit and set keybinds for tools and operations.

## Help
    
The **Help** submenu contains useful information and configuration options.

The dropdown contains links to information and resources. The [style editor](windows/themes.md) can be accessed through this window, allowing you to change and import custom colours for the Editor UI. 

## Notes

[^note1]: For versions 3.1.0 and below, a bug caused 'Start Delay' to be measured in ticks rather than seconds.