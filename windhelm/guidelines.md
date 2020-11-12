- [Guidelines For Addon Authors](#guidelines-for-addon-authors)
  - [In General](#in-general)
    - [Please follow the following naming convention.](#please-follow-the-following-naming-convention)
    - [Please keep your content as modular and self-contained as possible](#please-keep-your-content-as-modular-and-self-contained-as-possible)
      - [Example 1](#example-1)
      - [Example 2](#example-2)
    - [Please remember to add signs etc to the Windhelm Worldspace with your addon](#please-remember-to-add-signs-etc-to-the-windhelm-worldspace-with-your-addon)
  - [When Working On Interior Cells](#when-working-on-interior-cells)
    - [Please use an existing interior cell stub whenever possible](#please-use-an-existing-interior-cell-stub-whenever-possible)
    - [ALWAYS reuse existing interior doors, and never break any door links](#always-reuse-existing-interior-doors-and-never-break-any-door-links)
  - [When Working On Windhelm Worldspace Stuff](#when-working-on-windhelm-worldspace-stuff)
    - [Try to avoid large-scale visual changes to vanilla areas](#try-to-avoid-large-scale-visual-changes-to-vanilla-areas)
    - [Please try to keep all your changes purely additive](#please-try-to-keep-all-your-changes-purely-additive)
    - [Only use NAVCUT boxes to manage navmesh.](#only-use-navcut-boxes-to-manage-navmesh)
    - [Overall, DO NOT TOUCH navmesh and exterior doors.](#overall-do-not-touch-navmesh-and-exterior-doors)

# Guidelines For Addon Authors

## In General

### Please follow the following naming convention.

The base mod will be called `EpicWindhelmBase.esp`. Your addon should be called `EpicWindhelm-YourModName.esp`. For example, if you turned the [Western District Temple](/windhelm/details/western/temple.md) into a building called the "Temple of Kyne", a good addon name might be `EpicWindhelm-TempleOfKyne.esp`.

If you want to prevent potential naming collisions with other addons, you can add a prefix before the `YourModName` part. For example, I tend to prefix my stuff with `ltr`, so I might call it `EpicWindhelm-ltrTempleOfKyne.esp`.

If your addon is a simple patch that relocates another mod's contents into one of the buildings provided by the base mod, then you can simply put `-Patch` at the end, to both follow the convention of an addon, and to signal that it's a patch. For example, if my addon relocates [Astronomer's Loft](https://www.nexusmods.com/skyrimspecialedition/mods/38059) into the [Windhelm Blacksmith Quarters Attic](/windhelm/details/vanilla/blacksmithattic.md), a good name might be `EpicWindhelm-AstronomersLoft-Patch.esp`.

Having a common naming convention for addons improves user experience. It's nice when in MO2 or Vortex you can see all these related plugins looking the same and listed together.

### Please keep your content as modular and self-contained as possible

With a "base mod + addons" scheme where addons may depend on other addons, and addons are best created as ESPFEs because there can be many of them, it's a great idea to try to keep content modular and self-contained. It's hard to define exactly what modular and self-contained means, since they're kind of like general philosophies. I will provide two examples instead:

#### Example 1

Suppose I want to create an addon for the [Bathhouse](/windhelm/details/western/bathhouse.md) and one of the [Meadhall Apartments](/windhelm/details/western/apartments.md). Suppose the bathhouse is owned and managed by NPCs Alice and Bob, but they hire a worker called Carter who lives in that apartment. Alice and Bob have daily schedules that mostly revolves around the bathhouse itself. Carter however lives at the apartment and only shows up at the bathhouse during certain hours.

I can do all this in a single addon, or I can split it into two separate addons:

 - A Bathouse addon, including Alice and Bob
 - An Apartment addon, including Carter

The good thing about two separate addons is that first, each addon would have less new records than the combined addon, which means if the combined addon is too big to be an ESPFE, the two separate addons might be small enough to be turned into ESPFEs.

Second, the bathhouse addon is now usable without the apartment addon contents. This means it's now possible to choose a different addon for the apartment, and _still_ have the same bathhouse. This is good flexibility to have. Without being coupled together with the apartment, the bathhouse is now easier to depend on by other addons, and the user has more choices.

#### Example 2

Suppose I want to "prettify" the Windhelm worldspace by adding clutter and decoration. Unless you're doing it for the whole city everywhere, a good way to go about it is probably to "own an area", where you fully handle that area, and never touch anything beyond that area.

For example, I might choose to decorate ONLY the Southern Wallwalk, in which case I will thoroughly decorate the Southern Wallwalk, but leave other adjacent areas, such as Western District's ground level, the Market square, etc... alone.

Now, if someone else also did the same thing where they completely decorated the Western District's ground level, but did not touch anything beyond this scope, then we end up with the best of worlds. Together, the two addons leave nothing undecorated but do not overlap into each other.

Granted, what constitutes "an area" is kind of vague, so in the end it's your call, but you get what I mean. Folks might want to coordinate if they feel it's necessary, in which case the ["Forum" section in the base mod's NexusMods page](https://www.nexusmods.com/skyrimspecialedition/mods/40745?tab=forum) might be a good place to have discussions and coordinate efforts.

### Please remember to add signs etc to the Windhelm Worldspace with your addon

Suppose you turned one of the buildings into a shop, don't forget to add a sign for it in the Windhelm worldspace next to the door. If you're implementing that bakery, you might want to consider adding smokestacks and having smoke come out of it. If you're implementing that bathhouse, perhaps a good idea is to add some pipes that comes out somewhere near the door to let out steam.

Anyway, this is just a reminder for stuff that might be easy to forget. That's all.

## When Working On Interior Cells

### Please use an existing interior cell stub whenever possible

This really only applies to mods with the potential to be ESPFE, though I want to suggest it's good practice to do anyway.

The base mod provides interior cell stubs for all the available but unimplemented buildings. These stub cells should have names starting with `aaaltr` and labeled descriptively. Please, as much as possible, avoid creating new cells in your addon plugin and simply build out the interior from one of the existing interior stub cells.

This is important because ESPFEs have a limitation where new cells created in an ESPFE would break should another plugin ever override a record within, so creating new cells in ESPFEs is generally not the best idea.

Sometimes creating new cells may be unavoidable. For example, suppose in my base mod I provided a single stub cell with multiple doors, but you want to have the doors go into different, separate cells, then you would need to create the additional cells. And of course, larger addons that involve new additional locations elsewhere will need to create those new additional cells.

In that scenario, you might still be fine because the ESPFE limitation is not an immediate issue for as long as the addon you're creating won't have further patches that want to override something in its interior, and it would become a non-issue the moment it gets included in an addon pack. As for larger addons, they might not be able to fit into an ESPFE to begin with, in which case this would be a non-issue.

In general though, unless there is good reason to go otherwise, why not just reuse the stub?

### ALWAYS reuse existing interior doors, and never break any door links

This one is absolutely important. I would call this not a guideline, but a RULE.

The base mod provides interior cell stubs for all the available but unimplemented buildings. The interior cell stub will contain one or more interior doors. Those interior doors are already linked to exterior doors in the Windhelm worldspace. Absolutely, no matter what you do, REFRAIN from replacing the interior door with a new one and relink to the exterior door. No matter what you do, make sure you leave that door link alone.

You are free to move that interior door to whichever location, including relocating it into a different interior cell (which can be done in xEdit). You are also free to modify that interior door however - change its ownership, lock difficulty, etc... You are free to re-finalize that door onto any interior navmesh triangle. However, never break the door link to the exterior door.

Note that this also means never remove the door link and then recreate the same door link. Always leave that door link alone. This can be the result of an accident or mistake, and the point here is that simply "relinking" is not a valid way to resolve after the fact. Instead, it's good practice to back up your plugin frequently so that such an accidental action can be undone. In the worst case scenario, the proper way to fix it is by removing the associated overrides in xEdit.

The reason for always reuse the same doors and never touching door links is that, if you break the door link and relink the exterior door onto a different door, you create an override on the exterior door record. 

Now, the exterior door record has already been finalized onto an exterior navmesh triangle. If you create an override on the exterior door record, your override will "set in stone" that associated navmesh triangle, such that if I update the base mod to finalize the door onto a different triangle, your override would revert it back to the previous triangle.

This is bad in two ways. First, it makes it impossible for me to tweak navmesh and relocate exterior doors in later base mod updates without your addon to also update accordingly. Second, it makes it so that any base mod patch (say with JK's) that results in a different exterior triangle, would in turn require yet another separate patch for your addon.

So, again this is very important. Always _reuse_ the interior door I provided in the stub interior cells, never replace them with new doors, and never break that door link.

## When Working On Windhelm Worldspace Stuff

### Try to avoid large-scale visual changes to vanilla areas

The overall spirit of this Windhelm expansion mod is to expand Windhelm and not overhaul vanilla areas. In the base mod, the vanilla proper is largely untouched. There are some exceptions made to a few places where vanilla areas transition to newly expanded areas. For background and details, please see [Notable Vanilla Edits](/windhelm/details/vanilla/vanillaedits.md). If you decide to decorate the Windhelm worldspace, please try to avoid vanilla areas.

This is important because it is the base mod's responsibility to patch with mods that decorates vanilla areas, such as JK's Skyrim and Dawn of Skyrim. If your addon end up being incompatible with such mods, the base mod cannot handle them and your addon will need patches, and that can get really complicated.

Of course, dropping a marker for NPC behavior, or adding some small object for a quest, is probably okay. Use your own judgment.

### Please try to keep all your changes purely additive

Please refrain from _moving_ anything in the Windhelm worldspace. Instead, try to only add new objects. If you absolutely need to, it's probably okay to disable some objects, but try not to disable anything important, and only when absolutely necessary.

The concern here is creating a conflicting situation with another addon which may want to do the same thing. If you want to move object X to location Y while another addon want to move object X to location Z, only one will win that object, and the result may look visually jarring, so it's good to discourage this for all addons. With disables, the result can only mean the object disappears, so it's less of a problem. In general though, purely additive changes are the best.

If you feel a strong need to move or disable important objects, please reach out to me and we can have a chat. Depending on what it is, I might be able to do it as a base mod update so you don't have to. At least we can brainstorm ideas for how to best handle this.

### Only use NAVCUT boxes to manage navmesh.

This is also absolutely important, where I would consider this not a guideline but a rule.

It's very possible that you may want to add objects to the Windhelm worldspace that exists on navmesh but would block NPC passage. For example, if you want to add a new market stand, NPCs must be able to work the stand, but NPCs must not be allowed to try to walk through the stand and get stuck.

For cases like that, you can resolve the issue by using NAVCUT boxes. You can create a primative, such as a collision box, then set it to `L_NAVCUT` in the primitive tab, and then have it intersect the navmesh you want to cut. Once you do that, at any time the cell is loaded, the box will disable the intersected part of the navmesh at run time. This is a purely additive change, and it results in navmesh effects without an actual edit to the navmesh record.

It's important for you to not touch navmesh records themselves, since then I am free to update the navmesh in the base mod and patch it with other mods like JK's without your addon being affected.

### Overall, DO NOT TOUCH navmesh and exterior doors.

This is related to the above, and therefore absolutely important, where I would consider this not a guideline but a rule.

Navmesh records are messy and complicated records, and they make compatibility patches a nightmare. To make navmesh conflicts as easy and simple to resolve as possible, the base mod has to take full responsibility of all the navmesh. Additionally, exterior doors are tightly coupled with navmesh because the navmesh record contain door references, and the door record contain navmesh triangle references. Thus both need to be fully controlled by the base mod.

As long as you don't touch exterior navmesh and doors, I can handle patching with mods like JK's in the base mod, and your addon should remain compatible without anything extra. There may still be a very small chance that perhaps some object you placed is not in a good location post-patch. For those issues, I would recommend choosing a location that is good for both the before-patch state and the after-patch state. You can update your addon with the new location after you find these issues. This way, we avoid the need for patches beyond the base mod patch.

If you absolutely feel the need to change navmesh for some reason, reach out to me and I can see if this can be done as a base mod update. At least we can brainstorm for potential other solutions.

Keep in mind that effects on the door, such as ownership, lock information, etc... are usually done to the _interior_ door. That one you can change ([as long as you reuse the same door record, and never break the door link](#always-reuse-existing-interior-doors-and-never-break-any-door-links)).
