# File

The 'File' drop-down provides many useful features regarding loading and saving files to use within Axiom. 

## Import Schematic

When pressed, a file explorer window will be opened. Here you can select a schematic to import into Axiom. Both `.schem` and `.schematic` are supported, however only one schematic can be loaded at a time.

After you've opened a schematic in your file explorer, it will be loaded into your [Clipboard](/editor/windows/clipboard.md).

## Export Schematic

The Export Schematic option allows you to export a schematic using your clipboard. Once you have something in your clipboard, you'll be able to export it as a schematic.

For users with a [Commercial License](https://axiom.moulberry.com/commercial), you'll be able to export to any version from 1.7 to 1.19.

## Export Minecraft Structure NBT
Exports a [Selection](/editor/selections.md) to a Named Binary Tag format which makes it possible to load them via structure blocks or the /place command. 
Note that you can export structures of any size, but you can only load structures up to 32x32 blocks using structure blocks. 

## Save Selection as CSV

Exports a [Selection](/editor/selections.md) to a Comma-Seperated Value (CSV) format.

## Open Reference Image

Opens a file explorer window for you to select an image to be loaded into Axiom. Once opened, you can drag and resize the image window to wherever you want. 

Right-Clicking on an image window will display some options to adjust the reference image.

- **Close Window** removes the image.
- **Set Filtering: Nearest** "smoothes" out sharp pixels to reduce the blocky look. 
- **Set Filtering: Linear** stops it from smoothing out pixels, leaving the sharp edges.
- **Show In Game UI** makes it so the image is always shown. When disabled, the image is hidden when outside of the [Editor](/editor/intro.md).
- **Borderless** removes the outer padding and resizing tab.
- **Opacity** lets you set the opacity.

