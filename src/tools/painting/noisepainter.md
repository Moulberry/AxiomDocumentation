# Noise Painter

The **Noise Painter** is a very versatile painting tool which enables the user to use procedural noises for painting in the world. There is a large variety of noises which can be picked from and configured. Each of which having unique options and patterns useful in different scenarios.

The first unqiue option is the toggle for the ‘3D’ setting. This allows the noise to be calculated in 3D, allowing for the painting of the sides of surfaces instead of just the top.

Next, we have the scale option, which adjusts the size of the noise relative to the block grid. A larger scale means that the noise pattern is spread over a larger area of blocks.

## Noises

There are a few shared settings across the different noises. The common options between these noises are listed below, with sepcific settings for each noise described in their respective sections.

- **Octaves:** This setting determines the number of layers of noise that are used. More octaves result in more detail and complexity but comes with a higher computational cost.
Lacunarity and Gain can only be configured when you have more than one octave for your noise.
- **Lacunarity:** This influences the ‘frequency’ of each octave. A higher value increases the frequency, leading to smaller features in the noise pattern.
- **Gain:** This controls the amplitude of each octave. A higher value will increase the influence of each successive octave. A lower value will make effect of the octavation more subtle.
- **Seed:** The seed value is used to initialize the noise generation algorithm, providing a starting point. Different seeds produce different noise patterns, but the same seed will always produce the same pattern. Keeping the same seed is useful for when you want to continue a pattern rather than starting a new one.
- **Jitter:** This value controls how uniform the cellular noise appears by limiting how much the seed points can move off their starting grid arrangement.<br>
A value of 0.0 will return a perfectly uniform grid pattern, 1.0 returns a minimally uniform pattern.<br>
Applicable only to the cellular noise types **Voronoi Edges**, **Worley**, and **Metaballs**. 

### Simplex
    
Simplex noise generates a smooth, continuous pattern that often resembles a hilly or wavy terrain when visualized.

Simplex noise is an improved version of Perlin noise.
    
### Worley
    
Worley noise, also known as cellular noise, creates a pattern that looks like irregular cells or Voronoi diagrams, with each 'cell' having a distinct point of intensity and fading out towards its borders.
    
- **W1:** This is the weight of the distance of the closest voronoi point.
- **W2:** This is the weight of the distance of the second closest voronoi point.
- **W3:** This is the weight of the distance of the third closest voronoi point.
    
The interplay between W1, W2, and W3 values significantly affects the Worley noise outcome. For example, if W1 is high and W2 and W3 are low, the pattern will have clearly defined, irregular cells. But if W1, W2, and W3 are all high, the pattern will be more complex and interconnected, as it's influenced by multiple nearby points.
    
### Voronoi Edges
    
This type of noise specifically accentuates the edges or boundaries between the cells formed in Voronoi diagrams, resulting in a grid of interconnected lines or a 'cracked' appearance. This is useful for making things like cracks, stone tiles, etc.
    
### Metaball
    
Metaball noise creates a pattern that looks like overlapping blobs or spheres, with smooth transitions between these 'blobs'. Similar to the patterns of blobs in lava lamps.
    
- **Range:** Adjusts the radius around each point that influences the noise. A larger range results in larger, more spread-out blobs, resembling a pattern more reminescent of the aforementioned lavalamp blobs.
    
### White Noise
    
White noise generates a completely random pattern with no discernible structure, looking like static on an old television screen.

## Blocks  

The section beneath the noise configuration allows you to specify the blocks used in painting, as well as determine their distribution within the noise pattern. You can adjust the block distribution by setting a threshold between 0 to 1 or specifying a per-block percentage from 0 to 100%. The threshold setting is particularly useful when you're tweaking parameters for complex noises like Worley.

Clicking the '+' sign adds a new block. Clicking on an existing block allows you to select and add different blocks to your noise pattern. You can also drag and drop palettes and active blocks onto the blocks section.

## Preview

Lastly, beneath the settings, there are three windows to aid in visualizing the noise pattern, cumulative distribution, and probability density:

- **Noise Preview**: As the name suggests, this provides an approximation of how the current noise settings would look, mapped to the voxel grid. It uses a grayscale representation to depict block presence, with white denoting the primary block and the color darkening as more blocks are added. Black signifies no blocks.
- **Cumulative Distribution and Probability Density Visualizers**: These tools are especially useful when you've set the Blocks mode to be threshold-based. They help illustrate how the blocks will be distributed within the noise pattern. The Cumulative Distribution Visualizer provides a graph showing the cumulative percentages of different blocks as the noise threshold increases from 0 to 1. The Probability Density Visualizer gives a sense of how likely each block is to appear at a given noise value. It can help you understand and fine-tune the balance of blocks in your noise pattern.
