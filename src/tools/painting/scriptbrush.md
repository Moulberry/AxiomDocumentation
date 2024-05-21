# Script Brush

The Script Brush is a very unique tool, the scripting functionality mixed with useful functions can lead to near-unlimited possibilities. The use of clever logic can lead to things like simple texture generators all the way to structural generators.

Although intimidating at first, once you understand the basic concept of programming and have read this documentation, you'll be ready to make your own scripts! 

## Key Points

- The Script Brush is an advanced tool catered towards advanced users. The brush requires some knowledge of programming languages like Python. 

- The Script Brush is similar to [Mask Scripting](/editor/toolmasks.md).

- An IDE[^note1] window is used to input your code. It uses a similar language to Python called Lua[^note2].

> [!TIP]
> Lua doesn't require line indentation like most languages but Axiom provides a tabbing feature to indent. There is only one built-in library[^note3] and there are currently no others.

> [!IMPORTANT]
> The Script must return a block or use setBlock() to modify blocks in the world.

There are many predefined variables and functions that can be used throughout the script to interact with the world. Listed below, are all variables and functions with descriptions and examples.

## Custom Variables

| Variables | Description                                                    | Example      |
|-----------|----------------------------------------------------------------|--------------|
| x,y,z     | These three variables represent the XYZ coordinates.           | if y==5      |
| blocks    | Can be used to retrieve the blockstate[^note4] ID for a block. | blocks.stone |

## Custom Functions

|  <div style="width:100px">Functions</div> | Description                                                                                       | Example                                                        |
|-------------------------------------------|---------------------------------------------------------------------------------------------------|----------------------------------------------------------------|
| getBlock(x,y,z)                           | Returns the block ID at the given position (x,y,z).                                               | getBlock(x,y,z)==blocks.stone                                  |
| getBlockState(x,y,z)                      | Returns the blockstate[^note4] ID at a given position.                                            | getBlockstate(x,y,z)==withBlockProperty(blocks.chain,"axis=x") |
| getHighestBlockYAt(x,z)                   | Returns the Y value of the highest block on the XZ coordinates.                                   | getHighestBlockYAt(x,z)==20                                    |
| getSimplexNoise(x,y,z,seed)               | Returns a value between 0 and 1, representing the Simplex noise for the provided coordinates.     | getSimplexNoise(x,y,z,42)=>0.5                                 |
| getVoroniEdgeNoise(x,y,z,seed)            | Returns a value between 0 and 1, representing the Voroni Edge noise for the provided coordinates. | getVoroniEdgeNoise(x,y,z,01134)=>0.5                           |
| isSolid(block)                            | Returns true if the block is solid, false if not.                                                 | isSolid(getBlock(x,y,z))                                       |
| isBlockTagged(block,"tag")                | Returns true if the block has the provided tag, false if not.                                     | isBlockTagged(getBlock(x,y,z),"wooden_fences")                 |
| withBlockProperty(block,"property=value") | Used to return or set a block with a block property.                                              | withBlockProperty(blocks.oak_slab,"waterlogged=true")          |
| getBlockProperty(block,"property")        | Returns the value of the provided block property.                                                 | getBlockProperty(blocks.oak_slab,"waterlogged")==true          |
| setBlock(x,y,z,block)                     | Set an additional block at a given position.                                                      | setBlock(x,y,z,blocks.stone)                                   |

## Template Variables

Template Variables are not shown in the help text. Template Variables are used to visually display tool settings, removing the need to edit values within the script itself. Most Template Variables Use a **title**, this is used to display the usage or function of the specific Template Variable. The **default** value is used to set the most appropriate value within the range. The **min** and **max** variables are used to set the ranges on sliders.

| Template Variable                     | Description                           | Example                              |
|---------------------------------------|---------------------------------------|--------------------------------------|
| `$once$`                              | Runs the script once per click.       | `$once$`                             |
| `$blockState(title,block)$`           | Allows blocks to be input using GUI.  | `$blockState(Block to Paint,stone)$` |
| `$int(title,default,min,max)$`        | Creates a slider with whole values.   | `$int(Randomness Multiplier,1,0,2)$` |
| `$float(title,default,min,max)$`      | Creates a slider with decimal values. | `$float(Noise Threshold,0.5,0,1)$`   |
| `$boolean(title,default(true/false))$`| Creates a toggle                      | `$boolean(Disable Randomness,true)$` |

<!-- # Spotting And Resolving Errors

These four code examples have some issues with them. As you go down, the problems are harder to solve. You can click on the reveal buttons to see how they would be fixed. 

Each script contains a description of what it should do, alongside the issue.

Feel free to attempt these by debugging using the in-game IDE.

> [!IMPORTANT]
> Comments are marked with `--`, they are not part of the script.

### **Novice**

This script below is very basic, placing short grass on grass blocks. However, if there were more than one layer of grass block, It would replace each layer except for the bottom as it's only checking for blocks below the active block. 

