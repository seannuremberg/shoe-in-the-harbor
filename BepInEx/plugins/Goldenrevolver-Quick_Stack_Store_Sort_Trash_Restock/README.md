This mod attempts to be the one stop inventory management mod, combining various features into one cohesive package, while adding UI elements in addition to hotkeys as well as compatibility for Equipment and Quick Slot mods and localization.

This mod allows you to
- quickly stack your items into the current or nearby chests
- quickly restock the items you want (like food and ammo) from the current or nearby chests
- store all items into the current chest (complementary to the 'take all' button)
- sort the player inventory or the current chest by configurable criteria
- trash the currently held item or quick trash all previously trash flagged items in the player inventory

All these features are controlled by the option to favorite items or slots similar to games like Terraria.

There is also an extensive configuration system, that applies changes immediately. I highly recommend using an in-game Configuration Manager mod. I put a lot of effort into the descriptions of the config options, so if you have any questions, please read them.


## 1 - Favoriting

Favoriting is the main draw to combine all these features into one mod. By holding the Favoriting Key (default: Alt) or by using a new button, you can left click on an item to favorite it, or right click to favorite the slot it is in. This prevents most features of this mod from affecting it. No accidental quick stacking, sorting, storing or trashing. The favoriting state is shown with a custom colored border around the slot.

If you are actively using Favoriting, I recommend changing the config option 'OverrideHotkeyBarBehavior' in the 'General' section from 'NeverAffectHotkeyBar' to 'UseIndividualConfigOptions'.

