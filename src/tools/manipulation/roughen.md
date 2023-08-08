# Roughen

The **Roughen** tool is designed to create rugged or jagged edges in the terrain, essentially serving as the opposite of the smoothing tool. It works by "roughening" or making the terrain less smooth. It’s brush size can be configured to change the affected area.

The way it functions is by analysing how many faces (sides of the blocks) are currently exposed to the air and how many should be exposed after the roughening process. The amount of roughening applied to the terrain is determined by the "roughening ratio", which sets the proportion of change.

The 'Faces' parameter is a slider that ranges from 1 to 4. This determines how many sides (or faces) of a block will be exposed to air after the roughening process. If the value is set to 1, fewer faces will need to be exposed, leading to a more rugged look. On the other hand, if it's set to 4, less faces will need to be exposed, resulting in a highly irregular, rough appearance.

The 'Roughening Ratio' is a separate slider that you can also configure. This determines the intensity or amount of the roughening effect, or how much the terrain will be transformed. A high roughening ratio will cause a drastic change, making the terrain appear substantially more rugged. A lower ratio, on the other hand, will apply a more subtle roughening effect.
