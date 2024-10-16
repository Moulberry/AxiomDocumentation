# Editor Mode

The Editor Mode includes a large variety of tools and operations for large-scale world manipulation, painting, terraforming and sculpting. The Editor UI has been designed specially for this purpose, combining camera controls from conventional 3D software with powerful tools tailored for Minecraft building. The layout of the Editor UI can be customized by [Theming](/editor/windows/intro.md#themes) and [docking](/editor/windows/intro.md#docking) the windows to your liking.

To open the Editor mode, press the Right Shift key located below the 'Enter' key. If you don't have a Right Shift key, you can change this keybind in the Minecraft 'Controls' settings menu under the 'Axiom' section.

## Basic Keybinds

There are many keybinds which may be familiar in the Editor Mode:

- Cut: Ctrl+X
- Copy: Ctrl+C
- Paste: Ctrl+V
- Undo: Ctrl+Z
- Redo: Ctrl+Y

The default placement keybinds may be more unique to Axiom's functionality, however they still have a sense of familiarity:

- Rotate: Ctrl+R
- Flip: Ctrl+F
- Confirm: Enter
- Delete: Delete / Backspace

Most keybinds for the Editor Mode can be changed in the [Keybinds Window](/editor/mainmenubar/intro.md#keybinds).

## Menu Bars 

At the very top of the screen, the [Main Menu Bar](/editor/mainmenubar/intro.md) can be found containing items such as 'File' and 'View'.

The lower menu bar is located opposite of the Main Menu Bar, at the bottom of the screen. On the left of this menu are some tooltips for keybinds which can be used. If you have an active selection, it will be shown here as the last item on the list.  

On the right side of the list is the Flight Speed [Slider](#sliders) which can be used to alter the player flight speed. 

## User Interface Elements

Throughout the Editor mode, these interactive features appear throughout the interface. Below are all types along with their descriptions respectively.

### Sliders

Sliders are represented as an elongated, clickable box with a 'Slider Grab' located within the field. Clicking anywhere on a slider will alter the numerical value shown within the field. This numerical value will affect the described option to the right of the field.

Sliders have an upper and lower limit. However, these can be avoided by using `Ctrl + Click` while hovering the cursor over the slider. Doing this will allow for any numerical input. However, any input must respect the slider type.

There are two types of slider which define the precision of input. The 'integer' only allows for whole numbers to be set or input and the 'float' slider allows for any decimal input. However, each slider has its own limit to the number of decimal places which can be used. When inputting a custom value, if the number of decimal places exceeds the pre-defined amount, the input will be rounded to the nearest decimal number. The same applies for inputting decimals in 'integer' sliders.

### Drop-Downs

Drop-Downs are also represented as an elongated, clickable box. However, drop-downs feature an arrow to the right of the drop-down to represent the functionality of a drop-down. The currently selected option of the drop-down is shown within the button portion itself, and the description for the drop-down is located to the right, outside the drop-down.

Clicking the drop-down with left-click will open a small menu with all items within. In Axiom, drop-downs are used to control the functionality of a specific operation. For example, most tools use a 'Shape' drop-down in the [Tool Options](/editor/windows/tooloptions.md) which allows for multiple brush shapes within the same option.

Some drop-downs can be searched through, allowing easy retrieval of items in longer drop-downs. This can be found in the [Biome Painter](/tools/painting/biomepainter.md) 'Biome' drop-down and the [Tool Presets](/editor/toolpresets.md) drop-down. To search for an item in the drop-down, open the drop-down list and start typing for the desired item.

### Text Boxes

Text boxes are used to set coordinates or provide text for the [Annotation Tool](/tools/utility/annotation.md). To identify a text box, simply hover over a field in the Tool Options and the should change to a 'Text Cursor'. Clicking the text box field will allow you to type any ASCII character.

Some text boxes limit what kind of characters you can input. For example, the 'Factor X' field for the [Modify Tool](/tools/manipulation/modify.md) set to 'Translate Copies' will only allow for integer input.

Integer-based text boxes also support basic mathematical equations such as '24+6' or '73/2', resulting in the equation representing the new value in numerical form. One tool that can use this feature is the [Box Select](/tools/selection/boxselect.md) tool which allows for modifying the 'Position' and 'Size' with this method.

### Toggles

Toggles are used to enable or disable the described functionality. A toggle looks like a small button and when enabled, a small tick will appear within the toggle. To the right of the toggle field is the descriptor for the toggle's functionality.

Toggles feature in most Tool Options and menus. 

### Buttons

Buttons feature in many places throughout the Editor Mode and are essential for accessing menus and operations. Buttons can be found in the [Toolbar](/tools/intro.md) and in the [Annotation Tool](/tools/utility/annotation.md).

#### Block Icon Buttons

Block Icon Buttons are similar to buttons, however most Block Icon Buttons open the [Select Block Window](windows/intro.md#select-block) which allows for changing the block within the button. The block is shown over the button as a 2.5D image.

These buttons are used to represent the block to be used for a tool or operation. They appear in many functions such as the [Active Block](/editor/windows/activeblock.md), [Tool Masks](/editor/windows/toolmasks.md) and [Block Palettes](/editor/windows/palette.md).

Dragging and dropping other Block Icon Buttons onto another will copy the same block over to quickly alter the block. Using middle-click to drag a block from the game window into a Block Icon Button will also copy that block but instead from the world.

### Lua Code Editor

The Lua code editor is used for [Mask Scripting](/editor/windows/toolmasks.md) and the [Script Brush](/tools/painting/scriptbrush.md). The code editor includes a line count on the left and the ability to use the tab key to indent lines.

A basic syntax highlighter is used for the code editor. Syntax errors will result in the erroneous line to be highlighted.

| Trigger                 | Colour     |
| ----------------------- | ---------- |
| Built-in Functions      | Mint       |
| Comments                | Dark Green |
| Floats and Integers     | Lime       |
| Logic Operators         | Blue       |
| Mathematical Operators  | White      |
| Strings                 | Orange     |
| Variables and Functions | Light Grey |
