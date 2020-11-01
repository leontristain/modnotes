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

#### Windswept Manor Subdivisions 01, 02

Subdivisions 01 and 02 are larger than the other subdivisions in that they take up the two "wings" of the building. Each has 2 doors - an upper and a lower one - that both leads into the common area. These could be residences or shops, maybe for larger families.

#### Windswept Manor Subdivisions 03, 04, 05, 06, 07

Subdivisions 03 to 07 are smaller subdivisions that only take up one floor, with some on the first level and some on the second. The bottom subdivisions may have doors that opens right into the cafeteria area, which makes it rather lively, and this could be a good thing or a bad thing, depending on the resident's personality.

#### Windswept Manor Kitchen

The food in Windswept Manor are made here at the Windswet Manor Kitchen, staffed by a chef and a help. Their pay come out of the Windswept Manor common fund. Outside of cooking, the help also has the job of sweeping the commons and keeping the common areas clean.

#### Windswept Manor Suite

The top half of Windswept Manor, dubbed the "Suite" is the most coveted subdivision. I see this space to be turned into the fanciest out of Windhelm player homes. Size-wise it's similar to Hjerim, but it's located at a really cool part of the city. The killer feature here is that it has private access to Windswept Manor's balcony, which is not only large and and spacious, but also offers a beautiful view of the city below, the beacon above, and the mountains in the distance.

Ideally, there should be some kind of backstory as to why someone have not purchased it yet. The player should be able to obtain it through some kind of small quest.

### Northern District

The Western District ends as the Bathhouse alleyway ascend up to join up with the High Road at the end of the Western District Temple. From that junction we could further ascend north into the Northern District.

The Northern District is located on the hills behind Valunstrad adjacent to the Palace of the Kings, which makes it the highest elevation of Windhelm City. Despite this, at ground level you don't actually get an expansive view of the city, due to the size of Valunstrad houses. The mood here is more of an intimate, tucked in community in one of the safest parts of the city.

The following are available interiors for the Northern District.

#### Mountain Caves

On the northwest edge of Windhelm where it touches the mountain, there exists a large, epic gate that leads into the mountain.

I see this as the entrance for a large, open, cavernous interior that is to Windhelm as the Glittering Caves is to Helm's Deep. Perhaps there could be more people and communities living within, or perhaps it could largely be just patroled by soldiers. These caves should be easily defended from Windhelm's side, yet also connect to various other parts of Tamriel so that it may be used as an escape route should Windhelm ever be helplessly besieged. Perhaps parts of the caves even lead further down into vile, dangerous places that few have explored (is Blackreach too much of a stretch?).

A known and well-utilitized path, however, is the cavern path that ascends and leads out slightly to the southwest, and there we have the door that leads out to Windhelm's Beacon, where you can then descend the steep stairs back down to the Western District. I imagined that should Windhelm be breached by enemies and its defenses entirely pushed into the mountain cave, the Beacon is still an area of easy defense due to the steep and narrow stairs, so defending soldiers could peek out from there to look at the situation below.

#### Windhelm Bank

Beyond the massive Mountain Gate, the first building we chance upon is the Windhelm Bank, which serves as the financial backbone of the city's functions. Those who wish to set up shop would loan money and then pay back with profits. The bank also oversees commercial real estate within the city, so if you want to buy a house, perhaps you come here.

#### Stonemasonry Guild

The massive wood-and-stone house next to the bank is the Stonemasonry Guild. That's my idea anyway, and again you don't have to go with what I'm thinking on any of these buildings - feel free to do whatever you like.

I thought of the stonemasonry guild when I saw that there are existing NPCs that simply walks over to various windows and hammer them as their day jobs. With all the new expanded space, there is a need to keep all the roads populated with pedestrians to keep things lively.

Windhelm is a city made of stone. Everything is stone, from the massive walls to the buildings to the brick steps on the ground. I imagine throughout its history, stonemasonry must be a very mature trade that goes back endless generations. Windhelm is also in no shortage of stonework, since many areas - vanilla areas in particular, are full of _broken_ stone that are just asking to be repaired.

