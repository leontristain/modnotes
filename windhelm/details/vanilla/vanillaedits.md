# Notable Vanilla Edits

Windhelm's main south gate has been augmented with a "bridge" in order to allow the wallwalk to cross the gate from above. This "bridge" piece ended up adding a bit more to the footprint of the gate, which blocked navmesh access to the corner on the left side of the gate. Since that corner seems largely useless, I disabled the navmesh there entirely with a NAVCUT box. These are circled below.

Windhelm's new southern wallwalk needed to be accessible, so I added some thin stairs along the southern side of the road that leads to the market. This is also circled below.

![](/windhelm/pics/vanillaedit01.png?raw=true)

Like above, there are more such thin stairs along the wall all the way to the market square, and beyond.

The market square itself has been expanded further westward by roughly half of its original area. The far side is no longer a dead end. Now the road continues onward, underneath a bridge, and goes into the new Western District.

The bigger market square and nature of the path now being a "through path", meant the original placements of the market stands are now awkward and blocking people, so I rearranged the stands a bit.

The "thin stairs" that leads up to the wallwalk also displaced some firewood piles, which I relocated into the market.

All of these are shown in the below image.

![](/windhelm/pics/vanillaedit02.png?raw=true)

The old vanilla western walls have been repurposed into the [High Road](/windhelm/details/western/highroad.md) - an elevated road that runs up through the middle of the city. In Valunstrad I added two sets of stairs to make access to the high road (and the other side) easy. These are shown in the below two images.

![](/windhelm/pics/vanillaedit03.png?raw=true)
![](/windhelm/pics/vanillaedit04.png?raw=true)

On the west side of the Palace of the Kings there was a blocky structure that did not serve any purpose. I replaced the structure with a stairway that leads up to the Northern District, providing access between Valunstrad, Palace of the Kings, and Northern District.

![](/windhelm/pics/vanillaedit05.png?raw=true)

The restoration of the Windhelm Arena structure meant the prison building, which used to be a flat-topped building with an L-shaped path through it, is now replaced by the unused arena prison structure. This structure changes the L-shaped through path into a `+`-shaped crossroad paths. The old L-path directions were preserved, and now the crossroads allow direct access to the Windhelm Arena Entrance Area, the Gray Quarters Wallwalks, and the Northeast District.

![](/windhelm/pics/vanillaedit06.png?raw=true)

Lastly, there used to be a "piles-of-stones" broken half-wall across from Brunwulf's house. This has been turned into a "piles-of-stones" broken stairs that leads up to provide access to the Dockside Keep, and the Gray Quarters Wallwalks across the top of the docks gate.

![](/windhelm/pics/vanillaedit07.png?raw=true)

The above should be all major and notable edits to the vanilla Windhelm city. Other than these, there may also be some inconsequential edits that happened elsewhere, but they should be inconsequential, where patch conflicts should not result in a broken or even visually jarring game.

As far as navmesh goes, in border cells that now contain both vanilla navmesh and newly expanded spaces, the vanilla navmesh was expanded with more triangles on the same navmesh record. Vanilla navmesh records are NEVER deleted or "sunk under the terrain" to be replaced by new navmesh. The market square navmesh has been reworked (on the same record) to close up the holes it used to have that made room for market stalls. NAVCUT boxes were used to manage navmesh in some scenarios.

Hopefully, this should make patching with mods like JK's fairly simple. Though I haven't gotten there yet.