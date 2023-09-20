# Gradient Painter

The **Gradient Painter** tools allows you to paint gradients using multiple blocks.

To use, click on pos1 and you will see a line appear. Click and drag to paint from pos2. 

The **Mask Surface** option allows only painting blocks which are adjacent to a non-solid block.

# Planar vs Spherical Gradients

You may select the type of gradient to be either spherical or planar.

![Plane vs Sphere in gradient selection](https://cdn.discordapp.com/attachments/1012669638578020403/1153873402931724417/2023-09-19_21.46.32.png)

As you can see, for the "Plane" option, the gradient goes from pos1 to pos2 in one direction. For the "Sphere" option, The gradient radiates from pos1 to pos2, with pos2 being the radius, and pos1 being the center(i.e. starting point)

# Interpolation

You may select the type of interpolation to be used: Nearest, Linear, and Bezier. See the difference below:

In order from top to bottom: Nearest, Linear, Bezier.

![Interpolation](https://cdn.discordapp.com/attachments/1012669638578020403/1153874160502722641/2023-09-19_21.24.42.png)

Look up the curves to see how it is calculated specifically but in essence, nearest gives you hard boundaries between each block type. Linear gives a smooth transistion as the name implies, and Bezier has a more rapid change in the center, and eases in/out. The effect is more apparent with larger gradients.

# Locking

You may select between no locking, locking only pos1, and locking both pos1 and pos2. 

No locking makes it so that the start and end points of the gradient change with every stroke

Locking only pos1 makes it so that the starting point of the gradient remains fixed even after you release the mouse button. However pos2 remains unfixed such that the length of the gradient can change freely.

Locking both pos1 and pos2 makes it so that the gradient's start and end points remains fixed, and you can use multiple strokes to cover the same area with the same effect.

To unlock the points select locking to "none".

# Clamp to edge

If this option is enabled, the gradient will be applied in such a way that it doesn't extend beyond pos2.