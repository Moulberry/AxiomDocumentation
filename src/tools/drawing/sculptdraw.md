# Sculpt Draw

The **Sculpt Draw** tool is a powerful sculpting tool to change shape your terrain and organics. It uses the direction the surface is facing (the surface normal[^note1]) to determine what the peak of the shape should be. Instead of utilizing the active block, the Sculpt Draw tool pulls out existing blocks from the surface. Various settings are available to finetune the tool's sculpting behavior:

- **Radius**: Unlike other brush tools, the radius in the Sculpt Draw tool influences not only the size but also the shape of the sculpted form. Larger radii result in more spherical or ovoid forms, while smaller radii create parabolic shapes.
- **Strength**: This setting determines the intensity of the sculpted shape. The strength slider, ranging exponentially from 0 to 5, can be overridden for higher values. Given the tool's surface-normal approach, different strengths can yield a wide variety of results. This makes it versatile for creating structures such as overhangs, spiky formations, or naturally eroded patterns that seamlessly integrate with existing structures.
- **Invert**: This option toggles between adding to or subtracting from the surface, useful for carving out erosion paths or whittling down organic structures to create natural-looking strokes.
- **Mask Y**: When enabled, this setting causes the tool to only add mass along the Y-axis. This results in a more gradual change rather than abrupt protrusions, making it ideal for shaping the top surfaces of structures in a natural manner.
- **Denoise**: This option applies a denoising algorithm to smooth the shapes drawn by the Sculpt Draw tool. Generally, it's recommended to keep this setting on to enhance the tool's natural look. However, if you desire a rougher, rockier surface, you can disable this option.

[^note1]: The surface normal is a concept from geometry. In simple terms, it's the direction that a particular surface is facing. For example, if you were standing on flat ground in the real world, the surface normal would be straight up. If you were standing on a slope, the surface normal would point out at an angle.
