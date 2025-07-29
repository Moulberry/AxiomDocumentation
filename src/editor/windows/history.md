# History

The History window provides an overview of the changes you've made to the world, as well as how many blocks each operation affected. It allows you to visualize the undo and redo actions, with the current history action highlighted with white text.

Setting `allowClickingHistoryInEditor=false` in [axiom.hocon](/advanced/configuration.md) to true makes it possible to interact with the history window directly. 
Clicking on a history entry with left click will revert all actions to that point. Right clicking the entry will point your camera towards the center of the edit.

History is deleted after leaving the world. However, the [commercial license](https://axiom.moulberry.com/commercial) allows for history to be saved permanently across multiple worlds.