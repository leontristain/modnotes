# Overview

This is a document that lets you know what you get with this mod, complete with lots of pretty pictures.

For details of each area, please refer to [this document](/windhelm/details.md).

## The Big Picture

This mod is an City Expansion mod for Windhelm. The overall expansion looks like this:

![](/windhelm/pics/overview.png?raw=true "Raw Overview")

That's a lot bigger than vanilla Windhelm. Exactly how much bigger? Check it out.

![](/windhelm/pics/overview-vanillacomparison.png?raw=true "Expanded Windhelm Size vs Vanilla Windhelm Size")

In the expanded Windhelm, the wallwalks are now accessible. You can now climb up to the walls and dramatically gaze into the distance, perhaps with your HDT cloak fluttering in the wind.

More importantly, the wallwalks of Windhelm form into a very nice road network which you can see here:

![](/windhelm/pics/overview-wallwalknetwork.png?raw=true "Wallwalk Road Network")

The expansion expands Windhelm towards its west, north, and northeast directions, with the wallwalks nicely partitioning out 3 new districts. The expansion also restores the Windhelm Arena structure, expands the size of the market square by a bit, and adds a number of structures to the Gray Quarters wallwalk level. All of these are shown by the following pic.

![](/windhelm/pics/overview-newdistricts.png?raw=true "New Districts")

In the new districts, the mod adds a lot of new buildings, landmarks, points of interests, and doors to interiors, as shown by the following pic.

![](/windhelm/pics/overview-buildingsanddoors.png?raw=true "New Buildings, Landmarks, and Doors")

## Beautiful Visuals

I tried to make the expanded city look beautiful and epic, and I think I like what I ended up with. The following are a few screenshots hand-picked for their postcard-worthy prettiness. All photos are taken with Silent Horizons ENB for Cathedral Weathers, NobleSkyrim textures, Majestic Mountains, and Fluffy Snow.

First and foremost, we have this epically long Southern Wallwalk.

![](/windhelm/pics/southwall.png?raw=true "Southern Wallwalk")

In the Western District, we now have an epic temple structure currently dubbed the "Western District Temple". Here's a bird's eye view of it from the sky.

![](/windhelm/pics/westerntemple.png?raw=true "Western District Temple")

You also get some of these cozy alleyways, like the alleyway just outside the neighborhood bathhouse.

![](/windhelm/pics/bathhouse2.png?raw=true "Alleyway Outside Windhelm Bathhouse")

The top suite of the Windswept Manor building is intended to be a player home, and it's got a killer balcony view.

![](/windhelm/pics/windsweptsuitebalconyview.png?raw=true "View from Windswept Manor Balcony")

As evening falls and windows become noticeably lit, here's a photo of the Western District's High Road looking northward showing the city in all its majesty, note the Beacon of Windhelm on the cliffs above.

![](/windhelm/pics/highroadevening.png?raw=true "Evening High Road and Beacon of Windhelm")

At the northwest corner of the city there is a massive gate that leads into the mountains, perhaps leading to a Windhelm's equivalent for the Glittering Caves behind Helm's Deep.

![](/windhelm/pics/mountaingate.png?raw=true "View from Windswept Manor Balcony")

The mansion in the Northern District, complete with its stone arch entrance.

![](/windhelm/pics/mansion1.png?raw=true "Northern District Mansion")

A courtyard just inside the gates, located in the Northeast District, with stairs on the far side that ascends up into the Eastern Tower.

![](/windhelm/pics/northeasttempleback.png?raw=true "Northern District Mansion")

The Northeast Gatehouse in all its glory.

![](/windhelm/pics/northeastgatehouse.png?raw=true "Northern District Mansion")

The Northeast Castle with a pub built into its side.

![](/windhelm/pics/northeastcastle1.png?raw=true "Northern District Mansion")

Looking south from the Northeast Castle's railing, you first see the roofs of the Northeast District Residences, followed by the Northeast District Temple, and then the Dockside Keep in the distance on the other side of Gray Quarters.

![](/windhelm/pics/northeastcastlerailingview.png?raw=true "Northeast Castle Railing View")

On the backside of Windhelm Arena and Palace of the Kings, we have a courtyard leading to a massive statue of Talos.

![](/windhelm/pics/northeastarenabackgarden.png?raw=true "Back Courtyard of Palace of the Kings")

Looking across Northeast District after the falling of fresh snow.

![](/windhelm/pics/northeastdistrictroadview.png?raw=true "Northeast District, Fresh Snow")

View of Palace of the Kings from the stairs that leads up to the arena.

![](/windhelm/pics/northeaststairpalaceview.png?raw=true "Palace of the Kings view from arena stairs")

## Quality and Vanilla Fixups

Vanilla Windhelm has a lot of things that were basically broken, such as:

* Lots of landscapes disabled or missing in cells too close to be covered by LODs.
* A complete lack of standins for structures outside the city that are too close to be covered by LODs, such as the Windhelm Bridge and nearby farmhouses.
* Occlusion boxes for certain buildings set too high, resulting in objects popping in and out of view when you walk close to the building's roof in certain angles.
* Lots of vanilla building nifs, mostly in the Gray Quarters, having huge, gaping holes that show obvious empty interiors when viewed from above.

None of them are noticeable if you play a purely vanilla game and view things from purely vanilla view angles. However the moment you start flying (or in the case for this mod, walking along the wallwalks/new districts), you'll see and experience them.

Thus, this mod fixes them up. This means the visuals should be wholesome from wherever inside the city. Objects outside the city walls will still be lacking in detail and fairly primitive, but at least the landscape will be smooth and the large structures will be there, which provide a good illusion of what outside actually looks like.

In the Tamriel worldspace, new standin structures (walls, towers, etc...) were added to ensure the Windhelm city look more or less the same outside as it does inside. For technical reasons, they won't look 100% the same, but unless you squint your eyes and look for it, you probably won't notice.

Additional occlusion planes were added along the wall partitions to reduce Windhelm Worldspace draw calls and keep performance reasonable.

## Navmesh and Compatibility

The mod is fully navmeshed, with all doors linked to navmesh door triangles.

In the Tamriel Worldspace, standin structures (walls, towers, etc...) have been added to make Windhelm look outside the same it looks inside. As a result, the newly expanded areas cover good portions of Tamriel exterior navmesh.

These were entirely dealt with using NAVCUT boxes, which means other than the new northeast gate's door triangle, no navmesh records in the Tamriel worldspace were touched. Thus, this mod should play well with any other exterior expansion mod that does not directly conflict in object placement. Their navmesh changes should seamlessly combine with the NAVCUT boxes used in this mod, resulting in the best of both worlds, and keeping any need for patching as simple a problem as possible.

Areas directly outside the southern walls and dock gate were left alone, in order to minimize compatibility issues with exterior expansion mods such as Windhelm Bridge Overhaul, Windhelm Exterior Altered, and Windhelm Dock Pathways. I am not aware of any exterior expansion mods that put things on the west side and northeast side of the city, and thus those are the only directions I expanded the city towards.

In the Windhelm worldspace, vanilla areas are largely left alone, with the exception of a few places that transition from vanilla area to newly-expanded areas. This should make it so that mods that try to beautify/clutterfy vanilla areas, such as JK's Skyrim/Dawn of Skyrim, should not have severe conflicts that are not easily resolvable in a patch.
