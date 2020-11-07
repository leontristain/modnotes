# Addon Mods

If you want to help me with this Windhelm expansion mod effort, one way you can contribute is by creating an addon mod.

Basically, you can start by using `EpicWindhelmBase.esp` as a master, and then develop your addon content as its own plugin. You would follow [these guidelines](/windhelm/guidelines.md) as you develop your addon content, so that your mod would not have incidental conflicts with any other addons.

## What Can You Create As An Addon Mod?

You can do a lot of things in an addon mod. For example...

### A Small Scale Addon Mod

If you are new to Skyrim mod creation and want a beginner project, or you just in general don't want to commit too much time and effort, then you may want to do a small scale addon. For example, perhaps you can take one of the unfinished interiors in the base mod and build out an interior for it. Then, perhaps you can create an NPC to live in that house, and give the NPC a daily schedule. That would be it. Nothing more than that.

With small scale addon mods, it's possible that your addon could be an ESL-ified `.esp` file. If this can be done then it is highly encouraged since it would save the user an esp slot.

### A Large Scale Addon Mod

If you are a modding expert and want to work on a much bigger-scale project, then you can use the base mod as a canvas and start building. Perhaps you would implement the interiors of several major buildings including some complicated ones like the Mountain Caves, add a dozen or so NPCs, give them custom dialogue and personalities, and involve them in new quests.

### An Addon Mod That Decorates The City

If you have an eye for aesthetics and want to beautify the city even more, then you could create an addon mod that decorates the new expansion areas and add clutter, much like what JK's Skyrim and Dawn of Skyrim does. As long as all your changes are purely additive, and you don't touch doors and Windhelm worldspace navmesh (other than with NAVCUT boxes), then your addon mod should remain free of compatibility concerns with other addons.

For decoration/clutter additions, it's possible that your addon could be an ESL-ified `.esp` file. If this can be done then it is highly encouraged since it would save the user an esp slot.

### An Addon Mod That Patches The City With Another Mod

Lastly, you can create addons that patch together the base mod with some other mod. For example, if someone else created a mod that adds a shop, you can create an addon mod that depends on both `EpicWindhelmBase.esp` and that other mod, disable the shop's exterior structures, and then relocate the interior to be inside one of my base mod buildings.

For patch addons, it's easily possible that your addon could be an ESL-ified `.esp` file. If this can be done then it is highly encouraged since it would save the user an esp slot.
