# Script Brush

The Script Brush is a very powerful tool, it processes Lua code input which can be used to alter blocks based on multiple conditions.

Assuming you know some programming basics, this documentation will teach and simplify the tool in it's entirety. 

The Lua programming language is similar to Python, but is more lightweight. Hence why it was used in the mod.

### Script Examples

Even though the Script Brush can do almost anything, there are some things that it can't do so well. These include generating structures or anything that requires hard coding. The following examples may vary in difficulty.

- Terrain Generator
- Texturing Brush
- Rock Generator
- Crop Painter
- Spike Generator
- Cave Generator

## Tool Options

The [Tool Options](/editor/windows/tooloptions.md) window is used to enter code. [Presets](/editor/toolpresets.md) can be used to save code to be used later.

## Custom Variables

These two variables allow you to interact with coordinates and retrieve Blockstate IDs.

### x, y, z

The values of these three variables represent the position of the [Target Block](/tools/intro.md#target-blocks). Meaning using these three values is much better than hardcoding specific coordinates.

```lua
if y<100 then
--If the target block has a y level of less than 100
    -- Do Something
end
```

### blocks

The blocks object (or table) allows searching for Blockstate IDs. Blockstate IDs are numerical values used to represent a block state. You shouldn't use these values directly as it can get confusing. 

> Blockstate IDs are not the same as Block IDs[^note1].

```lua
dirt=blocks.coarse_dirt
```

## Custom Functions

Custom functions allow for further use of the two variables when combined.

### getBlock(x,y,z)

Returns the Blockstate ID value for the given coordinate. This function **does not** return a Blockstate ID with block properties.

In this example, I use `return` to place a block at the [Target Block](/tools/intro.md#target-blocks) position using `blocks.dirt`. Not to be confused with setBlock.

```lua
if getBlock(x,y,z)==blocks.grass_block then
    -- get the target Blockstate ID and check if it matches the grass_block Blockstate ID
    return blocks.dirt
end
```


### setBlock(x,y,z,`Blockstate ID`)

The setBlock function is another method to place blocks. Unlike using return, the position can be added without stopping the script.

An offset to the block placement can be added as it uses the XYZ variables. Using the setBlock function instead of return enables the ability to set more than one block for every Target Block process.

```lua
carpetFitForAKing=blocks.pink_carpet

if getBlock(x,y-1,z)~=blocks.air and getBlock(x,y,z)==blocks.air then
    -- only allows blocks with an empty block above
    setBlock(x,y,z,carpetFitForAKing)
    -- changes the block at the target block position
end
```

### isSolid(`Blockstate ID`)

The isSolid function returns a boolean if the block has a solid collision box.

```lua
--Represents solid blocks with lime wool, everything else is represented with red glass

currentBlock=getBlock(x,y,z)

if isSolid(currentBlock) then
    setBlock(x,y,z,blocks.lime_wool)
else
    setBlock(x,y,z,blocks.red_stained_glass)
end
```

### getHighestBlockYAt(x,z)

Returns the Y axis value for the highest block at the given x and z position. Unlike the other functions, this one returns a number between -64 and 319.

```lua
highestBlock=getHighestBlockYAt(x,z)

if highestBlock > 100 then
-- checks if the highest block is above Y=100
    setBlock(x,highestBlock,z,blocks.snow_block)
end
```

### withBlockProperty(`Blockstate ID`,`Property=Value`)

The withBlockProperty function allows for adding properties to existing Blockstate IDs. This removes the limitation of using the [blocks object](#blocks) to set blocks in the world.

```lua
--Replaces wheat with its fully aged variant

if getBlock(x,y,z)==blocks.wheat then
    agedWheat=withBlockProperty(blocks.wheat,'age=7')

    setBlock(x,y,z,agedWheat)
end
```

### getBlockState(x,y,z)

Unlike [getBlock](#getblockxyz), this function returns the exact Blockstate ID for the provided coordinate. 

```lua
--Replaces fully grown wheat with new wheat

currentBlockState=getBlockState(x,y,z)
--gets the exact blockstate ID for the target block 

agedWheat=withBlockProperty(blocks.wheat,'age=7')
newWheat=withBlockProperty(blocks.wheat,'age=0')
--defines fully aged wheat and new wheat

if currentBlockState==agedWheat then
--check if the target block is wheat with the age of 7
    setBlock(x,y,z,newWheat)
end
```

### getBlockProperty(`Blockstate ID`,`Property`)

The getBlockProperty function returns the value for the provided Blockstate ID and Property. Block Properties[^note2] are attributes used by Minecraft to determine things like stair rotation and redstone power levels.

```lua
--Checks if the target block can be waterlogged, and waterlogs it if possible

currentBlockState=getBlockState(x,y,z)

if getBlockProperty(currentBlock,'waterlogged')=='false' then
    --Checks if the block isn't waterlogged. Only waterloggable blocks have this property

    waterloggedBlock=withBlockProperty(currentBlock,'waterlogged=true')
    --Gets the waterlogged variant of the current block
    setBlock(x,y,z,waterloggedBlock)
end
```

### isBlockTagged(`Blockstate ID`,`Tag`)

This function can be used to check if a block is within a group such as fences or logs. This can reduce the use of manually listing blocks, saving performance in your script. The function returns true or false if the two block is within the tag group[^note3].

```lua
--Replaces all fences with their oak variant

oakFence=blocks.oak_fence
currentBlock=getBlock(x,y,z)

if isBlockTagged(currentBlock,fences) then
    setBlock(x,y,z,oakFence)
end
```

## findClosestBlockToRGB(`RGB triplet color`, `flags bitarray (integer)`, `index`)

Returns a blockstate id of the closest block to the RGB value. The RGB value is represented as an RGB merged binary triplet, where first second and third eight bit pairs represent r, g, b color values of the block accordingly. You can filter the block lookup list with flags, similar to how the color picker and gradient tools work. All flags are listed below. You can shift the picked block from the list by inputting an index, getting an i-th closest match to the hex.

```
Flags formatting:
add 1 to use solid-only blocks
add 2 to use opaque-only blocks
add 4 to use 1x1x1-only blocks
add 8 to use all sides-only blocks
add 16 to use no ores
add 32 to use no glazed terracota
add 64 to use no tile entities
```


```lua
function rgbToTriplet(r, g, b)
return r*(256^2) + g*256 + b
end

-- places the definitively bluest block in the game

color = rgbToHex(0, 0, 255)
block = findClosestBlockToRGB(color, 0, 1)
return block
```

### getBlockRGB(`Blockstate ID`)

Returns the RGB triplet of a given block in one number, where first second and third eight bit pairs represent r, g, b color values of the block accordingly. You can split the merged triplet value into separate R, G, and B values with the modulus operator like in the example. It returns a ```nil``` value for blocks like air, so it needs handling for such cases.
```lua
--This function converts the RGB merged triplet value into separate rgb values, stored in a table
function tripletToRGB(triplet)
  local r = math.floor( triplet/(256^2) )
  local g = math.floor( (triplet%(256^2))/256 )
  local b = triplet%256
return {r, g, b}
end
function vecScale(vec, scale)
  local x = vec[1]*scale
  local y = vec[2]*scale
  local z = vec[3]*scale
return{x, y, z}
end
function vecFloor(vec)
  local x = math.floor(vec[1])
  local y = math.floor(vec[2])
  local z = math.floor(vec[3])
return{x, y, z}
end
function rgbToTriplet(rgb_vec)
-- You need to round your rgb values to an integer to avoid artifacts if doing vector math, I'm doing that with the floor function
truncated_vector = vecFloor(rgb_vec)
return truncated_vector[1]*(256^2) + truncated_vector[2]*256 +truncated_vector[3]
end

-- Darkens the block by 10%

multiply = 0.90
block = getBlock(x,y,z)
color_triplet = getBlockRGB(block)
if color_triplet then
color_vector = tripletToRGB(color_triplet)
scaled_color_vector = vecScale(color_vector, 0.90)
darkened_triplet = rgbToTriplet(scaled_color_vector)
darkened_block = findClosestBlockToRGB(darkened_triplet)
return darkened_block
end
```

### getSimplexNoise(x,y,z,`seed`)

The 'getSimplexNoise' function is used to generate 3D noise using the [OpenSimplex](https://code.larus.se/lmas/opensimplex) noise algorithm. The function will return a 'random' float between 1 and 0 depending on the four inputs. 

The seed value only accepts integer values. If the seed value is invalid, it will default to 0. If the seed value is left empty, the seed will be randomized.

```lua
--Places black and white and black concrete using a noise threshold, making an equally distributed pattern.

niceSeed=69
threshold=0.5

if getSimplexNoise(x,y,z,niceSeed)>threshold then
    setBlock(x,y,z,blocks.white_concrete)
else
    setBlock(x,y,z,blocks.black_concrete)
end
```

### getVoroniEdgeNoise(x,y,z,`seed`)

Similar to 'getSimplexNoise', however this function generates a 3D noise using the [Voroni Edge](https://en.wikipedia.org/wiki/Voronoi_diagram) algorithm.

```lua
--Places black and white and black concrete using a noise threshold, making an equally distributed pattern.

niceSeed=420
threshold=0.5

if getVoroniEdgeNoise(x,y,z,niceSeed)>threshold then
    setBlock(x,y,z,blocks.white_concrete)
else
    setBlock(x,y,z,blocks.black_concrete)
end
```

## Template Variables

Template Variables are used control the functionality of the script and to display options directly in the [Tool Options](/editor/windows/tooloptions.md) menu. 

All Template Variables are encased using the '$' character when used in scripts.

### once

The 'once' variable sets the brush to run the script once when using the tool, disabling the 'brush' effect.

This variable does not return a value. It only alters the function of the script itself.

```lua
--sets a singular block of pink wool at the mouse position per use of the brush.

$once$

setBlock(x,y,z,blocks.pink_wool)
```

### blockState(`title`,`default`)

The 'blockState' variable allows the block to be set using the Tool Options menu using a [Block Icon](/editor/intro.md#block-icon-buttons) button. The default option can be set using a Block ID.

```lua
--Places the chosen block in the tool options. By default, oak leaves are chosen. The title: 'Leaf Type' is displayed to the right of the leaf icon

leaf=$blockState(Leaf Type,oak_leaves)$

setBlock(x,y,z,leaf)
```

### int(`title`,`default`,`min`,`max`)

The 'int' variable adds a slider which can be used to input whole numbers into the script using a [Slider](/editor/intro.md#sliders).

```lua
--Creates pink wool pillars with a height which can be modified using the 'Height' slider

$once$

height=$int(Height,5,1,10)$
--default value of 5, minimum value of 1 and maximum value of 10.

for yo=1, height do
	setBlock(x,y+yo,z,blocks.pink_wool)	
end
```

### float(`title`,`default`,`min`,`max`)

Similar to the 'int' variable, but allows for floating point numbers within the [Slider](/editor/intro.md#sliders).

```lua
--Allows for control over the threshold using the 'Threshold' slider

threshold=$float(Threshold,0.5,0,1)$

if getSimplexNoise(x,y,z)>threshold then
    setBlock(x,y,z,blocks.white_concrete)
else
    setBlock(x,y,z,blocks.black_concrete)
end
```

### boolean(`title`,`default`)

Booleans allow for adding toggles to the Tool Options menu.

```lua
--Toggles between green and red concrete using the 'Toggle Green' button

green=$boolean(Toggle Green,true)$
--enabled by default as its set it to true

if green then
	setBlock(x,y,z,blocks.green_concrete)
else
	setBlock(x,y,z,blocks.red_concrete)
end
```

## Notes

[^note1]: [Block IDs](https://minecraft.wiki/w/Java_Edition_data_values/Pre-flattening) were swapped out in favour of the new Blockstate IDs in [1.13](https://minecraft.wiki/w/Java_Edition_1.13).

[^note2]: [The Block Properties Wiki](https://minecraft.wiki/w/Block_properties)

[^note3]: A list of block tags can be found [here](https://minecraft.fandom.com/wiki/Tag#Blocks).