So, what more lore-friendly way to keep the streets lively by creating a guild of stone workers who file out of their guildhouse in the morning, and then throughout the day, walk from place to place hammering at stone? Between them all, they could cover every part of the city and walk every path. Hence, the Stonemasonry guild. Maybe they could develop their own fraternity ways complete with enigmatic emblems and complex rituals and have some folks base conspiracy theories on them.

#### Northern District Mansion and Servants Quarters

This is a large private mansion built right next to Palace of the Kings. It has a mini-courtyard with a side door that leads to the Servant Quarters, which could be its own interior or simply a part of the same main interior.

I see the resident here to be an upper class Thane of a large and great house, with questionable personality - maybe the Erikur of Windhelm, except perhaps less disloyal but a lot more bigoted. Perhaps folks like Rolff Stone-Fist behave the way they do because of the way this prominent, influential Thane acts in public.

#### Northern District Residences 01, 02, 03

These are various house doors located around the outside of the Northern District Mansion. They all have their doors more or less directly into the bonfire square that the Northern District surrounds.

These house doors could be residences or shops, though some may look better as shops while others may look better as residences.

### Windhelm Arena Entrance

One thing Epic Windhelm Expansion Base does is restores the Windhelm Arena structure. This structure is located to the east of Palace of the Kings, and accessible via cross paths at the prison building. Heading north from the prison building, you end up at the Windhelm Arena gate, where before you is the Arena gate itself, and behind you is a separate door that leads into the prison building.

The following are available interiors near the Windhelm Arena Entrance

#### Windhelm Arena Prison

This is the door that leads into the prison building. I think most likely, this door should be used in an effort to restore the Windhelm Arena content. Perhaps it can be patched to integrate with Faction: Pit Fighter.

#### Windhelm Arena Worldspace

The main door of the arena will lead to the "WindhelmPitWorld" worldspace containing the interior of Windhelm Arena. Currently there are a bunch of NPC spectators here that greet and do nothing else. Again, most likely this should be used in an effort to restore the Windhelm Arena content. Again, perhaps it can be patched to integrate with Faction: Pit Fighter.

### Northeast District

To the north of Gray Quarters is the Northeast District. Design-wise, this district serves two crucial purposes.

The first purpose is that Windhelm really lacks a gate to its north. The old Northern wall of Windhelm is right at the edge of the Gray Quarters, where it's 100% blocked off and there's no gate. Yet, what lies beyond the wall there is a perfectly flat piece of landscape that has basically nothing on it, and if you travel further down that direction, you can hike yourself on a much straighter path to Windhelm's closest ally of Winterhold. It made no sense that when the Empire is whole, they did not build the most obvious road between Windhelm and Winterhold, and no sense that after Ulfric started his rebellion, there wouldn't be a passage that goes straight to Winterhold whom sided with the Stormcloaks. Granted, at least with a few mods we can at least access that area from the docks, but relying on the dock gate for such an access is awkward and roundabout. There are also good lore-based arguments for that if there is a gate to the northeast, it should not be fully under the influence of the Gray Quarter, for back when that previous Jarl of Windhelm gave the Gray Quarter to the dunmer refugees, it would've only made sense if the neighborhood isn't part of the crucial defenses of the city. Thus, it made more sense to keep the Gray Quarters a cull-de-sac, and add a new Nord-majority district to the north of it where the gate could be placed.

The second is that, with the restoration of Windhelm Arena, there is now the need for some kind of inner city area that surrounds the Arena's northeast side. Otherwise, the Arena building itself would've been half inside Windhelm and half outside, which is awkward and strange. At the same time, the Windhelm Arena restoration brought about a new building for the prison, where instead of the previous L-shaped path, the new building has a "+" shaped cross path, allowing the eastern walls to be naturally accessed. This provided the perfect access point for that northeast district, which otherwise would've been very difficult to access without entirely rebuilding the northern side of Gray Quarters, the prison tower itself, or Palace of the Kings - all of which are almost-impossible tasks.

