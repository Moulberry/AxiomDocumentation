# Stamp

The **Stamp Tool** is a [Blueprint](/editor/windows/blueprints.md) placement tool designed for placing multiple, randomly placed blueprints. Listed below are all [Tool Options](/editor/windows/tooloptions.md) for the **Stamp Tool**.

| Option                      | Description                                                                                                                                                                                                                                                                                                    |
| --------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Base Chance                 | The base chance is the final factor that determines placement. A base chance of 1 means it will always place the blueprint regarding the Min Spacing.                                                                                                                                                          |
| Min Spacing                 | The Minimum Spacing is the first factor that determines placement. A minimum spacing of 100% will result in the center of two blueprints being at least 100% of the blueprint's width apart.                                                                                                                                        |
| Place (Immediate)           | The immediate option places all blueprints immediately after releasing your brush stroke.                                                                                                                                                                                                                      |
| Place (Deferred)            | The deferred option allows you to place blueprints with multiple strokes. You can also manually offset and rotate the blueprints by using the [Gizmo](/editor/gizmos.md) located at the centre of the blueprint. New brush strokes will still apply the placement rules to previously placed blueprints.       |
| Random Yaw                  | Randomises the placement by rotating the blueprint in a random direction.                                                                                                                                                                                                                                      |
|Direction|Allows for rotating the affected area making it work on surfaces like walls or ceilings. Stamped objects have to be rotated manually before to account for the rotation.|
| Random X/Z Flip             | Randomises the placement by flipping the blueprint on the X and Z axis.                                                                                                                                                                                                                                        |
| Keep Existing               | When enabled, pre-existing blocks are not overridden.                                                                                                                                                                                                                                                          |
| Extend Foundation To Ground | If the bottom surface doesn't reach the ground, it will be duplicated down until it does.                                                                                                                                                                                                                      |
|Apply Gravity|After confirming the stamp, gravity will be 'applied' to the stamped objects.|

To load blueprints into the **Stamp Tool**, click the 'Add Blueprint' button. This will open your [Blueprint Browser](/editor/windows/blueprints.md#Blueprint_Browser) and click on the blueprint you'd like to add. To add multiple blueprints, you can either [Dock](/editor/windows/intro.md#Docking) the Blueprint Browser or use Shift + Click to avoid closing the window.

Blueprints have their own offset and chance. If the Base of your blueprint should be lower, you can edit it here. If you want less or more of a specific blueprint, you can also change that here. 

> Tip: you can also use the `Add Clipboard` button to quickly add your clipboard into the Stamp tool. 

## Video Demo

<iframe width="560" height="315" src="https://www.youtube.com/embed/Vf4urSRSkdw?si=BQsjUDd7ZMWs4oNV" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>