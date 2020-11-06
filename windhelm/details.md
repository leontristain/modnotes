# Notes About Interior Spaces

## Recap

Epic Windhelm Expansion Base is my unfinished vision of a Windhelm expansion mod. At the time of writing, I can confidently say that the scope of the expansion exceeds any attempts that have been done before, and its layout and ideas are pretty nice-looking. At least, I hope I'm not the only one who thinks my pictures look really pretty.

However, right now it's just a shell. There are no interiors, no NPCs with daily schedules, and no quests or other gameplay content. This is where I hope the rest of the community could help out. If I just kept on working on this all by myself, getting all the gameplay content finished could take years, and at that timescale, it's easy for real life to happen and derail me at some point. Therefore if left entirely to my own abilities, I cannot guarantee even a good likelihood that this would ever finish.

There's also the problem that I'm not good at interior design, character design, or writing dialogue/quests. I imagine other talented folks in the community, who might be interested, would be able to do a much better job.

Therefore, I have spent my time and work on fleshing out Epic Windhelm Expansion Base as a _platform_ upon which contents can be built as addons. Basically, I will dictate and provide all the "infrastructure-y" things in the mod (basic city layout, building structures, navmesh, and door links), so that any interested mod author could pick an unfinished building, and build it out to their own vision, add NPCs, quests, etc... all as an addon mod. My "infrastructure-y" things would isolate addon mods from each other, minimize compatibility problems between addons, and let all addons coexist nicely.

If you're interested in helping in the effort and make an addon for it, this means you can keep the scope of your work as large or as small as you like. Maybe you only want to add 1 NPC to live in one of the tiny apartments with a simple daily schedule and nothing else - that's easily doable as an addon. Maybe you want to build out the entire Northeast Castle's interior with many NPCs capable of complex dialogue, relationships, and quest content - that's also easily doable as an addon. Hopefully, this flexibility and freedom lowers the barrier for interested folks to participate.

My "infrastructure-y" work should also isolate any further additional work in the Windhelm worldspace from addon content, for as long as addons only adds onto but don't fundamentally change the "infrastructure-y" stuff. This means there's also nothing preventing you from creating an addon that simply decorates an area of the city with clutter, if that's what you are interested in. The only requirements should be a few simple guidelines that shouldn't limit what you can do artistically. For details, please read the next section.

I also thought that keeping content modular within the expansion like this, would also allow players to pick and choose which addon they like or don't like, which might also be a bonus.

Anyway, if you're interested in contributing content as an addon, please read on.

## What Do You Mean? "Infrastructure-y" Stuff? (Guidelines for Addon Authors)

When it comes to multiple mods that try to change stuff in the same city, the biggest two sources of conflicts are navmesh conflicts and model clippings. The two problems are also highly coupled with each other, in that navmesh wants to follow the city layout, so they usually conflict together in the same way. Navmesh conflicts can also be very devious in that simple door triangles can be conflicts. If two doors opens to the same navmesh, they will conflict even if the doors themselves are from two entirely different buildings. All of the above problems will require conflict resolution.

Thus, to avoid conflict resolution, I gotta own the vision to all of the above. How the city is laid out - which buildings go where, what roads to have, where all the doors are, and the associated navmesh that's highly coupled with the layout - must be a single vision, and this is the purpose of Epic Windhelm Expansion Base. It dictates the city layout, the doors, and the navmesh. As an addon author, you shouldn't change these things. As long as you don't touch these things, your addon should be compatible with other addons without conflicts.

To this end, I hope what I've got in the Windhelm worldspace expanded areas are to your liking. If you don't like them, you can still improve them in a purely additive way, as long as you don't touch the navmesh, the doors, and the object layout in a way that doesn't play well with the existing navmesh. For object layout, you actually have a bit more freedom if you make use of NAVCUT boxes, since those allow you to disable navmesh without changing the navmesh record. This is extremely useful when you want to add clutter. So overall, you can always feel free to add more objects, disable existing objects, and rebuild parts of the city to look the way you like - just never touch navmesh, doors/door triangles, and make your changes play well with the existing navmesh, using NAVCUT as your only tool for dealing with navmesh.

The doors and door triangles are important because they're already linked to interior doors in "stub" cells. For each of my buildings, I have a stub cell. The stub cell contains the interior doors that link to exterior doors, an interior navmesh, a coc marker, and the bare minimum objects to make it traversable (usually just a floor and occasionally some stairs). This way, the door links have already happened, and the exterior navmesh triangle has already been set, where as long as you reuse the existing door links, any interior content would never touch the exterior navmesh record.

Initially, all the exterior doors will be locked so that the player can just assume any building that does not have content are simply closed and not operating.

The interior cell stubs are fully flexible. If you're working on an interior addon, you can easily start building from one of the stubbed cells from scratch. If you don't want to build from scratch, you can copy objects over from other cells. Or alternatively, you can ditch my stub cell and relocate the interior doors into another cell of your choice. This can be done using xEdit where you find the interior door records, and override the cell reference (copy/paste will work) with the cell you want those doors to be in.

