# Select
    
The Select submenu lets users perform a variety of functions to modify [Selections](/tools/selection/intro.md). Blocks within the selection are not factored in the following options, only the selection shape is modified.

## Expand

 - Expands the selection surface with the provided offset.
  
## Shrink

 - Shrinks the selection surface with the provided offset.

## Distort

 - Distorts the current selection with simplex noise by a specified radius and distance. Radius is the size of the noise pattern and the distance controls the distortion intensity.

## Smooth

 - Applies a Gaussian blur on the selection to smooth out the selection. StdDev is the intensity of the smoothing operation and the threshold is the 'cut-off' of how much input weight is needed to affect the output.

## Bounding Box

 - Creates a cuboid selection using the furthest points of the original selection. This option is only available when the selection isn't cuboid.

## Convex Hull

 - The Convex Hull function takes a concave selection and turns it convex, basically connecting a selection to create a solid shape. This option is only available when a shape is concave.