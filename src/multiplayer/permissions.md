# Permissions

Permissions can be used to control what a player can and cannot do with Axiom. Below are all server permissions and their effects.

> Tip: Using a permissions plugin such as luckperms is essential for managing player permissions.

| Permission                      | Effect                                                                                                                                                          |
| ------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| axiom.*                         | Provides the player with all Axiom permissions.                                                                                                                 |
| axiom.allow_copying_other_plots | Used for plot-based servers when you don't want players copying other player's plots[^note1].                                                                           |
| axiom.can_import_blocks         | Determines whether the player can import [blueprints](/editor/windows/blueprints.md) or schematics. Generally used for building competitions where you don't want players to use pre-existing structures. |
| axiom.debug                     | Determines whether the player can run [Debug Commands](/advanced/commands.md#Multiplayer_Commands).                                                                                                                                                              |
| axiom.entity.*                  | Provides the player with all entity permissions.                                                                                                                                                               |
| axiom.entity.delete             | Determines whether players can delete [Display Entities](/builder/displayentities.md) and [Marker Entities](/builder/marker.md).                                                                                                                                                                |
| axiom.entity.manipulate         | Determines whether players can move and modify [Display Entities](/builder/displayentities.md) and [Marker Entities](/builder/marker.md).                                                                                                                                                               |
| axiom.entity.spawn              | Determines whether players can create [Display Entities](/builder/displayentities.md) and [Marker Entities](/builder/marker.md).                                                                                                                                                               |

## Notes

[^note1]: Axiom requires the [Plotsquared plugin](https://dev.bukkit.org/projects/plotsquared) for the permission to correctly function.