Some of my interior stubs have multiple doors. For example, the gatehouse has 3 doors - 2 at the top that opens to the wallwalk, and 1 at the bottom that opens to ground level. Some of my buildings may also have doors that lead into multiple stubs. For example, the Northeast District Temple has a "front" cell and a "back" cell. This mostly reflects how I think the door groupings for interiors make the most sense. But since you can freely relocate doors to new cells, it means you can also totally combine interiors or separate interiors, by again, relocating the door into new cells that are either separated or combined together.

What's important is you never delete and relink the exterior door to a different door, because the moment you do that you will override the exterior navmesh, and that's bad. Always reuse the existing stub cell doors and relocate them around, never delete/abandon them and recreate the door link.

You'll likely also want to create NPCs, create AI schedules which involve placing markers at various places, and create all kinds of quest content. All that should be doable in a purely additive fashion whether in the interiors or Windhelm worldspace, so that should all be fine.

So, to recap:
* don't touch exterior navmesh
* don't touch exterior doors and their navmesh triangles
* always reuse interior doors from interior stubs - you can relocate them to other cells and re-finalize them onto other interior navmesh if you need to
* keep all your exterior changes purely additive, and only use NAVCUT boxes to deal with navmesh

As long as you do all that, your addons should be isolated from other people's addons, and we can have many addons on top of Epic Windhelm Expansion Base without need for patches.

And if you really, really don't like the "infrastructure-y" parts that I told you to not touch, let me know your concerns. I might be able to accommodate those changes into the next release of the base mod, if it makes sense and can be implemented in a backwards-compatible way.

## Existing Interiors

With that, I now give you a full listing of all the available existing interior stubs. If you want to make an addon by fleshing out an interior, this is the list that shows you what interiors are available, and which ones you can choose to work on.

For each one, I will give a brief description of what it is, how I thought about it, and what ideas I have for what it could be turned into. Of course you are free to take it into a totally different direction if you like. It's totally up to you.

* [Vanilla Areas](/windhelm/interiors/vanilla/main.md)
  * [Windhelm Bakery](/windhelm/interiors/vanilla/bakery.md)
  * [Windhelm Blacksmith Quarters Attic](/windhelm/interiors/vanilla/blacksmithattic.md)

* [Western District](/windhelm/interiors/western/main.md)
  * [Meadhall](/windhelm/interiors/western/meadhall.md)
  * [Meadhall Apartments 01-03](/windhelm/interiors/western/apartments.md)
  * [Western District Residences 01-04](/windhelm/interiors/western/residences.md)
  * [Western District Temple](/windhelm/interiors/western/temple.md)
  * [Windhelm Bathhouse](/windhelm/interiors/western/bathhouse.md)
  * [Western Fort](/windhelm/interiors/western/fort.md)

* [Windswept Manor](/windhelm/interiors/windswept/main.md)
  * [Windswept Manor Subdivisions 01-02](/windhelm/interiors/windswept/subdivision1-2.md)
  * [Windswept Manor Subdivisions 03-07](/windhelm/interiors/windswept/subdivision3-7.md)
  * [Windswept Manor Kitchen](/windhelm/interiors/windswept/kitchen.md)
  * [Windswept Manor Suite](/windhelm/interiors/windswept/suite.md)

* [Northern District](/windhelm/interiors/northern/main.md)
  * [Mountain Caves](/windhelm/interiors/northern/mountaincaves.md)
  * [Windhelm Bank](/windhelm/interiors/northern/bank.md)
  * [Stonemasonry Guild](/windhelm/interiors/northern/stonemasonryguild.md)
  * [Northern District Mansion and Servant Quarters](/windhelm/interiors/northern/mansion.md)
  * [Northern District Residences 01-03](/windhelm/interiors/northern/residences.md)

* [Windhelm Arena Entrance Area](/windhelm/interiors/arena/main.md)
  * [Windhelm Arena Prison](/windhelm/interiors/arena/prison.md)
  * [Windhelm Arena Worldspace](/windhelm/interiors/arena/arena.md)

* [Northeast District](/windhelm/interiors/northeast/main.md)
  * [Northeast District Pub](/windhelm/interiors/northeast/pub.md)
  * [Northeast District Temple](/windhelm/interiors/northeast/temple.md)
  * [Northeast District Temple Back](/windhelm/interiors/northeast/templeback.md)
  * [Northeast District Residences 01-06](/windhelm/interiors/northeast/residences.md)
  * [Northeast Warehouse](/windhelm/interiors/northeast/warehouse.md)
  * [Northeast Gatehouse](/windhelm/interiors/northeast/gatehouse.md)
  * [Northeast Castle](/windhelm/interiors/northeast/castle.md)
  * [Northeast District Arena Back](/windhelm/interiors/northeast/arenaback.md)

* [Wallwalk Level](/windhelm/interiors/wallwalk/main.md)
  * [Gray Quarter Wall Storerooms 01-02](/windhelm/interiors/wallwalk/grayquarterwallstorerooms.md)
  * [Dockside Keep](/windhelm/interiors/wallwalk/docksidekeep.md)
