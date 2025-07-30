# Gradient Helper

The Gradient Helper is a powerful tool that can be used to create gradients based on the average colour of two or more input blocks.
Using [OKLab](https://en.wikipedia.org/wiki/Oklab_color_space), the gradient helper is interpolating the blocks between the input slots to create a gradient. The size and complexity of the gradient depend on the slots the items are placed in.

## Options

The **Full Cube** (F) option ensures that only **1x1x1** blocks are used to construct the gradient.

The **Solid** (S) option ensures that only **collidable** blocks are used to construct the gradient.

The **Opaque** (O) option ensures that **no transparent** blocks are used to construct the gradient.

The **Same Texture** (T) option ensures that only blocks with uniform textures are used to construct the gradient.

The **Refresh** buttons on the output slots make it possible to cycle to the next or previous best match.

The **Copy to Hotbar** (Book and Quill) option puts the output gradient to your hotbar, replacing existing items.

The **Export to Editor [Gradient Brush](/tools/painting/painter.md) and [Gradient Painter](/tools/painting/gradientpainter.md)** options export the current gradient to the respective block lists of the tool specified.

>Note that blocks with properties thought to be filtered by the 'FSOT' options can still appear in the gradient since mod creators and Mojang need to register the items correctly or in a logical manner. 

![Gradient Helper](/img/gradienthelper.png)