The resulting Northeast District can be accessed from two directions. Right at the prison's crossroad, you can turn onto the northern Gray Quarter walls and then right around onto a set of stairs that descend into the Northeast District. Or, alternatively, you can approach along the wallwalk from the east side, where you can find your way down to the district's ground levels through the Eastern Tower or the Gatehouse.

The theme for the Northeast District is basically a castle town. It will feel like it's surrounded by fortifications on all sides. The biggest, most notable structures include a tower, a gatehouse, and a castle. The pub is built right into the side of the castle. This district will be a bit isolated from the rest of the city, so I imagine its people may develop a more local sub-identity.

Of note here is the Eastern Tower, which is a circular tower that is part of the walls. The insides of this structure is fully accessible entirely from the exterior. It has 2 levels, a bottom level accessible via flights of stairs from the ground, a wall level, and a roof level. The levels are connected by spiraling stairs at the tower's center. Since this doesn't provide any interior doors, I will not be listing this structure in the below descriptions. This tower serves as an important access point between the ground level of the Northeast District and the eastern wallwalk. Lore-wise, you can say it's also an important tower to the city's northeast defenses.

The following are available interiors in the Northeast District.

#### Northeast District Pub

The Northeast District Pub is the pub that serves this Northeast District. From the Northeast District, you're pretty far away from all other pubs - including the New Gnisis Cornerclub, so it makes sense for the district to also have its own pub. The pub is located at the end of a street, and is built right into the side of the Northeast Castle on the northern side of the district.

#### Northeast District Temple

The Northeast District also has its own temple, since other temples are rather far away and worship is a large part of Skyrim folks. The temple building itself is equal in size to the Temple of Talos, which makes it a bit bigger than the Western District Temple. However, it's also placed on lower elevation right against the side of a wall, which makes it feel less prominent. I also see only the front portion of the building to be used as the actual temple, while the backside of the building could be used for something else.

#### Northeast District Temple Back

This is the back side of the Northeast District Temple building, accessible via a side door right next to the stairs leading up the Eastern Tower. I think this interior could serve any purpose, such as a school, a library, a museum, or some kind of shop. Directly out the door is also a small square where some market stalls could be placed, which gives you a sense of the context.

#### Northeast District Residences 01, 02, 03, 04, 05, 06

The Northeast District is a modest, sleepy, no-frills district. It's not a place where fancy thanes would live. These 6 houses make up the living quarters of ordinary citizens of this district. Out of the houses, 01 and 02 are Brunwulf-style houses, while 03, 04, 05, and 06 are custom assets ("Stormcloak Cabin Resource by Kraeten). 01 and 02 line the western walls, while 03-06 form a block of residences within the middle of the district.

#### Northeast Warehouse

Built into the walls is another Stormcloak Cabin Resource building that I'm calling the Northeast Warehouse. Given its location, I am currently envisioning this to be a supply room or warehouse for the city guards. It could perhaps also be turned into a stable for horses, if it makes sense for horses to be able to go in and out of those normal rectangular doors.

#### Northeast Gatehouse

The Northeastern Gates out of the city is built with a massive Gatehouse that is at least as epic in splendor, if not even more so, than the main entrance to the city's south. The Gatehouse has a lower access door on its southern side, and two upper access doors at the wallwalk level that open in both directions along the wall. The wallwalk level also has convenient locations where defenders can watch the roads below.

While the gameplay constraints with such buildings means the interior is an entirely different cell where you can't actually look out from inside the gatehouse, or defend against invaders with arrow slits and murder holes, I think its mere existence can provide a realism boost. Also, I think it's totally possible to add a portcullis to the gate, which will happen in another iteration soon.

#### Northeast Castle

Traveling along the wall towards the northwest from the Gatehouse, and you arrive at the Northeast Castle, the structure that anchors this portion of the wall to the mountains to its North. This castle has two entrances, one at ground level close to the Northeast Warehouse, and one at the wall level on its west side. There's also nothing preventing you from adding more entrances between the pub and the castle, since the pub is built into the side of the castle.

