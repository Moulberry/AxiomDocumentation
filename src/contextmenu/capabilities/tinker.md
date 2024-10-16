# Tinker

The **Tinker** capability has various features related to right-clicking with your fist on blocks. Tinker often can be used in place of the debug stick, being slighty faster compared to the debug stick's clunky interface but sometimes lacking the ability to change some non-visual properties.

Aiming at specific parts of a block can change the effect of the tinker. This lets you quickly change full blocks into stairs, stairs into slabs and vice versa. It also lets you easily adjust walls/fences to create states that Minecraft normally doesn’t allow.

Tinker interactions can be negated while the capability is toggled on by either having a non-empty hand or by holding down the sneak or ‘shift’ button.

| Block                             | Tinker Property Effect                                  |
| --------------------------------- | ------------------------------------------------------- |
| Walls                             | Cycle `axis` and cycle `none`, `low`, `tall`            |
| Fences                            | Cycle `axis`                                            |
| Chorus Plant                      | Cycle `axis` and toggle `up` / `down`                   |
| Iron Bars                         | Cycle `axis`                                            |
| Piston                            | Cycle `facing` and switches `Extended` / `Retracted`    |
| Furnace                           | Cycle `facing` and toggle `lit`                         |
| Carved Pumpkin/Jack o'Lantern     | Cycle `facing` and switches `Carved` / `Jack o'Lantern` |
| Barrel                            | Cycle `facing`                                          |
| Iron Trapdoor/Door                | Cycle `open`                                            |
| Brewing Stand                     | Cycle `bottles`                                         |
| Glazed Terracotta                 | Cycle `facing`                                          |
| Farmland                          | Cycle `moisture`                                        |
| Scaffolding                       | Toggle `bottom`                                         |
| Amethyst Cluster                  | Cycles `stages`                                         |
| Lectern                           | Toggles `book`                                          |
| Cave Vines                        | Toggles `berries`                                       |
| Bamboo Stalk                      | Toggles `leaves`                                        |
| Cauldron                          | Cycles `fluid level`                                    |
| Composter                         | Cycles `compost level`                                  |
| Beehive                           | Cycles `honey level`                                    |
| Cake                              | Cycles `bites`                                          |
| Lantern                           | Toggles `hanging`                                       |
| Fence Gate                        | Toggles `lowered` and cycles `facing`                   |
| Player Head                       | Cycles `rotation`                                       |
| Banner                            | Cycles `rotation`                                       |
| Attached Melon/Pumpkin Stem       | Cycles `facing`                                         |
| Rails                             | Cycles `rotation`                                       |
| Bell                              | Cycles `facing`                                         |
| Bamboo Block                      | Cycle `facing` and toggles `stripped`                   |
| Chest                             | Cycle facing                                            |
| End Portal Frame                  | Cycle `facing` and toggles `eye`                        |
| Observer                          | Cycle `facing` and toggle `powered`                     |
| Snow                              | Cycle layer                                             |
| Turtle Egg                        | Cycle eggs                                              |
| Suspicious Sand/Gravel            | Switch `Suspicious Sand` and `Suspicious Gravel`        |
| Grass Block / Dirt Path           | Switch `Grass Block` and `Dirt Path`                    |
| Azalea                            | Switch `flowering`                                      |
| Water / Lave                      | Cycle `level`                                           |
| Any block with 'age' property     | Cycles `age`                                            |
| Any block with 'lit' property     | Toggles `lit`                                           |
| Any block with 'powered' property | Toggles `powered`                                       |


Additionally:
- Right-clicking with Moss Block on cobblestone/stone converts the block into its mossy variant
- Right-clicking with Shears on removes the mossy variant 
- Right-clicking on a pot with a plant replaces the plant inside the pot
- Any block with a slab or stair variant can be tinkered