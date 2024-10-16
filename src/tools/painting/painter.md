# Painter

The **Painter** is the most basic painting tool. It allows you to paint blocks with a single type using a brush stroke.

The **Mask Surface** option allows only painting blocks which are adjacent to a non-solid block.

The **Copy Properties** option appears when the [Active Block](/editor/windows/activeblock.md) has a block that has more than one variant. This could include stairs or slabs. When enabled, it replacing existing slabs, stairs, etc to the active block. This is similar to the [Type Replace](/contextmenu/intro.md#Toolbox) found in the [Replace Capability](/contextmenu/capabilitiesreplacemode.md).

The **Mode** drop-down allows switching between Active Block, [Clipboard](/editor/windows/clipboard.md) and Gradient. The active block mode paints with your active block. The clipboard mode paints using your clipboard in a repeating grid pattern. The gradient mode is similar to The [Gradient Painter](gradientpainter.md) but instead paints the gradient around the centre of the brush. The merge strokes option for the gradient mode stops the painter from overriding blocks that are in the gradient. 