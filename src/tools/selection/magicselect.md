# Magic Select

The **Magic Select** tool is a powerful selection tool which improves the building process immensely if used correctly. With a single click on a block type, the Magic Selection tool swiftly selects all adjacent blocks of the same type, streamlining the selection process.

The tool features the following options:
The **Compare** option mode lets you select the types of blocks that it can select adjacent to the original block. The default mode is ‘Block’

| Compare Type | Description |
| --- | --- |
| Block | All blocks of the same type including all blockstates. |
| BlockState | All blocks of the exact same blockstate as the target block. |
| Solid | Any block that you cannot pass through. For example stone, glass panes, etc. Not flowers, water, etc. |
| Any | All blocks directly adjacent including non solid blocks except for air. This causes it to ‘stop’ once it reaches air. |

The **Limit** option is a slider which can be configured to set how many blocks it should select in total. The magic select algorithm works by expanding outwards from the centre block to form an octahedron. Increasing the limit simply lets you select more blocks. The default limit is set to 100,000 blocks but can be set to any arbitrary limit.

The **Range** option is a slider which lets you set how far the algorithm should look for any adjacent blocks. This lets the tool ‘jump the gap’ between two blocks. The range simply represents how far it can look before cutting off. For example a bushy tree might have two or more blocks of air between it’s leaves and logs. This lets you select all the leaves that are on the tree regardless of the fact that there are air blocks between two branches with leaves.

The **Surface Only** option is a toggle which makes the tool only select the blocks on the surface of the selection or, equivalently, all blocks adjacent to air or the ‘outside’.
