# Paths

The path tool allows you create curves in 3d space using gizmos as nodes. Click on any point to create a gizmo. It will be automatically selected. Click `ctrl + z` or the undo keybind to remove the currently selected gizmo.

# Curve types

You may select from Linear(Bresenham), Linear(DDA), Catenary, Catmull-Rom Spline, and Bezier curve.

# Linear(Bresenham)

This creates a straight line from node to node. Diagonal blocks are not filled in. You cannot change the radius and shape.

![Linear(Bresenham)](https://imagedelivery.net/W9K_l6ndK9x4x8m3rurakg/5fd8e02b-0698-453c-8f90-cbd716807d00/original)

# Linear(DDA)

This also creates a straight line from node to node. The diagonal blocks are filled in. You may change the radius and shape.
![Linear(DDA)](https://imagedelivery.net/W9K_l6ndK9x4x8m3rurakg/b9d88f87-5f1a-4e87-deb1-60a6485e1300/original)

# Catenary

This creates a line which has some slack. It dangles down from node to node. The diagonal blocks are filled in. You may change the radius and shape.

There are two more parameters for this curve. You may invert it such that it is flipped upside down. You may also adjust the slack, a 0% slack is a straight line.

![Catenary](https://imagedelivery.net/W9K_l6ndK9x4x8m3rurakg/90849c39-9774-4ad7-377a-efed21509400/original)

# Catmull-Rom Spline
This type of spline is particularly useful for creating smooth paths. The spline passes through every node. The spline is also continuously smoothed between nodes evenly*.

![Catmull-Rom Spline](https://imagedelivery.net/W9K_l6ndK9x4x8m3rurakg/d2b12da7-3514-4be9-6ba1-3ae1d589d900/original)

# Bezier Curve

A Bezier curve is formed by specifying a set of nodess that influence the shape of the curve. The curve starts at the first nodes, ends at the last node, and is influenced by the positions of the intermediate control points. The curve smoothly interpolates between the control points. The curve does NOT pass through all the nodes. The nodes other than the start and end nodes affect how the curve is shaped.
[Read more here](https://www.wikiwand.com/en/B%C3%A9zier_curve)

![Bezier Curve](https://imagedelivery.net/W9K_l6ndK9x4x8m3rurakg/24a41357-17ef-4403-8ecd-6994d06cad00/original)

# Additional curve options

Looped: When enabled, this connects the first and last nodes, forming a loop.

# Node specific options

**Overried Block**

This option allows you to override the block for that node. It forms a gradient between the connected node(s). If this option is not enabled, the active block is used by default, forming a gradient with that block.

**Override Radius**

This option allows you to override the radius for that node. When enabled, the radius will smoothly transition between each node, allowing you to create curves with changes in thickness.

**Catmull-Rom Spline Easing**

You may select between Linear, Slight, Quadratic, Cubic, or Quartic easing. Each easing looks different. This only affects the easing of the selected node.