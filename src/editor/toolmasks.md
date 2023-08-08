# Tool Masks

Tool Masks empower users to set up rules for tools, applying their effects only when certain conditions are met. Leveraging boolean logic, Tool Masks allow users to specify block conditions across a variety of scenarios, such as affecting only blocks with air above them or a particular type of block beneath. These rule configurations, known as 'Rule Blocks', can be easily arranged in the tool menu via a drag-and-drop interface, providing a user-friendly alternative to scripting languages. The configuration of your mask is displayed as a string at the top of the menu for easy copying, sharing, and saving. The mask logic generates a boolean output, signifying either 'true' or 'false'.
    
The conditions fall into two main categories: Logic and Masks.
    
## Logic conditions
    
- **Any**
The 'Any' condition enables any rules within this block to take effect. For example, when selecting multiple blocks to mask, select 'any' block that matches grass_block or stone.

- **All**
The 'All' condition requires all rules within this block to apply. For instance, if you want to select a block that has air above and dirt below it. However, conflicting rules won't function in the same 'All' block, meaning you can't have two 'block =' masks or two 'above =' masks simultaneously. But, it's possible to nest another 'Any' block inside.

- **Not**
The 'Not' condition reverses the rule outcomes, making them true only when the original conditions are not met. For example, setting the rule 'above = air' within a 'Not' block selects all blocks that do not have air above them.
    
Combining these logic conditions allows for a broad range of expressions in masks, enabling you to select almost all blocks meeting specific criteria.
    
## Masks
    
Masks are conditions that depend on the target's state or the surrounding blocks' state.
    
- **Block**
The 'Block' mask returns true when the target matches the specified block or block state.
- **Y**
The 'Y' mask returns true when the target aligns with the given condition relating to the block's Y coordinate level. There are several conditions for the Y mask which can be modified by clicking on the '=' sign.
- **In Selection**
The 'In Selection' condition returns true when the target block is within the user-defined selection area.
- **Above**
The 'Above' condition is true when the block directly above the target block matches the specified block or block state.
- **Below**
The 'Below' condition is true when the block directly below the target block matches the specified block or block state.
- **Near**
The 'Near' condition is true when any of the blocks in the 3x3 area (26 blocks) surrounding the target match the specified block or block state.
- **Neighbor**
The 'Neighbor' condition returns true when any of the six blocks directly adjacent (up, down, north, south, east, west) to the target match the specified block or block state which allows the mask to check the immediate vicinity of the target block.
