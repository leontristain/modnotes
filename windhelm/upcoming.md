# Anticipated Future Work

Other than continuous improvement over the [Base Mod](/windhelm/base.md), and eventual patches with popular mods like JK's, I am also planning to do the following work as independent pieces or addons. These represent content that would "complete the vision" for the expanded Windhelm city, but for modularity/cleanliness purposes, should be created separately from the base mod.

## Mountain Rework North of Windhelm

The base mod currently have a set of northern walls designed to protect enemies that try to attack from the north over the mountains. However, the walls are currently raised incredibly high to the point where they could be seen as a distracting eyesore from the rest of the city, and even then, they don't achieve sufficient height to believably prevent enemies from scaling the walls from that direction.

I see the main issue here being the shape of the mountains to the north and a "valley" in-between two peaks from which enemies could believably march into to get to the walls.

Thus, I think a better solution than to make ridiculously high walls, is to rework the mountains there. Add more big mountain rocks with extreme vertical slopes on both sides, and block off the "valley" with them. The result should be a highly effective natural barrier making the wall less necessary. No enemy would be able to lead large armies over such peaks, and view of that area from the city would look a lot more natural.

This involves placing more objects and NAVCUT boxes in the Tamriel worldspace, and adding similar standins into the Windhelm worldspace. I can see it being done entirely in its own small mod, and I can see the it being a .esl, so it makes sense to keep it separate.

## Northeast Road to Winterhold

The base mod adds a northeast gate that opens to the snowy plains beyond. What I want to happen is to pave a new road from there for a more straightforward path to Winterhold.

I have already identified such a path as drawn in the following picture (in orange):

![](/windhelm/pics/roadtowinterhold.png?raw=true "Route To Winterhold")

I believe implementation can be purely isolated from the base mod. It would involve only laying down road stones along the path and setting preferred triangles on the affected navmesh. The base mod does touch the navmesh at the gate in order to add the door triangle, but this road addon does not have to touch that cell and can start the road one cell after. For all other places along the road, navmesh geometry shouldn't need to change, only metadata on the triangles to turn them into preferred paths.

Probably also need to add road signs to match at junctions.

## Windhelm Dock Expansion

The dockside in the Tamriel worldspace has expansion potential. However I think there may already be mods that address this, in which case perhaps patching the base mod with them would be sufficient.

But if not, here are rough sketches on some dockside expansion ideas:

![](/windhelm/pics/docksideexpansionidea.png?raw=true "Dockside Expansion Idea")

In the picture, orange is the road path, where the missing right side should be achievable by duplicating the path on the left side (which comes with a bunch of piers too). Blue represents where the water line might need to be pushed to, which would suggest potential terrain edits (hopefully this won't be necessary. Green represents where house facades can be pushed into, and I think "Stormcloak Cabin Resource" (i.e. the structure used for the Northeast Pub, Warehouse, and Residences) may be a great fit for these dock buildings.
