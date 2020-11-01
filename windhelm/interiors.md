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

### Vanilla Areas

For the large part, vanilla areas have not changed. However, the many edges of the vanilla areas now connect up to the wallwalk levels via stairs, and additional space have been made available for the marketplace square to its west. In these places we have opportunities for some new doors that lead to interiors.

The following are available interiors for vanilla areas.

* [Windhelm Bakery](/windhelm/interiors/vanilla/bakery.md)
* [Windhelm Blacksmith Quarters Attic](/windhelm/interiors/vanilla/blacksmithattic.md)

### Western District

Vanilla Windhelm's western walls has been repurposed into the High Road - a broad, wide, raised avenue that runs down the western center of the city. The Western District is the portion of the city that lies to the west of the High Road. To its east, it links directly to the market square underneath a bridge. To its north, it joins up at the end of the high road, ascending up to the mountain cave gate and the Northern district beyond.

The following are available interiors for the Western District.

* [Meadhall](/windhelm/interiors/western/meadhall.md)
* [Meadhall Apartments 01-03](/windhelm/interiors/western/apartments.md)
* [Western District Residences 01-04](/windhelm/interiors/western/residences.md)
* [Western District Temple](/windhelm/interiors/western/temple.md)
* [Windhelm Bathhouse](/windhelm/interiors/western/bathhouse.md)
* [Western Fort](/windhelm/interiors/western/fort.md)

### Windswept Manor

Located on the western edge of the city, Windswept Manor is a massive house built into the mountains. This house was first built by a thane who foolishly attempted to build a home larger than the Jarl's. Some told that he had business investments in the Snow Quarter back in the days, but when it was suddenly confiscated to house Dunmer migrants by an order from the Jarl, he found himself in total financial collapse. As a result, the bank forced him to sell off the manor to pay off his debts. The bank then subdivided the building into individual units to be resold to new owners.

As a result, though it looks like one house, the interior of Windswept Manor is more like a enclave community of its own. There are 7 subdivisions, a common kitchen, a common dining area with a nice fireplace, as well as a upper suite. The common areas, dubbed the "Windswept Manor Commons" can be considered a pub-like hangout, though managed to be more like a cafeteria. Residents of Windswept Manor normally live in their subdivided units, they would eat drink and hang out in the commons, and head out the city for work and trips.

The following are available interiors for Windswept Manor.

* [Windswept Manor Subdivisions 01-02](/windhelm/interiors/windswept/subdivision1-2.md)
* [Windswept Manor Subdivisions 03-07](/windhelm/interiors/windswept/subdivision3-7.md)
* [Windswept Manor Kitchen](/windhelm/interiors/windswept/kitchen.md)
* [Windswept Manor Suite](/windhelm/interiors/windswept/suite.md)

### Northern District

The Western District ends as the Bathhouse alleyway ascend up to join up with the High Road at the end of the Western District Temple. From that junction we could further ascend north into the Northern District.

The Northern District is located on the hills behind Valunstrad adjacent to the Palace of the Kings, which makes it the highest elevation of Windhelm City. Despite this, at ground level you don't actually get an expansive view of the city, due to the size of Valunstrad houses. The mood here is more of an intimate, tucked in community in one of the safest parts of the city.

The following are available interiors for the Northern District.

* [Mountain Caves](/windhelm/interiors/northern/mountaincaves.md)
* [Windhelm Bank](/windhelm/interiors/northern/bank.md)
* [Stonemasonry Guild](/windhelm/interiors/northern/stonemasonryguild.md)
* [Northern District Mansion and Servant Quarters](/windhelm/interiors/northern/mansion.md)
* [Northern District Residences 01-03](/windhelm/interiors/northern/residences.md)

### Windhelm Arena Entrance Area

One thing Epic Windhelm Expansion Base does is restores the Windhelm Arena structure. This structure is located to the east of Palace of the Kings, and accessible via cross paths at the prison building. Heading north from the prison building, you end up at the Windhelm Arena gate, where before you is the Arena gate itself, and behind you is a separate door that leads into the prison building.

The following are available interiors near the Windhelm Arena Entrance

* [Windhelm Arena Prison](/windhelm/interiors/arena/prison.md)
* [Windhelm Arena Worldspace](/windhelm/interiors/arena/arena.md)

