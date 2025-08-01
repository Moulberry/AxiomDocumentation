# Path

The **path** tool features the ability to set multiple points in a 3D environment and choose how each point is connected with blocks.

The block used is determined by the [Active Block](/editor/windows/activeblock.md)

You can choose from either a line or a curved path to connect the points. There are multiple variants for both lines and curves:

- Line
  - Bresenham
  - DDA
- Curve
  - Catenary
  - Catmull-Rom Spline
  - Bezier Curve

## Path Types

### Line (Bresenham)

- A line which is always one block wide and only changes angle once it has reached a node. This is the only path type without a modifiable width.

### Line (DDA)

- Unlike the Bresenham Line, the DDA has a modifiable width using the **Radius** slider, allowing for rounded path lines.

### Catenary

- This path type creates the effect of hanging rope or bunting. For each point, the path takes a 'dipped' approach to the next point. You can increase the slack by increasing the **Slack** slider.

  You can also invert the slack direction by enabling the **Inverted** button.

### Catmull-Rom Spline

- This path type smoothes out the path direction while still reaching each node.

### Bezier Curve

- The Bezier Curve path type smoothes the path but isn't required to reach each node except for the start and end nodes. Unlike the Catmull-Rom Spline, the nodes influence the direction rather than direct it.

## Path Tool Options

| Option               | Description                                                                                                                                                                                                             |
| -------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Looped               | Connects the end position to the start position to form a loop.                                                                                                                                                         |
| Use Stairs and Slabs | This option only appears when using a block with stair or slab variants such as stone or planks. It smooths out the path by adding stairs and slabs to the curve or line. This works best with a radius of one or more. |
| Shape                | Allows you to change the path shape between sphere, flat and [Clipboard](/editor/windows/clipboard.md). This setting is not available for the Bresenham line.                                                           |
| Radius               | Used to adjust the width of the chosen shape between a spherical or flat surface.                                                                                                                                       |
| Keep Existing        | When enabled, all existing blocks will not be overridden by the path.                                                                                                                                                   |
| Extend to Ground     | When enabled, the path is extended to the ground until it reaches a solid surface.                                                                                                                                      |
| Paste Copy           | The 'Paste Copy' button places the path while allowing you to continue editing it.                                                                                                                                      |

## Node Options

When an individual node is selected, you can adjust the position using the [Gizmo](/editor/gizmos.md).

Alongside adjusting node positions, you can modify the node properties individually.

| Option          | Description                                                                                                                                                        |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Position        | Allows for changing the coordinates of the selected node directly.                                                                                                 |
| Override Block  | Allows for overriding the block used for the node. The blocks between each node are blended using a [Bezier gradient](/painting/gradientpainter.md#interpolation). |
| Override Radius | Enables the ability to set a radius for that node specifically. The path smoothly increases width along two points.                                                |
| Remove          | Deletes the current node. This can also be done by pressing the `Del` or `Backspace` key.                                                                          |