The castle building itself is a Prison-style building, which means it has the exterior crossroads through its middle. Other than the directions that goes through the middle of the castle from the walls to the back garden of Palace of the Kings, there is a third direction that simply stops at a balcony for views, and a fourth direction that leads out to another balcony that can look outside the city. The structure here are placed such that enemies couldn't jump onto it from the mountain rocks nearby, thus maintaining defensive integrity.

The Prison-style building with the cross road going through its bottom may make interior design a bit of a challenge. Though it's also worth remembering that the majority of the building is actually below the crossroads, and the portion above the crossroads actually isn't that big. So perhaps put your palaces on ground level and have tower-like interiors that goes up and connect to the wall-level door. Worst case scenario, the interior doesn't have to match the exterior. As long as it's not blatantly different, I imagine few players would really notice or care.

#### Northeast District Arena Back

Going through the Northeast Castle, and you would arrive at a "back garden" located behind the Windhelm Arena and adjacent - basically connecting right into - the Palace of the Kings. Here we have a large statue of Talos at the top of some stairs. More importantly, there's a door that leads into the building behind the Arena.

I actually don't see this space to be an Arena-related space. After all, the Arena interior doesn't leave much room to add more viewing capacity from that direction, and the Arena quest and backstory probably doesn't make it easy to integrate such a location. What I can see, however, is for this location to be an additional "wing" of the Palace of the Kings. That makes this door essentially a back door of sorts to the Palace of the Kings.

Or you can just make it into a mini-temple, a mini-museum, or some shop isolated to a corner of the city few people visit. Up to you.

### Wallwalk Level

Epic Windhelm Expansion Base makes the entirety of Windhelm's wallwalk level accessible. Along the wallwalks, there are two places as far as interiors are concerned, that isn't covered in the other sections.

The following are available interiors along the wallwalks.

#### Gray Quarter Wall Storeroom 01, 02

Due to vanilla Windhelm shenanigans, there is actually a good chunk of unused space where the Eastern Wall is to the Gray Quarters. Basically, the Tamriel Worldspace's walls there are actually some distance further to the east than the Windhelm Worldspace's walls, which means vanilla Windhelm's gray quarters is actually slightly smaller than the space carved out for it. This means when I restored the exterior walls into the Windhelm Worldspace, I ended up with two layers of walls at two different elevations. I considered using this space to expand the Gray Quarters, but that turned out to be unfeasible due to the lack  of flexibility of the Gray Quarter building nifs, where after trying many different ideas I could not find one that work well. Thus, I kept the two layers of walls, and added two wall-level doors into the elevation difference.

There's a lot of wall-level space here so I imagine the city guard could put a lot of guard activity into this area. Perhaps the wide space makes this a great area for guards to train and hone their fighting skills - something like the Castle Dour Courtyard. These interiors could be guard sleeping quarters, or simply storerooms for supply. Perhaps one of them could be an armory.

#### Dockside Keep

The restored walls also restored the large flat roof of the Windhelm Docks building that houses the East Empire Company. Here, I added a keep, because it makes sense for the docks - and this part of the walls in general - to have some kind of defensive structure. It may also make sense if we put a lighthouse at the top of the keep (though that has yet to happen).

The keep structure has five doors. The lowest door is located right at the wall level on the building's east side. The main door is located a bit higher, along a set of stairs that goes up and then down around Calixto's House of Curiosities. This door is easily accessible from the road between Brunwulf Free-Winter's home and the Aretino Residence. Then, the fort has balconies on its eastern and southern side, as well as a roof that is also accessible via a door.

At the very beginning, I liked this space for a player home (in the style of The Rookery by Elianora), but now I think it makes much more sense for this to building to be used by the city guard. If the Gray Quarter Wall Storeroom area are not used for a guard training academy, then perhaps this building could serve as one, as well as your typical sleeping quarters for guards, etc...

This building does not take up all the space above the docs. The remaining space is enough for a small market or maybe something else.

