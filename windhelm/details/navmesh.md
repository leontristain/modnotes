# Navmesh Changes

The following vanilla navmesh were modified/extended. Other than what's mentioned here, there should be no other vanilla navmesh that are touched by this mod. This means other vanilla navmesh will not have override records in the mod's plugin, and this was done by meticulously checking the data and hand-deleting unintended overrides in xEdit, then regenerating NAVI in the CK, and double-checking edge/door links in the CK both before and after. Pathing issues not mentioned below are handled via NAVCUT boxes. Hopefully this minimizes patching efforts with other mods.

## Windhelm Worldspace

### Blacksmith Quarters Navmesh
```
Cell: (32, 8) "WindhelmCandlehearthHallExterior"
NAVM Record: 0004b66c
```
* This navmesh covered the main road from the Southern Gate to the Market Square; it was extended up the newly added wall-side stairs to cover portions of Southern Wallwalk.

### Palace of the Kings Navmesh
```
Cell: (32, 10) "WindhelmPalaceOfTheKingsExterior"
NAVM Record: 000ed015
```
* This navmesh extended over to valunstrad to connect to a valunstrad navmesh; the valunstrad "stub" has been extended upward to climb the newly added stairs, and goes on to cover portions of the Northern District.

### Aretino-Prison Navmesh
```
Cell: (33, 9) "WindhelmOrigin"
NAVM Record: 000f1a86
```
* This navmesh covered the road that goes through the Aretino Residence and the Prison structure. On the southern side, it has been extended up the Dockside Keep stairs and then over across the top of the Dock Gate to cover portions of the Gray Quarters Wallwalk. On the northern side, it has been extended through the cross-path of the new Arena Prison structure to cover portions of the Gray Quarters Wallwalk.

### Market Square Navmesh
```
Cell: (31, 8) "WindhelmMarketplaceExterior"
NAVM Record: 000f7797
```
* This navmesh covered most of the Market Square; it has been extended further west to cover the expanded market square, then under the high road bridge to cover portions of the Western District. It has also been extended above the wallwalk to cover portions of the Southern Wallwalk and High Road. The vanilla "holes" in the navmesh that used to accomodate some vanilla positions of market stands have been reduced in size in response to those market stands being repositioned elsewhere in the mod.

### Clan Shatter-Shield Navmesh
```
Cell: (31, 9)
NAVM Record: 0002e50f
```
* This navmesh covered the front of the Clan Shatter-Shield house. It has been extended up the newly added stairs to the left side of the house, to cover portions of the High Road. Along the High Road, it now goes north and then back down around to connect to the Hjerim navmesh.

### Hjerim Navmesh
```
Cell: (31, 10)
NAVM Record: 000be45a
```
* This navmesh covered the front side of Hjerim. Its geometry was not changed by the mod, but some "stub" navmesh that it used to connect to (000ed002, 000ed00f) that goes to a dead end, is now replaced by the Clan Shatter-Shield navmesh's High Road extension coming down the new stairs added there.

### Navmesh Sunk Below Ground
```
Cell: (31, 0)
NAVM Record: 000ed002

Cell: (31, 10)
NAVM Record: 000ed00f
```
* These two navmesh are small stubs that covered route around the side of Hjerim to a dead end. The mod adds a stair there to the high road. This connection allowed the High Road extension of the Clan Shatter-Shield navmesh to come down, replacing these two navmesh, to connect to Hjerim Navmesh. These two navmesh thus have been "disabled" by being sunk far beneath the ground. These two navmesh are small and had negligible role even in the vanilla game.

## Tamriel Worldspace

## Northeast Gate Navmesh
```
Cell: (34, 10)
NAVM Record: 000fc12b
```
* The new Northeast Gate now has a door triangle on this navmesh. A few vertices have also be repositioned slightly.

## Windhelm Pit Worldspace

## Windhelm Pit Navmesh
```
NAVM Record: 00040428
```
* The restored Windhelm Arena door link now has a door triangle on this navmesh.