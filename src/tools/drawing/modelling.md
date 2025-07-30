# Modelling

The **Modelling** tool allows for plotting multiple interconnecting points in a 3D environment which are forming custom surfaces and shapes using the [Active Block](/editor/windows/activeblock.md) to determine which block is being used for them.

Furthermore the surface options feature the ability to link multiple points together, forming a `row`. Multiple rows can be added and will be assigned an index. Points within rows are only able to connect to points of adjacent rows. These properties will form a lofted surface which will differ depending on which algorithm is being used to calculate the mesh connecting rows and points with each other.

## Shapes
| Shapes  | Description                              |
| --------- | ---------------------------------------- |
| Convex Hull     | Creates a shape based on the smallest convex set that encloses all points.              |
| Triangle Strip | Creates a set of triangles that are being created by connecting the last added vertex to the previous two vertices. |
| Triangle Fan| Creates a set of triangles that share one central vertex.|

| Surfaces  | Description                              |
| --------- | ---------------------------------------- |
|Flat|Creates a flat surface by filling in the shortest path between rows and points.|
|Catmull-Rom|Creates a surface composed of smooth curves that pass through every point.|
|Bezier|Creates a surface composed of smooth curves that pass through the corner points and approximate the intermediate points.|
| Smart Surface      | Creates a shape that adapts to the placement of points. Doesn't use rows.                |


## Placement

| Placement           | Description                         |
|---------------------|-------------------------------------|
| Offset target point | Offsets the placed point when placing it |


## Paste

| Paste         | Description                                                     |
| ------------- | --------------------------------------------------------------- |
| Keep Existing | Disables the overriding of other blocks when placing the shape. |
| Paste Copy    | Places a copy of the shape at the current position.             |