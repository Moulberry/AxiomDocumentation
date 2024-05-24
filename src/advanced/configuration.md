# Configuration

Axiom has its own dedicated configuration located in `.minecraft/config/axiom` containing 3 folders and 3 files.

The folders are used to store saved [Blueprints](editor/blueprints.md), [Heightmaps](editor/tools/heightmap/elevation.md) and [Tool Presets](editor/toolpresets.md) so even if the mod is removed, your assets are saved.

The files contain the more important information such as UI layout and enabled capabilities. Axiom uses a variant of JSON called HOCON (Human-Optimized Config Object Notation).

Below are the three files alongside their descriptions.

### `.axiominternal.hocon`

| Key                            | Description                                                           |
| ------------------------------ | --------------------------------------------------------------------- |
| completedTutorials             | Lists the tools that have shown their short tutorial.                 |
| customDowngradeSuggestions     | Lists the downgrades suggested by Axiom.                              |
| globalScale                    | A float representing the [Editor](editor/intro.md) UI Scale.         |
| lastTranslationCount           | A value determining the amount of translations.                       |
| openEditorWindowTypes          | A list of open windows in the editor.                                 |
| rootEditorPalette              | The default block palette for the editor mode.                        |
| savedCustomTheme               | Stores the currently active theme as a string.                        |
| showCloseWindowButton          | A boolean to toggle the "x" to close windows.                         |
| showNon90DegreeRotationWarning | A boolean to toggle the warning before applying non-90-degree angles. |
| showToolMaskOpenWarning        | A boolean to toggle the warning when using tool masks.                |
| shownIntroduction              | A boolean representing whether the introduction has been completed.   |

### `.axiom.hocon`

| Key             | Description                                                                                                                                                                       |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| blockAttributes | Contains the currently toggled block attributes.                                                                                                                                  |
| blueprint       | Stores the toggle to automatically refresh and a list of all used blueprint tags.                                                                                                 |
| capabilities    | Lists all abilities and their state. Also contains the `autoSwapToCreative` boolean that controls switching to creative when opening the [context menu](builder/contextmenu.md). |
| keybinds        | Stores in-game keybinds and settings for the Builder Mode and camera movement.                                                                                                    |
| toolKeybinds    | Stores all Editor keybinds for switching tools.                                                                                                                                   |
| rendering       | Stores booleans representing the toggles in the Toolbox found in the [Context Menu](builder/contextmenu.md).                                                                     |


### `imgui.ini`

This file is generally not meant to be modified, hence why it uses a different file format. However, if you're having an issue with a specific window that you can't recover, you can either edit or delete this file to fix the issue.