```lua
--Checks if the block below is a grass block
if getBlock(x,y-1,z)==blocks.grass_block then
    --Places short grass
	return blocks.short_grass
end
```

<details>
    <summary>Click to reveal the fix</summary>
    Adding another check will resolve this issue. You could add a check that the target block is air, therefore only the top layer of grass will be affected.
</details>

### **Advanced**

This script incorporates some more logic and function. However, there are three errors within the script. There are no blocks placed when the script is run.

```lua
--Custom Variables
chance=$float(Chance,0.5,0,1)$
multiplier=$float(Multiplier,1,0,2)$

--Noise
noise=getSimplexNoise(x/8,y/8,z/8)

--Check if on water and the target block is air
if getBlockState(x,y-1,z)==blocks.water and getBlockState(x,y,z)==blocks.air and noise<(0.5*multiplier) and math.random() < chance then
    return lily_pad
end
```

<details>
    <summary>Click to reveal the fix</summary>
    The first two errors are that it checks the blockstate with getBlockState. However `blocks` returns the block ID so replacing getBlockState with getBlock will fix the first two errors. The last error is that the script does not return a block ID. It should be `return blocks.lily_pad`. 
</details>

### **Expert** 

This more advanced script places kelp randomly within a maximum height. There are two errors in the script. It always places two block-long floating kelp pieces and the kelp is only placed from a certain depth (It should be placed at any depth).

```lua
--Custom Variables
multiplier=$float(Multiplier,1,0.01,4)$
heightMax=$int(Maximum Height,25,1,50)$

--Random Placement and Random Length
noise=math.random()
length=math.floor(math.random(0,heightMax))

--Check if the block is water and the bottom block of kelp is on a solid surface
if noise<(multiplier*0.1) and isSolid(getBlock(x,y-length,z)) and getBlock(x,y+heightMax,z)==blocks.water then
    --For each block in the length, place a block of kelp
    for block = 0,1 do
        if not isSolid(getBlock(x,y-block,z)) then
            setBlock(x,y-block,z,blocks.kelp_plant)
        end
    end
    --Place the top kelp and end the script
    return blocks.kelp
end
```

<details>
    <summary>Click to reveal the fix</summary>
    The `for` loop has an incorrect range, causing it to only place two blocks. replace `0,1` with `0,length`. The check for water should be at the target block, meaning there should be no offset. Replace it with `getBlock(x,y,z)==blocks.water`.
</details>

### **Professional**

This is one of the most advanced scripts which places flowers in random positions around the active block. However, three errors are present. One has completely stopped the script from running, another causes flowers to always float and the last one returns an error when placing double tall flowers.

```lua
$once$

--Custom Variables
local tries = $int(Tries, 64, 0, 256)$
local xzSpread = $int(XZ Spread, 6, 1, 32)$
local ySpread = $int(Y Spread, 2, 1, 16)$
local block = $blockState(Block, poppy)$

--Random Flower Placement
for i in tries do
	--Calculate Offset
	local xo = math.random(0, xzSpread) - math.random(0, xzSpread)
	local yo = math.random(0, ySpread) - math.random(0, ySpread)
	local zo = math.random(0, xzSpread) - math.random(0, xzSpread)

	if getBlockProperty(block, "half") ~= nil then
		--Logic for double-tall blocks such as rose bushes
		if getBlock(x+xo, y+yo+1, z+zo) == blocks.air and
				getBlock(x+xo, y+yo+2, z+zo) == blocks.air then
			if isSolid(getBlock(x+xo, y+yo, z+zo)) then
				setBlock(x+xo, y+yo+1, z+zo,
						withBlockProperty(block, "half"="lower"))
				setBlock(x+xo, y+yo+2, z+zo,
						withBlockProperty(block, "half"="upper"))
			end
		end
	else
		--Logic for single-tall blocks such as poppies
		if getBlock(x+xo, y+yo+1, z+zo) == blocks.air then
			if not isSolid(getBlock(x+xo, y+yo, z+zo)) then
				setBlock(x+xo, y+yo+1, z+zo, block)
			end
		end
	end
end
```

<details>
    <summary>Click to reveal the fix</summary>
    The first error was caused by the `for` loop using incorrect syntax. The proper syntax would be `for i=0, tries do`. The second error is split into two, both block properties for the upper and lower halves are incorrect. They should be "half=lower" for example. The last error which caused floating flowers, was caused by an incorrect operator. The last check before placing the one tall flower should exclude the `not` operator.
</details>--> 

## References

[^note1]: An integrated development environment (IDE) is a software application that provides comprehensive facilities for software development.

[^note2]: Lua is a lightweight programming language designed for embedded use within applications.

[^note3]: The [Math Library](https://www.lua.org/pil/18.html) is the only built-in library in the Script Brush.

[^note4]: Blockstate IDs are calculated using [Block IDs](https://minecraftitemids.com/). The formula for blockstate IDs is `-n-x` where n is the Block ID and x is the block state.
