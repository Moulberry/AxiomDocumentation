# Operations

The **Operations** submenu contains various useful 'operations' to modify blocks within [Selections](/editor/selections.md).

> IMPORTANT: Operations only affect [Selections](/editor/selections.md).

## Fill

The 'Fill' operation fills the selected area of blocks with a specified block. A small [Window](/editor/windows/intro.md) will open, allowing you to choose which block by clicking the block icon. This will open the 'Select Block' Window.

The default keybind for this operation is `Ctrl+F`.

## Fill Nearest

The 'Fill Nearest' operation doesn't use a specified block. Rather, it uses the nearest block that isn't air for each block within the selection.

## Replace

The 'Replace' operation is similar to 'Fill'. However, instead of filling every block in the selection, you can replace a specific block with another.

The default keybind for this operation is `Ctrl+R`. Note that this shortcut is overridden when a [Placement](/editor/placement.md) is active.

## Set Biome

The 'Set Biome' Operation sets the biome within the selection with a specified biome.

## Autoshade

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

## Drain

Removes all water in your selection. This operation also removes the 'waterlogged' property from blocks.

## Waterlog

Replaces all air blocks with water and replaces all water-loggable blocks with their waterlogged variant.

## Smoothsnow

Adds a layer of snow between one and eight layers above existing terrain. No blocks are replaced as existing terrain is prioritised.

The operation attempts to generate snow as smooth as possible.

## Simulate Gravity

The 'Simulate Gravity' operation processes simulates the effect of gravity to all blocks, regardless of whether they normally float or not.

## Trigger Updates

The 'Trigger Updates' operation removes any blocks that are incorrectly positioned.

For example, a floating sign within the selection will be removed.

## Hollow

Fills the inside of the selected object with air, leaving the a shell of the original object.

The 'Hollow' operation also considers transparent/non-solid blocks so having an exterior that includes glass will be accounted for.

## Fill Gaps

The 'Fill Gaps' does the opposite of the 'Hollow' operation, empty space within an object is filled with your active block.

Again, transparent and non-solid blocks are considered.

## Generate Colour Field

The 'Generate Colour Field' operation Generates a colour field using the [CIELAB colour space](https://en.wikipedia.org/wiki/CIELAB_color_space) within a selection.

A colour field (colour space) is a way to organise colours. CIELAB was chosen as it utilises XYZ coordinates to represent LAB. LAB represents three components of the colour space:
### **L - (Lightness)**
- Brightness is mapped to positive X
- Darkness is mapped to negative X
### **A - (Red/Green)**
- Red is mapped to positive Y
- Green is mapped to negative Y
### **B - (Yellow/Blue)**
- Yellow is mapped to positive Z
- Blue is mapped to negative Z

All blocks within the colour field used are full, non-transparent blocks to reduce overlapping.

If two blocks are similar enough, Axiom will attempt to place them in the same position. However, Axiom prevents this by offsetting blocks until there is no overlap. This means there's little chance for blocks to be excluded.

## Analyze

Displays each block type within a selection ordered by the count of each block. A total for both the count and distribution is shown in the last row.  

## Animated Rebuild

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

## Notes

[^note1]: For versions 3.1.0 and below, a bug caused 'Start Delay' to be measured in ticks rather than seconds.