# Painter

The **Painter** is the most basic painting tool. It allows you to paint blocks with a single type using a brush stroke.

By default, the painter only affects solid blocks, like all painter tools. To make it affect air as well, you need to use [tool masks](/editor/windows/toolmasks.md).

The **Mask Surface** option allows only painting blocks which are adjacent to a non-solid block.

The **Copy Properties** option appears if one of the selected blocks can have block properties. 
Painting with this option enabled will automatically match the properties of blocks you're painting over.

The **Type Replace** option appears if all the selected blocks have variants such as stairs, slabs, and fences, etc. Painting with this option enabled will automatically replace the type of blocks you're painting over and keep their properties in the process.

|Modes|Description|
|-|-|
|Active Block|Paints with your active block|
|Tiled Clipboard|Paints your [Clipboard](/editor/windows/clipboard.md) in a repeating grid pattern|
|Stamped Clipboard|Paints your [Clipboard](/editor/windows/clipboard.md) freely on your cursor|
|Gradient|Simlar to the [Gradient Painter](gradientpainter.md) but instead paints the gradient around the center of the brush. The **Merge Strokes** option prevents the painter from overriding blocks that are in the gradient|