### Northeast District

To the north of Gray Quarters is the Northeast District. Design-wise, this district serves two crucial purposes.

The first purpose is that Windhelm really lacks a gate to its north. The old Northern wall of Windhelm is right at the edge of the Gray Quarters, where it's 100% blocked off and there's no gate. Yet, what lies beyond the wall there is a perfectly flat piece of landscape that has basically nothing on it, and if you travel further down that direction, you can hike yourself on a much straighter path to Windhelm's closest ally of Winterhold. It made no sense that when the Empire is whole, they did not build the most obvious road between Windhelm and Winterhold, and no sense that after Ulfric started his rebellion, there wouldn't be a passage that goes straight to Winterhold whom sided with the Stormcloaks. Granted, at least with a few mods we can at least access that area from the docks, but relying on the dock gate for such an access is awkward and roundabout. There are also good lore-based arguments for that if there is a gate to the northeast, it should not be fully under the influence of the Gray Quarter, for back when that previous Jarl of Windhelm gave the Gray Quarter to the dunmer refugees, it would've only made sense if the neighborhood isn't part of the crucial defenses of the city. Thus, it made more sense to keep the Gray Quarters a cull-de-sac, and add a new Nord-majority district to the north of it where the gate could be placed.

The second is that, with the restoration of Windhelm Arena, there is now the need for some kind of inner city area that surrounds the Arena's northeast side. Otherwise, the Arena building itself would've been half inside Windhelm and half outside, which is awkward and strange. At the same time, the Windhelm Arena restoration brought about a new building for the prison, where instead of the previous L-shaped path, the new building has a "+" shaped cross path, allowing the eastern walls to be naturally accessed. This provided the perfect access point for that northeast district, which otherwise would've been very difficult to access without entirely rebuilding the northern side of Gray Quarters, the prison tower itself, or Palace of the Kings - all of which are almost-impossible tasks.

The resulting Northeast District can be accessed from two directions. Right at the prison's crossroad, you can turn onto the northern Gray Quarter walls and then right around onto a set of stairs that descend into the Northeast District. Or, alternatively, you can approach along the wallwalk from the east side, where you can find your way down to the district's ground levels through the Eastern Tower or the Gatehouse.

The theme for the Northeast District is basically a castle town. It will feel like it's surrounded by fortifications on all sides. The biggest, most notable structures include a tower, a gatehouse, and a castle. The pub is built right into the side of the castle. This district will be a bit isolated from the rest of the city, so I imagine its people may develop a more local sub-identity.

Of note here is the Eastern Tower, which is a circular tower that is part of the walls. The insides of this structure is fully accessible entirely from the exterior. It has 2 levels, a bottom level accessible via flights of stairs from the ground, a wall level, and a roof level. The levels are connected by spiraling stairs at the tower's center. Since this doesn't provide any interior doors, I will not be listing this structure in the below descriptions. This tower serves as an important access point between the ground level of the Northeast District and the eastern wallwalk. Lore-wise, you can say it's also an important tower to the city's northeast defenses.

The following are available interiors in the Northeast District.

* [Northeast District Pub](/windhelm/interiors/northeast/pub.md)
* [Northeast District Temple](/windhelm/interiors/northeast/temple.md)
* [Northeast District Temple Back](/windhelm/interiors/northeast/templeback.md)
* [Northeast District Residences 01-06](/windhelm/interiors/northeast/residences.md)
* [Northeast Warehouse](/windhelm/interiors/northeast/warehouse.md)
* [Northeast Gatehouse](/windhelm/interiors/northeast/gatehouse.md)
* [Northeast Castle](/windhelm/interiors/northeast/castle.md)
* [Northeast District Arena Back](/windhelm/interiors/northeast/arenaback.md)

### Wallwalk Level

Epic Windhelm Expansion Base makes the entirety of Windhelm's wallwalk level accessible. Along the wallwalks, there are two places as far as interiors are concerned, that isn't covered in the other sections.

The following are available interiors along the wallwalks.

* [Gray Quarter Wall Storerooms 01-02](/windhelm/interiors/wallwalk/grayquarterwallstorerooms.md)
* [Dockside Keep](/windhelm/interiors/wallwalk/docksidekeep.md)

