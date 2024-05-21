# Script Brush

The Script Brush is a very unique tool, the scripting functionality mixed with useful functions can lead to near-unlimited possibilities. The use of clever logic can lead to things like simple texture generators all the way to structural generators.

Although intimidating at first, once you understand the basic concept of programming and have read this documentation, you'll be ready to make your own scripts! 

## Key Points

- The Script Brush is a powerful, yet advanced tool so some knowledge of programming languages similar to Python is recommended. 

- The Script Brush is similar to [Mask Scripting](/editor/toolmasks.md).

- An IDE[^note1] window is used to input your code. It uses a similar language to Python called Lua[^note2].

> [!TIP]
> Lua doesn't require line indentation like most languages but Axiom provides a tabbing feature to indent. 
> 
> There is only one built-in library[^note3] and there are currently no others.

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

# Code Examples

These four code examples range from a novice user all the way to a professional in terms of difficulty. Each script provides a description and a breakdown of how the script works.

> [!NOTE]
> Feel free to copy these and mess around with them.

### **Novice**

This script below is very basic, it replaces oak leaves with birch leaves.

```lua
if getBlock(x,y,z)==blocks.oak_leaves then
	return blocks.birch_leaves
end
```

<details>
    <summary>Novice Code Breakdown</summary>

    The if check ensures that the current block is oak leaves. Using "getBlock(x,y,z)" targets the active block. 
	
	Then "blocks.oak_leaves" is used to check if the block IDs match.

	Finally, the script returns birch leaves, therefore replacing oak leaves.

</details>

### **Advanced**

This script places pink petal flowers using simplex noise to control the block property.

```lua
multiplier=$float(Multiplier,1,0,2)$
noise=getSimplexNoise(x/8,y/8,z/8)

if getBlock(x,y,z)==blocks.air and isSolid(getBlock(x,y-1,z)) and noise<(0.75*multiplier) then
    return withBlockProperty(blocks.pink_petals,"flower_amount="..math.floor((getSimplexNoise(x/2,y/2,z/2,0)*4)))
end
```

<details>
    <summary>Advanced Code Breakdown</summary>

	Firstly, The multiplier and noise variables by utilising the float variable and the simplex noise function.
	
	Then the script checks that the block is air and is above a solid surface while also checking if the noise is within range.

	Finally, the block is placed using "withBlockProperty" to set the flower amount property. This uses a modified simplex noise that returns values between 0 and 4.

</details>

### **Expert** 

The script below generates kelp in water using a maximum height to control the length of kelp.

```lua
multiplier=$float(Multiplier,1,0.01,4)$
heightMax=$int(Maximum Height,25,1,50)$

noise=math.random()
length=math.floor(math.random(0,heightMax))

if noise<(multiplier*0.1) and isSolid(getBlock(x,y-length,z)) and getBlock(x,y,z)==blocks.water then
    for block = 0,length do
        if not isSolid(getBlock(x,y-block,z)) then
            setBlock(x,y-block,z,blocks.kelp_plant)
        end
    end
    return blocks.kelp
end
```

<details>
    <summary>Expert Code Breakdown</summary>

    Firstly, the script defines all the variables. 
	
	As the script builds the kelp from top to bottom, it checks if the lowest attemptable block is solid.  
	
	Then, for each solid block, the script places a kelp plant.

	Once all kelp plant blocks are placed, the script then sets the active block to be the top piece of kelp. 

</details>

### **Professional**

This final script creates a curved bowl shape using mathematical formulae. This is one of the most complex types of script brushes in Axiom.

```lua
$once$
scale = $int(Scale,30,10,50)$
flatness = $float(Bowl Flatness,0.8,0.1,2.5)$
tolerance = (scale*10)*flatness
block=$blockState(Block)$

for DistX = -scale, scale do
    for DistY = -scale, scale do
        for DistZ = -scale, scale do
            local formulaL = DistX^2 + DistY^2 + (DistZ^1.5)*-(flatness*10)^2
            local formulaR = 0
            if (formulaL - formulaR) <= tolerance then
                setBlock(x + DistX, y + DistZ, z + DistY, block)
            end
        end
    end
end
```

<details>
    <summary>Professional Code Breakdown</summary>

    This script represents the following equation:
	(X²+Y²+(Z¹.⁵)(-n)10^2)=0
	Where n is the flatness variable. 
	
	The script draws the 3D shape by using a loop for each axis.

</details>

## References

[^note1]: An integrated development environment (IDE) is a software application that provides comprehensive facilities for software development.

[^note2]: Lua is a lightweight programming language designed for embedded use within applications.

[^note3]: The [Math Library](https://www.lua.org/pil/18.html) is the only built-in library in the Script Brush.

[^note4]: Blockstate IDs are calculated using [Block IDs](https://minecraftitemids.com/). The formula for blockstate IDs is `-n-x` where n is the Block ID and x is the block state.
