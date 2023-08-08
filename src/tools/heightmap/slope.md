# Slope

The **Slope** tool is a heightmap tool designed to easily create a ramp or slope between two points, with its function differing slightly from other heightmap tools. In order to start a slope you have to click once to set the target position and then you can drag-click from anywhere else to start drawing a slope between those two points.

On the initial click, a triangle appears displaying details such as height disparity, slope angle, and Euclidean distance between the two points. When you hold down the right-click and drag, a grid plane visible around the initial point of the slope shows the slope's exact angle and provides a rough image of what the final slope will look like.

As for configuration, brush settings allow you to manipulate the height and radius. The sharpness function, similar to other heightmap tools, manages the curvature of the slope at points above and below the tool.

Two modes are available: Plane and Cone. Plane mode operates on a flat surface, whereas Cone mode functions within a spherical region centred on the initial point. The cone's orientation changes depending on whether the target point is above or below your current aim.

However, be cautious when creating a large slope as it may induce lag. For very large slopes, it is suggested to handle smaller areas at a time.
