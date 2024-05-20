# Tool Masks

Tool Masks empower users to set up rules for tools, applying their effects only when certain conditions are met. Leveraging boolean logic, Tool Masks allow users to specify block conditions across a variety of scenarios, such as affecting only blocks with air above them or a particular type of block beneath. These rule configurations, known as 'Rule Blocks', can be easily arranged in the tool menu via a drag-and-drop interface, providing a user-friendly alternative to scripting languages. The configuration of your mask is displayed as a string at the top of the menu for easy copying, sharing, and saving. The mask logic generates a boolean output, signifying either 'true' or 'false'.
    
The conditions fall into two main categories: Logic and Masks.
    
## Logic conditions

Combining these logic conditions allows for a broad range of expressions in masks, enabling you to select almost all blocks meeting specific criteria.

| Logic      | Description                                                                                                                                                                                                                                                                                                                                                      |
|------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **OR**     | The `OR` condition enables any rules within this block to take effect. For example, when selecting multiple blocks to mask, select blocks that match grass_block `OR` stone.                                                                                                                                                                                     |
| **AND**    | The `AND` condition requires all rules within this block to apply. For instance, if you want to select a block that has air above and dirt below it. However, conflicting rules won't function in the same `ANY` block, meaning you can't have two `block =` masks or two `above =` masks simultaneously. But, it's possible to nest another `AND` block inside. |
| **NOT**    | The `NOT` condition reverses the rule outcomes, making them true only when the original conditions are not met. For example, setting the rule `above = air` within a `NOT` block selects all blocks that do not have air above them.                                                                                                                             |
| **OFFSET** | The `OFFSET` condition allows coordinate input to apply a mask for a nearby block relative to the current block. For example, using `offset(0,-1,0){ surface }` will mask block 1 block above the surface.                                                                                                                                                       |

## Masks
    
Masks are conditions that depend on the target's state or the surrounding blocks' state.

| Mask             | Description                                                                                                                                                                                                                                                         |
|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Block**        | The `Block` mask returns true when the target matches the specified block or block state.                                                                                                                                                                           |
| **Above**        | The `Above` condition is true when the block directly above the target block matches the specified block or block state.                                                                                                                                            |
| **Below**        | The `Below` condition is true when the block directly below the target block matches the specified block or block state.                                                                                                                                            |
| **Near**         | The `Near` condition is true when any of the blocks in the set radius surrounding the target match the specified block or block state.                                                                                                                              |
| **Neighbour**    | The `Neighbor` condition returns true when any of the six blocks directly adjacent (up, down, north, south, east, west) to the target match the specified block or block state which allows the mask to check the immediate vicinity of the target block.           |
| **Adjacent**     | The `Adjacent` condition returns true when any of the four horizontally touching blocks match the specified block or block state.                                                                                                                                   |
| **Y**            | The `Y` mask returns true when the target aligns with the given condition relating to the block's Y coordinate level. There are several conditions for the Y mask which can be modified by clicking on the `=` sign.                                                |
| **Angle**        | The `Angle` mask utilises two inputs. The `Angle` input is used to mask a specific angle and the `Range` input is how many angles are used originating from the `Angle` input. For example, an angle of 90 and a range of 10 would cover all angles from 80 to 100. |
| **In Selection** | The `In Selection` condition returns true when the target block is within the user-defined selection area.                                                                                                                                                          |
| **Can See Sky**  | The `Can See Sky` condition returns true if the target block has direct access to the sky.                                                                                                                                                                          |
| **Surface**      | The `Surface` mask returns true if the block is adjacent to air or liquids.                                                                                                                                                                                         |

# Scripting

Similar to the [Script Brush](/tools/painting/scriptbrush.md), the mask scripting allows users to input custom scripts using Lua.

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