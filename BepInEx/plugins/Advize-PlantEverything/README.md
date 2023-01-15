![](https://staticdelivery.nexusmods.com/mods/3667/images/1042/1042-1618905952-462602285.png)

| [Description](#description) | [Features](#features) | [Installing](#installing) | [Compatibility](#compatibility) | [Contact Author](#contact-author) | [Other Info](#config-and-other-info) | [Config](#config) | [Source](#source) | [Changelog](#changelog) | [Screenshots](#screenshots) |
|---|---|---|---|---|---|---|---|---|---|

## Description
A rewrite of the Planting Plus mod by bkeyes93. Plant Everything allows you to plant and harvest gathered and pickable resources found throughout the world, such as berry bushes, mushrooms, thistle, dandelion, as well as previously unavailable saplings and decorative flora. Expand your farming repertoire with berry bushes, flowers, and mushrooms whose resources will respawn over time. While you're at it, spruce up your settlement with some small trees, bushes, and even wall-mountable vines!

In addition to the added plantable resources, a wide range of configurable options allows you to tweak the mod/game's farming related aspects in favor of aesthetics, game balance, or your personal preference. By default the configuration file is centered around game balance and respects all of the vanilla game settings. This includes its obscenely long respawn time for pickables, which can range as high as several hours of real time spent in the game. I strongly encourage you to lower your pickable respawn times for a more enjoyable experience.

`If you need to remove a spawner, aim at it and press your deconstruct key (middle click by default) with your cultivator in your hand the way you would destroy a building piece with your hammer equipped.`

## Features

This mod adds a wide range of features, some of which are not well known (or even forgotten), but all of which are toggleable. I'll do my best to provide as comprehensive a list as I can, and will update it over time. The following is a short list of some of the most significant features.

**Adds 24 recipes to the cultivator**
- which are unlocked by obtaining at least 1 of each of the recipe's required materials, as you would any other recipe in the game.

**Provides the option to grow crops in any biome.**
- Also allows you to remove other restrictions such as whether crops need cultivated ground, open sky, space to grow, or even whether you can plant your trees indoors.

**Displays growth time remaining**
- on crops, pickables, and saplings as hover text. See [UI] section of config for related settings and toggling it on/off.

**Personalize numerous game settings**
- relating to crops, saplings, pickables, and seeds. These settings include growth times, costs, yields, grow radius, and size scaling.

**Remove pesky respawning debris**
- such as sticks, stones, and flint using your cultivator (see bold text at end of 'Description' section). Also allows you to set resource cost and return of debris.

**Plant some flora indoors.**
- When [Difficulty]PlaceAnywhere is enabled, the following changes take effect: Saplings, small trees, and bushes can be placed indoors. Saplings can grow into trees indoors, and sapling grow radius is ignored. Bushes and saplings/trees placed while PlaceAnywhere is enabled will defy gravity (to prevent them from falling through floors). Even if PlaceAnywhere is later disabled, the pieces will continue to float until the world is loaded without the mod present.

**Synchronizes configuration settings in multiplayer using ServerSync.**
- Mod configurations will be synchronized between connected clients who are using the mod. If [General] LockConfiguration is set to true, only server admins will be able to modify configuration settings. However, settings falling under the [General] category of the config file will not be synchronized (with the exception of AlternateIcons, and EnableMiscFlora). Though ServerSync will sync configs between connected clients, a client's locally stored configuration file will not be altered.

**Supports localized text**
- for the added plantable resources. The mod does offer localization support, but the mod has yet to be translated to other languages. Users can help to translate the mod to other languages by enabling "EnableLocalization" in the config, and then re-launching the game once. This will generate a .json file in the plugins directory alongside Advize_PlantEverything.dll named 'english_PlantEverything.json'. Using any text editor, edit the names and descriptions in the right column and resave the file as '{language}_PlantEverything.json'. Finally, change the language setting in the mod's config file to match {language} of your json file. For example, if you launch the game while "spanish_PlantEverything.json" is present alongside the .dll file AND the config language option is set to "spanish", it will load strings for names and decriptions from the Spanish json file.

If you are willing to translate to other languages, I would be more than happy to offer them as optional downloads with the mod.

**Miscellaneous Features:**

- Custom meshes for flowers and mushrooms to indicate picked status. Picked models will not display on clients without the mod or who have ShowPickableSpawners set to false, but the spawner will remain and will display again once matured.
- Works in multiplayer environments even for users without the mod. Unmodded clients will be able to see and interact with all of the added resources that you plant. However, some settings may only work if the mod is installed on the server as well.
- Snap points can be seamlessly toggled on/off for vines to help with placement using Configuration Manager.
- Many pickable resources can be disabled by setting their resource cost to 0. Eligible resources will mention it in the description of their respective config settings.

The following recipes have been added to the cultivator:

Raspberry Bush, Blueberry Bush, Cloudberry Bush\
Mushrooms, Yellow Mushrooms, Blue Mushrooms\
Thistle, Dandelion\
Ancient Sapling, Ygga Sapling

With EnableMiscFlora enabled in config:

Small Beech Tree, Small Fir Tree, Small Dead Fir Tree\
Small Plains Bush, Small Fruitless Bush (2 tints), Small Shrub (2 tints)\
Vines, Glowing Mushroom\
Branch, Stone, Flint

## Installing

### Manual Install

Extract the Advize_PlantEverything.dll file into the BepInEx/plugins folder.
Directory structure should look like this:
```
BepInEx ->
    plugins ->
        Advize_PlantEverything.dll
```
#### In multiplayer environments:
It is strongly recommended you install the mod on the server, though it is not required for all settings and features. Other connected clients are encouraged to use the mod as well, but that too is not a requirement.
## Compatibility
Here you'll find info about known mod conflicts and possible solutions.

### Valheim+:
Though compatible out of the box, Valheim+ does have some config settings that overlap with settings from Plant Everything. Only if and when these specific features are desired from one mod or the other will you have to decide which mod's feature you'd prefer to use. Doing so is as simple as toggling something on/off in either of the mod's config files.

### FarmGrid:
The FarmGrid config file requires a bit of tweaking in order to support the resources added in this mod. See following guide.
```
Open your FarmGrid config file in a text editor or in game using the Configuration Manager mod. Find the line beginning with

plantObjectMasks =

Change it to:

plantObjectMasks = piece, piece_nonsolid, item

Find the line beginning with

﻿customPlants = 

Change it to:

customPlants = RaspberryBush(Clone): 0.5, RaspberryBush: 0.5, BlueberryBush(Clone): 0.5, BlueberryBush: 0.5, Pickable_Mushroom(Clone): 0.5, Pickable_Mushroom: 0.5, Pickable_Mushroom_yellow(Clone): 0.5, Pickable_Mushroom_yellow: 0.5, Pickable_Mushroom_blue(Clone): 0.5, Pickable_Mushroom_blue: 0.5, CloudberryBush: 0.5, CloudberryBush(Clone): 0.5, Pickable_Thistle(Clone): 0.5, Pickable_Thistle: 0.5, Pickable_Dandelion(Clone): 0.5, Pickable_Dandelion: 0.5


Tweak grid spacing as you see fit.

Additionally, you can cause the other pieces added by this mod to align to the grid. In order to support all pieces added by this mod, I believe you would need to add 'Default_small' to plantObjectMasks. As for the customPlants field, the following are the names of the remaining prefabs. Adjust grid spacing as necessary.

Beech_small1(Clone): 0.5, Beech_small1: 0.5, FirTree_small(Clone): 0.5, FirTree_small: 0.5, FirTree_small_dead(Clone): 0.5, FirTree_small_dead: 0.5, Bush01(Clone): 0.5, Bush01: 0.5, Bush01_heath(Clone): 0.5, Bush01_heath: 0.5, Bush02_en(Clone): 0.5, Bush02_en: 0.5,  shrub_2(Clone): 0.5, shrub_2: 0.5, shrub_2_heath(Clone): 0.5, shrub_2_heath: 0.5, vines(Clone): 0.5, vines: 0.5
```
## Contact Author
You can reach me on the Nexus to provide bug reports or feedback https://www.nexusmods.com/valheim/mods/1042

For further mod or mod dev support, I can be found at the following Discord server:

[![](https://i.imgur.com/GfpDTSu.png)](https://discord.gg/vP9jsGrCyu)
[![](https://i.imgur.com/HZMpQip.png)](https://discord.gg/89bBsvK5KC)

## Config and Other Info:
Mod is highly configurable, a config file will be generated after first loading the mod and can be found in ﻿BepInEx/config/advize.PlantEverything.cfg

The config can be edited out of game with a text editor, or modified in game using the Configuration Manager mod.

## Config
### Default Config File:
```
Configuration file has become so long that the readme size limit of thunderstore.io has been reached. Please see Nexus mod page for the default configuration.
```
## Source
Github Repo: [Advize_ValheimMods](https://github.com/AdvizeGH/Advize_ValheimMods)

## Changelog
### 1.13.0
- Trees & Seeds update!
- Added ygga saplings.
- Gave ancient saplings a unique appearance.
- Added [Seeds] config options TreeDropMin & TreeDropMax.
- Corrected [Seeds] setting descriptions.
- Fixed benign NRE when leaving game while viewing plant growth progress.

### 1.12.0
- Updated for Mistlands v0.212.7.
- [Crops] configuration options added for, and now apply to, jotun puffs and magecap.
- Added small ygga tree recipe to the cultivator.
- Added 2 new [Crops] settings, CropsRequireSunlight & CropsRequireGrowthSpace.
	- Greenhouses?

### 1.11.7
- Updated ServerSync to v1.13 for Valheim 0.211.11.

### 1.11.6
- Updated ServerSync to v1.11 for Valheim 0.211.7 crossplay support.

### 1.11.5
- Fixed null reference error that occurs when an ancient sapling matures into a tree while PlaceAnywhere is enabled.

### 1.11.4
- Fixed localized text for BlueberryBush build description.

### 1.11.3
- Fixed [Crops]OnionReturn using value set in OnionCost.
- Ensured plant growth times are set to a minimum 10 seconds.
- [Difficulty]ResourcesSpawnEmpty now applies to all pickables.
	- Applies to berry bushes, mushrooms, flowers, and debris.
- Updated to ServerSync v1.6.

### 1.11.2
- Fixed collision on dandelions.

### 1.11.1
- Added new icons for all added pieces in the cultivator menu to match vanilla art style.
- Removed [General]AlternateIcons config option.
- Added 3 new buildable pieces: Branch, Stone, and Flint debris.
- New config category 'Debris', including 6 new settings.

### 1.11.0
- At long last, with 3D modeling assistance from Bento, custom meshes for picked flowers and mushrooms are finally here.
	- Added custom meshes for picked flowers and mushrooms.
- [General]AlwaysShowSpawners has been removed in place of ShowPickableSpawners (defaults to true) which can be toggled off to restore vanilla behaviour.
- Added toggleable snap points for vines.
- Updated some config descriptions.
- Misc improvements.

### 1.10.1
- Toggling [Crops]EnableCropOverrides off while in game now correctly un-applies all [Crops] settings.

### 1.10.0
- Removed custom AncientSeeds item.
	- Planting an Ancient Sapling now requires a vanilla AncientSeed.
- Added Cost and Return config settings for individual crops.
- Added extra null reference prevention.
- Compiled against BepInEx 5.4.19.0.
- Moved [Difficulty]EnableCropOverrides to [Crops].
- Added EnableSeedOverrides to [Seeds]
	- Must be enabled for [Seeds] config options to be applied.

### 1.9.2
- Fixed incompatibility with Better Creative, with fix submitted by its author, Heinermann.

### 1.9.1
- New config category: UI.
	- Moved EnablePickableTimers to UI category.
	- Added [UI]EnablePlantTimers and [UI]GrowthAsPercentage.
- Growth time remaining can be seen as hover text on crops, saplings, and pickables, and optionally may be displayed as a percentage.

### 1.9.0
- Adopted ServerSync in place of Authoritative Config.
- Changes to configuration options while in game, through BepInEx Configuration Manager or synchronization with connected clients, will immediately take effect without a world reload.

### 1.8.6
- Berry bushes, mushrooms, and flowers can now individually have their recipes removed from the cultivator by setting their respective resource cost to 0 in the configuration file.

### 1.8.5
- Added extra null reference error prevention.
- Compiled against BepInEx 5.4.1601 and Valheim 0.205.5.

### 1.8.4
- Fixed bug where some trees would only drop one or two items from their drop table, even when [Seeds] oneOfEach was set to true.

### 1.8.3
- Added [Seeds] configuration options category with 4 new settings.
	- These settings normalize the amount of seeds that drop from the various tree types, and allow the user to define seed drop rates and amounts.

### 1.8.2
- Fixed ancient trees having no placement cost.

### 1.8.1
- Updated for Valheim v 0.202.14 (Hearth & Home).
- Removed config options [Saplings] BirchCost, OakCost, AncientCost.
- Removed custom Birch/Oak seeds and saplings (included now in base game).

### 1.8.0
- Added [General] EnablePickableTimers config option (defaults to true).
	- When enabled, pickables will display growth time remaining in hover text.
- Added large glowing mushroom recipe to cultivator.

### 1.7.1
- Cultivator can now remove branch, stone, and flint spawners using the deconstruct key.

### 1.7.0
- Redesigned the PlaceAnywhere config setting.
- When PlaceAnywhere is enabled, the following changes take effect:
    - Saplings, small trees, and bushes can be placed indoors.
    - Saplings can grow into trees indoors, and sapling grow radius is ignored.
    - Bushes and saplings/trees placed while PlaceAnywhere is enabled will defy gravity.
        - (to prevent them from falling through floors).
    - Even if PlaceAnywhere is later disabled, the pieces will continue to float until the world is loaded without the mod present.

### 1.6.3
- Rebuilt embedded asset bundle for Valheim 0.155.7.
- Fixed monster AI targeting non-player built flora after 0.155.7 AI changes.

### 1.6.2
- Added config option [Difficulty] : ResourcesSpawnEmpty (defaults to false).
    - When set to true, berry bushes will spawn without fruit when placed.

### 1.6.1
- EnforceBiomes config option now correctly applies to saplings.
- Fixed cultivator not animating when deconstructing vines.

### 1.6.0
- Cultivator can no longer remove all building pieces, only pickables and vines.
- Deconstruct now respects ward permissions.
- Added vfx and sfx when removing vines.
- Added config option, RecoverResources, to the [Difficulty] section of config (off by default).

### 1.5.2
- Updated for Valheim 0.154.1.
- Removed respawn time fix for pickable resources (fixed in base game).

### 1.5.1
- Added CropsRequireCultivation config option to [Crops] section (defaults to true).
- Fixed logic for PlaceAnywhere and RequireCultivation config options.

### 1.5.0
- Added new server authoritative config options to override grow radius, growth time, and scale of crops.
- Improved compatibility with other mods that cause game code to execute earlier than expected.

### 1.4.3
- Added chance for birch sapling to spawn autumn (plains) leaf variants.
- Added AlwaysShowSpawners config setting.
    - When enabled, spawners for mushrooms, thistle, and dandelion will remain visible after being picked.

### 1.4.2
- Birch trees found in the plains can now drop birch cones.
- Added config options for modifying growth time and min/max scale of beech, pine, and fir saplings.
- Centralized debug log source for tidier logging.

### 1.4.1
- Correctly adds cultivator recipes after receiving authoritative config.

### 1.4.0
- Added several new buildable pieces to the cultivator that can be enabled/disabled with new config option EnableMiscFlora (on by default).
- New config options to control grow radius of all tree saplings.
- Misc performance and code improvements.
	
### 1.3.3
- Fixed mod not initializing when connecting to a server that isn't hosting the mod.
- Fixed BirchCost, OakCost, and AncientCost config options not taking effect.
	
### 1.3.2
- Reverted to 1.2 method of adding cultivator recipes.
    - Hopefully this addresses the problem some people were experiencing with 1.3.
	
### 1.3.1
- Server configuration settings are now properly authoritative when enabled.
- Configuration options are now re-applied each time a world is loaded.
	
### 1.3.0
- Dropped MCE support.
    - Mod now uses Authoritative Config for server config synchronization.
	
### 1.2.2
- Fixed small beech and fir trees disappearing. Improved MCE support.
	
### 1.2.1
- Re-fixed functionality of EnforceBiomesVanilla config option.

### 1.2.0
- Added ability to plant small fir and beech trees.
- EnforceBiomesVanilla config option now allows barley and flax to grow outside of the plains.
- Added localization support (see mod description for details).

### 1.1.0
- New icons for berry bush pieces and placeholder icons for seed items.
- Corrected DandelionRespawnTime config description.
- Added EnforceBiomesVanilla option (default true).
- Optimizations: reduced mod footprint.

### 1.0.0
- Created Mod.

## Screenshots

Showcase of some the additional flora added in 1.4.0

![](https://staticdelivery.nexusmods.com/mods/3667/images/1042/1042-1619617919-1974000660.png)

Added cultivator recipes

![](https://staticdelivery.nexusmods.com/mods/3667/images/1042/1042-1653289490-629916861.png)

Custom meshes for picked flowers and mushrooms, with growth time displayed

![](https://staticdelivery.nexusmods.com/mods/3667/images/1042/1042-1650757157-636832645.png)