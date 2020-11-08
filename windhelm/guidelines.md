# Guidelines For Addon Authors

## In General

### Please follow the following naming convention.

The base mod will be called `EpicWindhelmBase.esp`. Your addon should be called `EpicWindhelm-YourModName.esp`. For example, if you turned the [Western District Temple](/windhelm/interiors/western/temple.md) into a building called the "Temple of Kyne", a good addon name might be `EpicWindhelm-TempleOfKyne.esp`.

If you want to prevent potential naming collisions with other addons, you can add a prefix before the `YourModName` part. For example, I tend to prefix my stuff with `ltr`, so I might call it `EpicWindhelm-ltrTempleOfKyne.esp`.

If your addon is a simple patch that relocates another mod's contents into one of the buildings provided by the base mod, then you can simply put `-Patch` at the end. For example, if my addon relocates [Astronomer's Loft](https://www.nexusmods.com/skyrimspecialedition/mods/38059) into the [Windhelm Blacksmith Quarters Attic](/windhelm/interiors/vanilla/blacksmithattic.md), a good name might be `EpicWindhelm-AstronomersLoft-Patch.esp`.

Having a common naming convention for addons improves user experience. It's nice when in MO2 or Vortex you can see all these related plugins looking the same and listed together.

### Please keep your content as modular and self-contained as possible

With a "base mod + addons" scheme where addons may depend on other addons, and addons are best created as ESPFEs because there can be many of them, it's a great idea to try to keep content modular and self-contained.

Here's an example. Suppose I want to create an addon for the [Bathhouse](/windhelm/interiors/western/bathhouse.md) and one of the [Meadhall Apartments](/windhelm/interiors/western/apartments.md). Suppose the bathhouse is owned and managed by NPCs Alice and Bob, but they hire a worker called Carter who lives in that apartment. Alice and Bob have daily schedules that mostly revolves around the bathhouse itself. Carter however lives at the apartment and only shows up at the bathhouse during certain hours.

I can do all this in a single addon, or I can split it into two separate addons:

 - A Bathouse addon, including Alice and Bob
 - An Apartment addon, including Carter

The good thing about two separate addons is that first, each addon would have less new records than the combined addon, which means if the combined addon is too big to be an ESPFE, the two separate addons might be small enough to be turned into ESPFEs.

Second, the bathhouse addon is now usable without the apartment addon contents. This means it's now possible to choose a different addon for the apartment, and _still_ have the same bathhouse. This is good flexibility to have. Without being coupled together with the apartment, the bathhouse is now easier to depend on by other addons, and the user has more choices.

### Please remember to add signs to the Windhelm Worldspace to match your content

This is just a reminder for something that I think is easy to forget.

If you turned one of the buildings into a shop, you should also add a sign for it in the Windhelm worldspace just outside the door. This should be the responsibility of the addon because the sign should reflect what the addon turned the building into, which can easily differ from addon to addon.

The placement of the sign object should be purely additive, and shouldn't touch any navmesh or exterior doors, so it should be perfectly fine to do so.

## When Working On Interior Cells

### Please use an existing interior cell stub whenever possible

The base mod provides interior cell stubs for all the available but unimplemented buildings. These stub cells should have names starting with `aaaltr` and labeled descriptively. Please, as much as possible, avoid creating new cells in your addon plugin and simply build out the interior from one of the existing interior stub cells.

This is important because ESPFEs have a limitation where new cells created in an ESPFE would break should another plugin ever override a record within, so creating new cells in ESPFEs is generally not the best idea.

That said, sometimes creating new cells may be unavoidable. For example, suppose in my base mod I provided a single stub cell with multiple doors, but you want to have the doors go into different, separate cells, then you would need to create the additional cells. In that scenario, you might still be fine because the ESPFE limitation is not an immediate issue for as long as the addon you're creating won't have further patches that want to override something in its interior, and it would become a non-issue the moment it gets included in an addon pack.

Simply avoid creating new cells until it's necessary.

### ABSOLUTELY reuse existing interior doors

This one is absolutely important.

The base mod provides interior cell stubs for all the available but unimplemented buildings. The interior cell stub will contain one or more interior doors. Those interior doors are already linked to exterior doors in the Windhelm worldspace. Absolutely, no matter what you do, REFRAIN from replacing the interior door with a new one and relink to the exterior door. No matter what you do, make sure you leave that door link alone.

You are free to move that interior door to whichever location, including relocating it into a different interior cell (which can be done in xEdit). You are also free to modify that interior door however - change its ownership, lock difficulty, etc... You are free to re-finalize that door onto any interior navmesh triangle. However, never break the door link to the exterior door. Note that this also means never remove the door link and then recreate the same door link. Always leave that door link alone.

The reason for this is that, if you break the door link and relink the exterior door onto a different door, you create an override on the exterior door record. 

Now, the exterior door record has already been finalized onto an exterior navmesh triangle. If you create an override on the exterior door record, your override will "set in stone" that associated navmesh triangle, such that if I update the base mod to finalize the door onto a different triangle, your override would revert it back to the previous triangle.

This is bad in two ways. First, it makes it impossible for me to tweak navmesh and relocate exterior doors in later base mod updates without your addon to also update accordingly. Second, it makes it so that any base mod patch (say with JK's) that results in a different exterior triangle, would in turn require yet another separate patch for your addon.

So, again this is very important. Always _reuse_ the interior door I provided in the stub interior cells, never replace them with new doors, and never break that door link.

## When Working On Tamriel Worldspace Stuff

### Please try to keep all your changes purely additive

Please do not _move_ anything in the Tamriel worldspace. Instead, try to only add new objects.

If you absolutely need to, it's probably okay to disable some objects, but try not to disable anything important, and only when absolutely necessary.

The concern here is creating a conflicting situation with another addon which may want to do the same thing. If you want to move object X to location Y while another addon want to move object X to location Z, only one will win and the result may look visually jarring, so it's good to discourage this for all addons. With disables, the result can only mean the object disappears, so it's less of a problem, but purely additive changes is best.

If you feel a strong need to move or disable important objects, please reach out to me and we can have a chat. I might be able to do it as a base mod update.

### ONLY use NAVCUT boxes to manage navmesh.

It's very possible that you may want to add objects to the Windhelm worldspace that exists on navmesh but would block NPC passage. For example, if you want to add a new market stand, NPCs must be able to work the stand, but NPCs must not be allowed to try to walk through the stand and get stuck.

For cases like that, you can resolve the issue by using NAVCUT collision boxes. You can create collision boxes, set it to `L_NAVCUT` in the primitive tab, and then have it intersect the navmesh you want to cut. Once you do that, at any time the cell is loaded, the box will disable the intersected part of the navmesh at run time. This is a purely additive change, and it results in navmesh effects without an actual edit to the navmesh record.

It's important for you to not touch navmesh, since then I am free to update the navmesh in the base mod and patch it with other mods like JK's without your addon being affected.

### Overall, DO NOT TOUCH navmesh and exterior doors.

Navmesh records are messy and complicated records, and they make compatibility patches a nightmare. To make navmesh conflicts as easy and simple to resolve as possible, the base mod has to take full responsibility of all the navmesh. Exterior doors are directly coupled with navmesh because the navmesh record contain door references, and the door record contain navmesh triangle references. Thus both need to be fully controlled by the base mod.

As long as you don't touch exterior navmesh and doors, I can handle patching with mods like JK's in the base mod, and your addon should remain compatible without anything extra. There may still be a very small chance that perhaps some object you placed is not in a good location post-patch, but that's nothing that can't be addressed by simply choosing a better location that works for both worlds (see next guideline). If you touch navmesh, the need for more patches is inevitable.

### Please try to choose object placement locations with an eye for potential compatibility issues.

I will eventually create patches between the base mod and mods like JK's. When that happens, I expect 95% of Windhelm will remain the same from a functional perspective, but at the border between vanilla areas and expanded areas where conflicts are resolved, the resulting space may be slightly different, such that when objects are placed in some places, it might end up being a bad place post-patch.

To avoid a patch for your addon, it's best to choose a location that works both pre-patch and post-patch. This can be tricky, but the following may be good to keep in mind.

* Locations squarely within newly expanded areas should be perfectly safe, since other mods would not have modified those places. If you are working on clutter/decoration, you'll likely be working in these newly expanded areas so you're probably fine.
* For locations close enough to vanilla areas that other mods may touch and a patch may result in a different space, places "in the middle of the road" might be safer than places right next to a corner or a wall, since decorations are likely to line up against walls. If you're working close to or in vanilla areas, you're probably placing down things like markers, so perhaps "don't put them too close to edges" is a good idea?
