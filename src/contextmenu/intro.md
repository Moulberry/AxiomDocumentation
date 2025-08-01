# Context Menu

Part of the Builder Mode, the Context Menu provides options which allow the user to modify how they view and interact with the world.

![Builder Context Menu](/img/AltMenuOverview.png)

### Hotbar Swapper

The Hotbar Swapper is a better version of the vanilla “Saved Hotbars” which are stored in the creative inventory and are loaded using keybinds. The Hotbar Swapper is in the center of the Context Menu and has infinite saveable hotbars. 

To save items to the hotbar swapper, use the scroll wheel while the context menu is open to select the hotbar you would like to save to.

Then close the context menu and fill your hotbar with the items you want. When you’re done, you can scroll to the next hotbar you would like to modify. Another way to modify hotbars would be to click on an item with left-click and drop it into another position with left-click.

> Note: Hotbars are not transferred between worlds but can be copied and renamed to your world in the 'minecraft/config/axiom/hotbars' folder 

Loading saved Hotbars is simple. Just use the scroll wheel in the context menu to select the hotbar you’d like to use. Then close the context menu and the blocks and items you previously saved should be loaded into your hotbar.

>Tip: Setting 'autoSwapToOtherHotbarWithItem=false' to true in [axiom.hocon](/advanced/configuration.md) will make your hotbar automatically swap to a hotbar already containing the item when middle-clicking.

### Capabilities
Capabilities allow you to change the way you place, destroy and modify blocks. When a capability is enabled, the button will be tinted green. Disabled capabilities are represented as greyed. 

Further information on the individual capabilities can be found [here](/contextmenu/capabilitiesintro.md).

### [Create Display Entity](displayentities.md)

### [Edit Block Attributes](blockattributes.md)

### Gamemode Switcher

Using these buttons can be slightly faster than messing around with F3+F4 or chat commands.

Pressing Left Alt while in another gamemode will put you into creative mode, this can be useful if you are in spectator mode and want to quickly switch to creative. This can be disabled in the [config](/advanced/configuration.md) as `autoSwapToCreative`.

### Flight Speed

The Flight Speed is represented as a vertical slider on the right side of the context menu. The current speed is represented as a percentage above the slider. 100% is normal flight speed and 200% would be two times as fast. The limit is 999%.

To change the flight speed, use left-click on the slider to select a specific speed. Dragging the slider and clicking the plus and minus symbols are other ways you can change the flight speed.

### Toolbox

The Toolbox is located under the flight speed slider in the context menu and contains useful settings for building. Listed below are all Toolbox settings alongside their description.

| Setting                    | Description                                                                                                                                                                                                                                                     |
| -------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Show marker entity gizmos  | Toggles visualisation of [Marker Entity](marker.md) [Gizmos](/editor/gizmos.md).                                                                                                                                                                                |
| Show display entity gizmos | Toggles visualisation of [Display Entitiy](displayentities.md) [Gizmos](/editor/gizmos.md).                                                                                                                                                                     |
| Show key hints             | Toggles the ability to view currently pressed keys at the bottom right corner of the screen. This can be useful for debugging or tutorials.                                                                                                                     |
| Infinite reach limit       | Sets the range for the [Infinite Reach capability](/contextmenu/capabilitiesintro.md). The slider ranges from 5 to 100 and is set to infinite by default.                                                                                                                  |
| Liquid opacity             | Sets the opacity of water. 100% normal opacity and 0% results in water being invisible.                                                                                                                                                                         |
| Minimum Brightness         | Sets the minimum brightness. 0% is default and 100% removes all shadows.                                                                                                                                                                                        |
| Type replace               | The Type Replace toggle affects the [Replace capability](/contextmenu/capabilitiesreplacemode.md). Replacing blocks with multiple variants such as stairs and slabs with another multi-variant block will change that block to the variant regardless of what block it is. |
| Flight direction           | Flight Direction changes the way you fly in creative mode. The vanilla flight mode is 'Horizontal' and the Axiom version is called 'Camera'. The camera mode allows you to fly in all directions using the direction of the camera.                             |
| Flight momentum            | The flight momentum affects how long it takes to change speeds while flying. A higher momentum means a longer delay until you reach full speed, resulting in a smoother flight.                                                                                 |

### Clear Hotbars

This button clears all **saved** hotbars.