# Annotation Tool

The Annotation Tool can be used to draw on and add text to terrain for marking out and planing builds. These annotations can be seen by other players who are using the mod on servers[^note1] if you're using the [commercial license](https://axiom.moulberry.com/commercial).

## Annotation Types

To change annotation type, click one of the six large icons located in the [Tool Options](/editor/windows/tooloptions.md). Hovering over the icons will show you the annotation type.

### Draw

The draw mode is used to draw a line over blocks. The line width can be modified using the appropriate slider.

### Outline

The 'Outline' mode allows for drawing full-block highlights. There are three modes for the outline annotation:

- Freehand
  - Similar to the draw mode, uses the cursor position to draw lines.
- Lines
  - Allows for the ability to specify each point. Pressing the 'Finish Lines' button will confirm the annotation.
- Box
  - Click two points to define the corners of a box, once both points have been set, all blocks excluding air will be annotated.

### Text

The Text mode is used to place text in the world, similar to [Text Displays](/contextmenu/displayentities.md#text-display). 

The 'Shadow' option toggles the shadow effect on the text. The 'Billboard' drop-down determines how the text is shown to the player.

### Image

The Image mode enables the user to import images into the world.

The 'Width' option determines the width of the image and the 'Image URL' option is used to import the image from the web. For example, a valid link would look like: `https://willatronix.com/example.png`. Any invalid link will result in a pink and black texture in place of the image.

### Erase

The Erase option allows for removing annotations by drawing a box across the screen with right-click. Any annotation within this red box will be removed.

This action can be undone with `Ctrl+Z` and redone with `Ctrl+Y`.

### Move

The Move mode is used to relocate images and text created using the annotation tool. Upon approaching an image or text annotation, a node will appear. Clicking this node will provide a [Gizmo](/editor/gizmos.md) to move the annotation.


## Other Tool Options

### Colour Picker

The colour picker can be used to precisely choose what colour you'd like to use for your annotations. 

### Raycast Fluids

When enabled, annotations will collide with liquids such as water.

## Notes

[^note1]: Servers may deny the permission to use annotations as it can lead to issues regarding server performance.