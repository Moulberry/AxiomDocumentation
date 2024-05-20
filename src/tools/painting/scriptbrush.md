# Script Brush

The Script Brush is a very unique tool, it allows you to create your own brush. This can be for easing the building process or adding new tools to axiom.

## Key Points

- The Script Brush is an advanced tool catered towards advanced users. The brush requires some knowledge of programming languages like Python. 

- The Script Brush is similar to [Mask Scripting](/editor/toolmasks.md).

- An IDE[^note1] window is used to input your code. It uses a similar language to Python called Lua[^note2].

- Lua doesn't require line indentation like most languages but axiom provides a tabbing feature to indent. There is only one built-in library[^note3] and there are currently no others.

### The Script must return a block or use setBlock() to modify blocks in the world.

There are many predefined variables and functions that can be used throughout the script to interact with the world. Listed below, are all variables and functions with descriptions and examples.

## Custom Variables

| Variables | Description                                                    | Example      |
|-----------|----------------------------------------------------------------|--------------|
| x,y,z     | These three variables represent the XYZ coordinates.           | if y==5      |
| blocks    | Can be used to retrieve the blockstate[^note4] ID for a block. | blocks.stone |

## Custom Functions

|  <div style="width:100px">Functions</div> | Description                                                                                       | Example                                                                        |
|-------------------------------------------|---------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------|
| getBlock(x,y,z)                           | Returns the block ID at the given position (x,y,z).                                               | if getBlock(x,y,z)==blocks.stone                                               |
| getBlockState(x,y,z)                      | Returns the blockstate[^note4] ID at a given position.                                            | if getBlockstate(x,y,z)==withBlockProperty(blocks.chain,"axis=x")              |
| getHighestBlockYAt(x,z)                   | Returns the Y value of the highest block on the XZ coordinates.                                   | if getHighestBlockYAt(x,z)==20                                                 |
| getSimplexNoise(x,y,z,"seed")             | Returns a value between 0 and 1, representing the Simplex noise for the provided coordinates.     | if getSimplexNoise(x,y,z,"WILLATRONIXisCOOL")=>0.5                             |
| getVoroniEdgeNoise(x,y,z,"seed")          | Returns a value between 0 and 1, representing the Voroni Edge noise for the provided coordinates. | if getVoroniEdgeNoise(x,y,z,"coolseed")=>0.5                                   |
| isSolid(block)                            | Returns true if the block is solid, false if not.                                                 | if isSolid(getBlock(x,y,z))                                                    |
| isBlockTagged(block,"tag")                | Returns true if the block has the provided tag, false if not.                                     | if isBlockTagged(getBlock(x,y,z),"wooden_fences")                              |
| withBlockProperty(block,"property=value") | Used to return or set a block with a block property.                                              | withBlockProperty(blocks.oak_slab,"waterlogged=true")                          |
| getBlockProperty(block,"property")        | Returns the value of the provided block property.                                                 | if getBlockProperty(blocks.oak_slab,"waterlogged")==true                       |
| setBlock(x,y,z,block)                     | Set an additional block at a given position.                                                      | setBlock(x,y,z,blocks.stone)                                                   |

## Template Variables

Template Variables are not shown in the help text. Template Variables are used to visually display tool settings, removing the need to edit values within the script itself. Most Template Variables Use a **title**, this is used to display the usage or function of the specific Template Variable. The **default** value is used to set the most appropriate value within the range. The **min** and **max** variables are used to set the ranges on sliders.

| Template Variable                     | Description                           | Example                              |
|---------------------------------------|---------------------------------------|--------------------------------------|
| `$once$`                              | Runs the script once per click.       | `$once$`                             |
| `$blockState(title,block)$`           | Allows blocks to be input using GUI.  | `$blockState(Block to Paint,stone)$` |
| `$int(title,default,min,max)$`        | Creates a slider with whole values.   | `$int(Randomness Multiplier,1,0,2)$` |
| `$float(title,default,min,max)$`      | Creates a slider with decimal values. | `$float(Noise Threshold,0.5,0,1)$`   |
| `$boolean(title,default(true/false))$`| Creates a toggle                      | `$boolean(Disable Randomness,true)$` |

## Code Examples

### The script below places lily pads above water using white noise and simplex noise.

```lua
chance=$float(Chance,0.5,0,1)$
multiplier=$float(Multiplier,1,0,2)$

noise=getSimplexNoise(x/8,y/8,z/8)

if getBlock(x,y-1,z)==blocks.water  and getBlock(x,y,z)==blocks.air and noise<(0.5*multiplier) and math.random()< chance then
    return blocks.lily_pad
end
```

### This more advanced script generates kelp underwater at a set length.

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

## References

[^note1]: An integrated development environment (IDE) is a software application that provides comprehensive facilities for software development.

[^note2]: Lua is a lightweight programming language designed for embedded use within applications.

[^note3]: The [Math Library](https://www.lua.org/pil/18.html) is the only built-in library in the Script Brush.

[^note4]: Blockstate IDs are calculated using [Block IDs](https://minecraftitemids.com/). The formula for blockstate IDs is `-n-x` where n is the Block ID and x is the block state.