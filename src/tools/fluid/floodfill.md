# Floodfill

The floodfill tool fills a chosen area with the provided amount of blocks to place. The [Active Block](/editor/windows/activeblock.md) is the block used to fill an area.

By default the tool fills an area by equally spreading across and down from the selected starting position. The amount of blocks used can be set using the **Limit** Slider in the [Tool Options](/editor/windows/tooloptions.md), and a visualisation of the floodfill is shown when hovering over the [Main View Window](/editor/windows/views.md).

The **Up** option is a toggle which makes the tool only fill blocks that are located above and on the same layer as the cursor.

The **Down** option is a toggle which makes the tool only fill blocks that are located below and on the same layers as the cursor.

The **Horizontal** option is a toggle which allows the tool to spread across the area to be filled. 

The **Corners** option is a toggle which requires 'Horizontal' to be enabled. It will allow the tool to extend the area to be filled by including corner blocks which results in a boxier shape.

Using right-click will initiate a floodfill at the position of your cursor.