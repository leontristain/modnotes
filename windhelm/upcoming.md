- [Anticipated Future Work](#anticipated-future-work)
  - [Base Mod Work](#base-mod-work)
    - [Continuous Bug Fixes And Quality Improvements](#continuous-bug-fixes-and-quality-improvements)
    - [Beacon of Windhelm Lighthouse Structure](#beacon-of-windhelm-lighthouse-structure)
    - [Make Northern District Bonfire Smaller](#make-northern-district-bonfire-smaller)
    - [Shininess Pass](#shininess-pass)
    - [Northeast Gatehouse Portcullis And Murder Holes](#northeast-gatehouse-portcullis-and-murder-holes)
    - [Battlements](#battlements)
    - [Windswept Manor Balcony Railing](#windswept-manor-balcony-railing)
    - [Tamriel Worldspace Intruder Prevention](#tamriel-worldspace-intruder-prevention)
    - [Civil War Compatibility](#civil-war-compatibility)
  - [Eventual Patches](#eventual-patches)
    - [Windhelm Worldspace](#windhelm-worldspace)
    - [Tamriel Worldspace](#tamriel-worldspace)
    - [Fortified Windhelm, Capital Windhelm Expansion (when they come out)](#fortified-windhelm-capital-windhelm-expansion-when-they-come-out)
    - [USSEP](#ussep)
    - [Faction: Pit Fighter](#faction-pit-fighter)
    - [AI Overhaul](#ai-overhaul)
    - [A Note On Open Cities Skyrim](#a-note-on-open-cities-skyrim)
  - [Work To Be Done As Separate ESPs](#work-to-be-done-as-separate-esps)
    - [Mountain Rework North of Windhelm](#mountain-rework-north-of-windhelm)
    - [Northeast Road to Winterhold](#northeast-road-to-winterhold)
    - [Windhelm Dock Expansion](#windhelm-dock-expansion)

# Anticipated Future Work

## Base Mod Work

### Continuous Bug Fixes And Quality Improvements

There are remaining bugs and quality issues in the base mod that I will continue to address and improve. These may include:

* Many structures could be tweaked to look better
* Need to fix small cosmetic and gameplay issues, such as imprecisely moved objects that hover above ground, nooks and crannies that player could get into but could not get out, etc...
* More standin equivalence between Tamriel and Windhelm worldspaces
* Further occlusion planes improvement
* Mark objects properly as snow so that things like footsteps show up and sound right.
* Lighting pass for exterior light sources and windows
* Idle markers where they make sense
* Quality check on door openings - add black planes behind them where necessary.
* Compatibility pass with mods like Frostfall (i.e. ensure all fire sources work as warmth etc...)
* Issue related to LODs (or lack thereof)
* Snow shader shenanigans (usually only an issue when you are far away)
* Cleaning out redundant and unused objects that have accumulated over time.
* Identify and cleaning up any accidental vanilla record changes that for some reason can't be cleaned as ITMs (like maybe I accidentally moved it by a pixel and now it's no longer perfectly identical).

### Beacon of Windhelm Lighthouse Structure

The current "Beacon of Windhelm" is a simple giant camp bonfire. Following some feedback and discussion from folks on NexusMods, we have decided that a lighthouse beacon structure would be better. An existing Frostflow Lighthouse nif can be retextured using Windhelm/Nordic textures, and its size should fit nicely.

### Make Northern District Bonfire Smaller

The northern district bonfire is perhaps a tad too large. Perhaps a smaller bonfire there would be a bit more realistic.

### Shininess Pass

It seems that with vanilla textures, some of the structures are overly shiny. I will take a look at how to address this. Perhaps with more nif hacking.

I suppose I can say that the base mod is "optimized" for NobleSkyrim in mind, but I should certainly take a look at reducing "glaring issues" (hehe) for other textures.

### Northeast Gatehouse Portcullis And Murder Holes

The [Northeast Gatehouse](/windhelm/details/northeast/gatehouse.md) has a fairly large space underneath the gate. This could use a portcullis and some murder holes which may make Shadiversity fans a bit happier. Though the vanilla portcullis nif is too small for this purpose, maybe I can find some witcher nifs for it. Murder holes can probably be made out of some of those windows. Of course it will all just be for appearances and nothing is expected to actually be functional.

### Battlements

Currently, the wallwalks are basically lined on both sides with a big, rectangular log. This has been my best idea so far but it's obviously not ideal.

It would be really cool if we can add battlements along the outward-facing edge of the walls. Currently, there is a wall piece from "Castle Modders Resource" that I can use, though I worry that the size of the piece means a lot of copies are needed to fully cover all the walls. Would that result in performance issues? Not sure.

Anyway, things to be experimented with.

### Windswept Manor Balcony Railing

The [Windswept Manor Suite](/windhelm/details/windswept/suite.md) has an awesome balcony. The fences of that balcony however are currently a bunch of overlapping ladders, and the overlapping surfaces means if you squint your eyes you can see the textures flickering. I plan to redo the railing to resolve this issue.

### Tamriel Worldspace Intruder Prevention

I imagine one reason vanilla Windhelm only _barely_ touches the mountainside with one of its corners, is because that design made it easy to prevent people from jumping into the city (and all those Tamriel worldspace building LODs) from above the mountain. With my expansion more or less hugging the mountain, this becomes a legitimate quality concern. As it stands, if you climb to the mountain peak in Tamriel worldspace and jump into the city, you'll end up among the LOD chaos and get stuck. Any player can of course un-stuck themselves using various console tricks, but ideally we wouldn't have to do that.

I think this can be solved by cleverly using collision planes and autoloaddoors. Make it so that in some places, you simply can't jump over the walls at all, and in other places, jumping over the walls and into the city will teleport you into an appropriate location into the Windhelm worldspace.

### Civil War Compatibility

Windhelm is involved in the civil war, so a Windhelm expansion should ideally be compatible with the civil war events.

Thus far, since I didn't touch the vanilla content much, I suspect it should remain compatible with the civil war events. However, the new areas would not be affected by civil war events, so there may be some oddities. For example, during certain civil war events, vanilla buildings may be burning next to newly added buildings that are not - I don't know how bad or weird this may look. Another example is that there are "anti-fast travel" regions drawn with gigantic boxes that cover the entire vanilla Windhelm. Those may need to be enlarged to also cover the expanded Windhelm, or you'll be able to simply, in the event, walk over to an expanded area, and then fast travel out of there and break the game.

Anyway, at some point there will probably be a pass to address these. Until then, the player can always choose to not stray away from the normal/expected path, and the player can always fix issues using console tricks.

## Eventual Patches

### Windhelm Worldspace

* JK's Skyrim / Dawn of Skyrim

### Tamriel Worldspace

* Windhelm Bridge Overhaul (if anything is needed)
* Windhelm Exterior Altered
* Windhelm Docks Pathways

### Fortified Windhelm, Capital Windhelm Expansion (when they come out)

I've been told that the author of [Fortified Whiterun](https://www.nexusmods.com/skyrimspecialedition/mods/40094) is working on a [Fortified Windhelm](https://www.nexusmods.com/skyrimspecialedition/images/84030) mod. This mod is not yet released but there are preview screenshots with really great looking battlements. When this mod is out I will be attempting a patch to see if we can get this mod's interior expansion and wallwalks but with that mod's battlements, gate, and bridge. Wouldn't that be amazing?

I've also learned that the author of [Capital Whiterun Expansion](https://www.nexusmods.com/skyrimspecialedition/mods/37982) is working on an interior expansion mod for Windhelm. This mod and that mod conflicts in concept so a direct patch may not be possible. However I am a huge fan of Surjamte's work with Whiterun and I'm sure the Windhelm version will come with many high quality interiors, NPCs, and quests, and I wonder if at the very least I can create a patch that brings over some of the interiors, NPCs, and quests into my city layout and buildings as an addon.

Of course these mods must come out first, then we shall see what's possible.

### USSEP

The base mod needs an USSEP patch. If you see floating icicles around the Arena prison - those are some USSEP-added objects that can only be disabled or relocated in an USSEP patch.

### Faction: Pit Fighter

The base mod restores the arena structure but doesn't touch any playable content. Faction: Pit Fighter is the forefront mod that restores the arena quest content, so it would be nice to patch that in. I currently don't know how straightforward it would be to do that since I've never played through that mod myself, but it's definitely something to take a stab at.

### AI Overhaul

This mod was mentioned as a potential patch candidate, so I will look at this at some point. Not yet sure whether a patch is easy or difficult or needed at all. I think it will depend on what it does to navmesh if any.

### A Note On Open Cities Skyrim

I do not plan to eventually work on an Open Cities patch, or, more accurately, an OCS patch is very low priority for me and I don't expect to ever get to it.

I personally do not use Open Cities Skyrim and not a fan of the idea in general. I think throwing everything into one worldspace makes compatibility and large modlists a harder problem for folks to solve. My personal view is also not only that loading doors don't bother me, but that Skyrim could use _more_ loading doors and separated spaces. Separate spaces help with modularity and confining the scope of issues. It can also be advantageous in that the inside can be bigger or different from the outside and still allow suspension of disbelief.

Though, I recognize that these are personal views and lots of people think differently (after all OCS is incredibly popular). That said, as you can clearly see here, there are tons of other work to do. So with my personal preference on OCS, I naturally have less motivation to work on an OCS patch, and thus I will be prioritizing an OCS patch near the bottom of my list, which realistically means I don't expect to ever get to it.

That said, anyone else is completely free to work on an OCS patch. More choices is always better than less choices.

Currently, the base mod is roughly the same size inside as it is outside, so I believe fundamentally an OCS patch is possible.

## Work To Be Done As Separate ESPs

### Mountain Rework North of Windhelm

The base mod currently have a set of northern walls designed to protect enemies that try to attack from the north over the mountains. However, the walls are currently raised incredibly high to the point where they could be seen as a distracting eyesore from the rest of the city, and even then, they don't achieve sufficient height to believably prevent enemies from scaling the walls from that direction.

I see the main issue here being the shape of the mountains to the north and a "valley" in-between two peaks from which enemies could believably march into to get to the walls (circled below).

![](/windhelm/pics/futuremountainchanges.png?raw=true)

Thus, I think a better solution than to make ridiculously high walls, is to rework the mountains there. Add more big mountain rocks with extreme vertical slopes on both sides, and block off the "valley" with them. The result should be a highly effective natural barrier making the wall less necessary. No enemy would be able to lead large armies over such peaks, and view of that area from the city would look a lot more natural.

This involves placing more objects and NAVCUT boxes in the Tamriel worldspace, and adding similar standins into the Windhelm worldspace. I can see it being done entirely in its own small mod, and I can see the it being an ESPFE, so it makes sense to keep it separate.

### Northeast Road to Winterhold

The base mod adds a northeast gate that opens to the snowy plains beyond. What I want to happen is to pave a new road from there for a more straightforward path to Winterhold.

I have already identified such a path as drawn in the following picture (in orange):

![](/windhelm/pics/roadtowinterhold.png?raw=true "Route To Winterhold")

I believe implementation can be purely isolated from the base mod. It would involve only laying down road stones along the path and setting preferred triangles on the affected navmesh. The base mod does touch the navmesh at the gate in order to add the door triangle, but this road addon does not have to touch that cell and can start the road one cell after. For all other places along the road, navmesh geometry shouldn't need to change, only metadata on the triangles to turn them into preferred paths.

Probably also need to add road signs to match at junctions.

### Windhelm Dock Expansion

The dockside in the Tamriel worldspace has expansion potential. However I think there may already be mods that address this, in which case perhaps patching the base mod with them would be sufficient.

But if not, here are rough sketches on some dockside expansion ideas:

![](/windhelm/pics/docksideexpansionidea.png?raw=true "Dockside Expansion Idea")

In the picture, orange is the road path, where the missing right side should be achievable by duplicating the path on the left side (which comes with a bunch of piers too). Blue represents where the water line might need to be pushed to, which would suggest potential terrain edits (hopefully this won't be necessary. Green represents where house facades can be pushed into, and I think [Stormcloak Cabin Resource](https://www.nexusmods.com/skyrim/mods/66514/) (i.e. the structure used for the Northeast Pub, Warehouse, and Residences) may be a great fit for these dock buildings.
