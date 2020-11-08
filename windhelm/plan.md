# Plan For Community Effort

## What Remaining Work Are Left?

The remaining work involves:

 - interiors
 - NPCs
 - quests, merchants, other dynamic gameplay content
 - exterior decor/clutter

## How Contributions Will Be Managed

The current state of the mod is what I currently consider the "base mod", which includes the expanded city layout, navmesh, working door links, and stub interior cells. In order to best isolate contributor works from each other and minimize compatibility concerns, I will be in charge of these "infrastructure" bits of the expanded city, and ask contributors to not touch exterior layout, navmesh, and door links.

I'd like to ask contributors to contribute their content as modular, self-contained "***addon***" mods in their own ESPs.

This "base mod + addon" scheme has the following advantages:

* The base mod provides a common platform for addon authors to work on.
* The base mod can take up the responsibility of patching with other Windhelm overhaul mods like JK's/DoS, and addons should be largely isolated from these changes.
* The base mod can progress in parallel with addons. I will do the best I can at maintaining backwards compatibility with base mod updates.
* Addons are self-contained and isolated from each other, minimizing conflicts and patching needs between addons.
* Addons are modular and composable, allowing for combinations of addons to be curated together into "addon packs" or simply be picked and chosen by users themselves.
* The overall scheme should end up giving addon authors a lot of flexibility. An addon could be of any size, so novice mod authors could pick up a small beginner project while highly interested prolific authors can attempt something really big and complex.
* The overall scheme should end up giving addon authors a lot of creative freedom to work on their own vision. There's no need to conform to a singular vision, and multiple addons that implement the same building could each have their audience (see [Concerns Regarding Overlapping Content](#concerns-regarding-overlapping-content)).

When addons are complete, they are expected to be published individually, and eventually merged into an "addon pack", that when installed together with my base mod, will represent the final, complete product.

This means I am expecting contributors to provide open permissions for myself or others to include their creative work in any "addon packs" I or others may curate eventually.

## What Can Addon Authors Work On?

Barring logistical issues (see [Concerns Regarding Dependencies Between Addons](#concerns-regarding-dependencies-between-addons)), contributors are free to work on any interiors, NPCs, quests, merchants, other dynamic gameplay content, and decor/clutter. For example:

* A small-scale addon mod that builds out a single interior and adds NPCs that live in it.
* A small-scale addon mod that builds out a single interior as a merchant shop, complete with NPCs with a shop schedule.
* A large-scale addon mod involving multiple related interiors, lots of NPCs, and large quests.
* A small-scale mod that simply adds decor and clutter to various places around the city, making it look prettier.

Basically, you are free to work on anything. All I ask is that you follow [these guidelines](/windhelm/guidelines.md). I also encourage you to keep your addons modular and self-contained. For example, if you are implementing 2 interiors, see if you can organize the work into two separate addons, as that would be preferred. (related: see below section on "Plugin Count Concerns")

For interested folks, a good starting point is to read [the overview](/windhelm/tldr.md) and then browse through [what buildings are available](/windhelm/details.md), maybe one or two of them would spark your interest and enthusiasm.

## What If I Want Something "Infrastructure-y" Changed?

If you are a contributor and you feel strongly about something "infrastructure-y" that I asked you not to touch, let's chat.

Though I reserve my right to have final call on creative decisions in the "base mod", I could very well agree with your points or be convinced by your arguments. If I do, I will handle the work myself in the base mod.

## Concerns Regarding Dependencies Between Addons

Some addons may naturally depend on other addons.

For example, an addon that tries to build out an interior of one of the residences, and adds an NPC to live in it, may want the NPC to loiter around the market during the day, eat dinner at the [Meadhall](/windhelm/interiors/western/meadhall.md) in the evening, then head over to chill at the [Windhelm Bathhouse](/windhelm/interiors/western/bathhouse.md) for an hour, before heading home for the night. This addon would depend on a completed implementation of both the Meadhall and Bathhouse locations.

Since I am giving addon authors "free reign" in what they choose to work on, I am expecting these dependencies to manifest naturally. For example, folks working on residences may be blocked initially until we have folks interested and then completing the communal buildings, which may naturally encourage folks to work on the communal buildings because they are not blocked by other dependencies.

## Concerns Regarding Plugin Count

With a flexible "addon" ecosystem being attempted here, there is the concern that many addons may eat into the user's plugin count. This is expected to be mitigated in two ways:

First, addon authors are encouraged to release ESPFE (ESL-ified ESPs) plugins whenever possible. ESPFEs have a limitation of 2048 new records, however 2048 is likely enough for small-sized addons. For some examples to compare against: [Wares of Tamriel](https://www.nexusmods.com/skyrimspecialedition/mods/31519) has ~800 records. [Crossroads Inn](https://www.nexusmods.com/skyrimspecialedition/mods/1406) has ~1000 records, [Astronomer's Loft](https://www.nexusmods.com/skyrimspecialedition/mods/38059) has ~700 records.

Second, the expected method for eventual "final form" of the Windhelm expansion involves merged "addon packs". See [How Contributions Will Be Managed](#how-contributions-will-be-managed). Addon authors are expected to provide permissions for them to be curated into addon packs, in which case plugin count would become less of an issue.

If your addon does not fit into the limit of an ESPFE, and you feel strongly about maintaining distribution control such that you don't want to provide permission to include into addon packs, then I think it's likely that you have created a large, extensive, and high-quality mod that took lots of time and effort. If so, then I think perhaps it is deserving of an ESP slot of its own, in the same way as, say, Morskom Estate deserves its own ESP slot in a modlist that overhauls Dawnstar, and Drengin's Blue Palace Terrace deserves its own ESP slot in a modlist that overhauls Solitude. In this scenario, the additional ESP slot is no more an issue than what folks should already be used to.

## Concerns Regarding Overlapping Content

Multiple addons that change the same thing obviously are not compatible with each other. This is not a problem because as separate, independent addons, each can have its own audience. In contrast, if contributor work is managed the typical way as a singular overall project with a single vision, then only one person's creative vision will be realized.

Regarding "addon packs", while I will curate and release my own "addon pack" out of the addons we get, I will release it as a separate NexusMods mod so to not advertise it as "official". From my perspective, anyone can curate their own addon pack and release it, and any addon may be chosen by any addon pack to be included. Again, permission for your addon to be part of an addon pack is not required, but I do highly encourage it.

The user is also not required to use addon packs and can choose to merge their own addon pack, or simply install individual addons separately (if they've got the space in their modlist).