![image](https://staticdelivery.nexusmods.com/mods/3667/images/2094/2094-1671547317-763384465.gif)


## 2.1 - Quick Stacking

You are probably already familiar with Quick Stacking. With one button press every non favorited item possible is put into the current or nearby chests that already contain this kind of item.

This implementation is based on the original [Quick Stack](https://www.nexusmods.com/valheim/mods/29) mod by [damnsneaker](https://www.nexusmods.com/valheim/users/52080261), who gave me permission. This mod has a smarter algorithm for accessing multiple containers than the original (even if it's not threaded like [Quicker Stack](https://www.nexusmods.com/valheim/mods/2049), but that prevents the issues that mod is currently facing).

I have also improved the checks for multiplayer, so you can't quick stack into chests that are currently open anymore. I have tested this a lot with a friend and situations that would delete items with other Quick Stack mods are no longer an issue.

![image](https://staticdelivery.nexusmods.com/mods/3667/images/2094/2094-1671547317-1324456515.gif)


## 2.2 - Restocking

Restocking is like Quick Stacking but in reverse. Quickly refill your arrows, your food or your one emergency stack of wood from the current or nearby chests. Restocking tops off the stack for each item you need (configurable).

![image](https://staticdelivery.nexusmods.com/mods/3667/images/2094/2094-1671547324-1045740202.gif)


## 3 - Store and Take All

This simply adds a 'Store All' button to the chest overlay which stores all non favorited items (it can even store and unequip equipped items if you configure it that way).

The logic of the 'Take All' button of chests (excluding tomb stones for compatibility) was also updated to work complementary and symmetrically to 'Store All'.


## 4 - Sorting

Sorting is based on the popular mod [InventorySorting](https://valheim.thunderstore.io/package/end360/InventorySorting/) by [end360](https://valheim.thunderstore.io/package/end360/) (with permission). It adds a 'sort inventory' and 'sort container' button that respects favoriting.

There are various different sort criteria to choose from:
- category (bunches up similar item types into categories like armor, weapons, etc)
- internal name
- translated name
- weight
- value

Ties are always broken by internal name, quality and stack size. You can also sort automatically when opening the inventory or a container.

![image](https://staticdelivery.nexusmods.com/mods/3667/images/2094/2094-1671547329-2082520177.gif)


## 5 - Trashing and Quick Trashing

Trashing is based on the amazing mod [Trash Items](https://www.nexusmods.com/valheim/mods/441) mod by [virtuaCode](https://www.nexusmods.com/valheim/users/111195808) (with permission). It adds a trash can UI element to the inventory screen to quickly trash any non favorited item.

This mod also adds Quick Trashing. By holding the Favoriting Key while you attempt to trash an item, you instead 'trash flag' this kind of item, similar to favoriting. When you click on the trash can without holding an item, an option to Quick Trash will appear allowing to trash all trash flagged items in your inventory.

If you are scared of trashing the one stack of an item that you usually consider trash flagged, consider putting it in a favorited slot.

![image](https://staticdelivery.nexusmods.com/mods/3667/images/2094/2094-1671547324-1808242402.gif)


## Compatibility

This mod has explicit compatibility for the following Equipment and Quick Slot mods

[ComfyQuickSlots](https://valheim.thunderstore.io/package/ComfyMods/ComfyQuickSlots/):
- My mod will respect both the equipment slots and the quick slots, and intentionally allows restocking the quick slots. 'Take All' will put items into the quick slots though, but that is intended functionality of ComfyQuickSlots.

[OdinsQOL](https://valheim.thunderstore.io/package/OdinPlus/OdinsQOL/) and [OdinsExtendedInventory](https://valheim.thunderstore.io/package/OdinPlus/OdinsExtendedInventory/):
- My mod will respect both the equipment slots and the quick slots, and intentionally allows restocking the quick slots. The buttons from my mod will move to not overlap if the separate equipment slot UI is enabled.

Aedenthorn's [Extended Player Inventory](https://www.nexusmods.com/valheim/mods/1356):
- This mod behaves identically to OdinsQOL and OdinsExtendedInventory, because they used Aeden's work as a base. If you use this, be sure to download this mod from Nexus and not from Thunderstore, as those are unofficial irregularly updated versions.

RandyKnapp's [Equipment and Quick Slots](https://valheim.thunderstore.io/package/RandyKnapp/EquipmentAndQuickSlots/):
- The slots from this mod are not actual inventory slot, so my mod cannot affect them in any way (which is good). Due to that, restocking the quick slots is not possible though. The buttons from my mod will move to not overlap with the equipment slot UI and while using a chest the small Quick Stack and Restock buttons are hidden.

[Better Archery](https://valheim.thunderstore.io/package/ishid4/BetterArchery/):
- My mod will respect the slots this mod reserves for the quiver feature (all 16 of them, even if it only uses 3), and intentionally allows restocking the arrows. Better Archery also changes how item adding, including 'Take All', works, so please be aware that that is not my doing.


## Incompatibility

As stated on their mod page, this mod, like every quick stacking mod, is incompatible with [MultiUserChest](https://valheim.thunderstore.io/package/MSchmoecker/MultiUserChest/) until they add a patch for my mod. This is in the very nature of this mod combination, so neither of our mods are bugged. I have contacted the author, so no need to message them or me about it.

Stacks of items with custom data, like from [Jewelcrafting](https://valheim.thunderstore.io/package/Smoothbrain/Jewelcrafting/), [Blacksmithing](https://valheim.thunderstore.io/package/Smoothbrain/Blacksmithing/) or [Cooking](https://valheim.thunderstore.io/package/Smoothbrain/Cooking/) by [Smoothbrain](https://valheim.thunderstore.io/package/Smoothbrain/), are excluded from getting merged by sorting or getting restocked, but otherwise behave normally.

This mod is incompatible with [Trash Items](https://valheim.thunderstore.io/package/virtuaCode/TrashItems/) because it is included in this mod.


## Localization

This mod includes a translation system for all ingame display texts (not the config menu). Currently English and Chinese are supported. For minor edits, you can override any display text in the config. If you are translating all display texts to your native language, please reach out to me, so I can add it to the mod as an automatic translation.

The Chinese translation was provided by [Tiomer](https://www.nexusmods.com/users/114839878).


Source code available on github: https://github.com/Goldenrevolver/QuickStackStore