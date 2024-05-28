# ![](/img/buildertools/smear.png) Smear

Stretches blocks between two points.

## Creating Selections

To create a selection, start by using left-click to select your first corner and then right-click to select the second. You can use middle-click to select faces instead of the corners. This makes it much easier to select blocks that don't already have edges.

See below for a demonstration. The initial selection is made with a Left & Right click, which is then further expanded to include the whole tree using three middle-clicks.

## Smearing Selections

Once you're happy with your selection, you can smear it by scrolling with the mouse wheel. Now, a hologram will represent the selection you'll be working with. You will also be presented with different controls, using middle-click you can smear the selection to the direction you're facing.

Using the scroll wheel, you can nudge the selection by one block. Scrolling up will push the selection away from the player and scrolling down will bring the selection closer to the player, so the direction the player is facing determines the direction the selection is pulled or pushed. The arrows on the faces of your selection will indicate the scroll up direction.

By holding the 'X', 'Y' or 'Z' keys, you can force the selection to smear in a single axis. For example, holding the 'X' key while nudging the selection will force it to smear on the X axis only.

## Smearing Properties

The path between the origin point and your selection must not include any solid blocks. Solid blocks in the path of your smear will cut it off.

This means it's best to use a 3D object for a 3D stretch, a 2D object for a 2D stretch and so on. This ensures the stretch looks best for your application.

Below is a demonstration of the smear tool. The player builds a roof by smearing two rows of blocks.

<video width="960" height="520" controls autoplay loop>
    <source src="/img/SmearTool.mp4" type="video/mp4">
</video>
