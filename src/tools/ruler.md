# Ruler Tool

The **Ruler** Tool is designed to measure the distance between two or more points in a world. You can add points to the world by right-clicking. Once you have selected two or more points, a line appears between the most recent point and the one before it. The rounded Euclidean distance, or straight line distance, is shown in the centre of this line. You can keep adding more points as needed.

When you check the tool options, you'll find more information about these points. What's shown depends on whether you've chosen two or more points.

Here's the information you'll see:

- Total Length (Euclidean): This is the straight-line distance from the first point to the last one, as if a bird flew directly there, not caring about the blocks in between.
- Total Length (Manhattan): This is the sum of the horizontal, vertical, and depth distances. In Minecraft terms, it's like how a player would travel: one block up, down, left, right, forward, or backward at a time.
- Minimum: The coordinates of the earliest point in the sequence of points.
- Maximum: The coordinates of the latest point in the sequence of points.
- Bounding Size: The size of the box needed to draw around all the points.
- Yaw (Only visible with two points): The yaw of the line between two points.
- Pitch (Only visible with two points): The pitch of the line between two points.
