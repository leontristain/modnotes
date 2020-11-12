- [Community Effort Plan](#community-effort-plan)
  - [What Remaining Work Are Left?](#what-remaining-work-are-left)
  - [How Contributions Will Be Managed](#how-contributions-will-be-managed)
  - [What Can Addon Authors Work On?](#what-can-addon-authors-work-on)
  - [What If I Want Something In The Base Mod Changed?](#what-if-i-want-something-in-the-base-mod-changed)
  - [Is Windswept Manor Commons Part Of The Base Mod?](#is-windswept-manor-commons-part-of-the-base-mod)
  - [Concerns Regarding Dependencies Between Addons](#concerns-regarding-dependencies-between-addons)
  - [Concerns Regarding Plugin Count](#concerns-regarding-plugin-count)
  - [Concerns Regarding Overlapping Content](#concerns-regarding-overlapping-content)

# Community Effort Plan

## What Remaining Work Are Left?

The remaining work involves:

 - interiors
 - NPCs
 - quests, merchants, other dynamic gameplay content
 - exterior decor/clutter

## How Contributions Will Be Managed

The current state of the mod is what I consider the "base mod", which includes the expanded city layout, navmesh, working door links, and stub interior cells. In order to best isolate contributor works from each other and minimize compatibility concerns, I will be in charge of these "infrastructure" bits of the expanded city, and ask contributors to not touch exterior layout, navmesh, and door links.

I'd like to ask contributors to contribute their content as modular, self-contained "***addon***" mods in their own ESPs. The addon esp would depend on my base mod (as master). Addons should abide by [these guidelines](/windhelm/guidelines.md) in order to keep addon content self-contained and isolated, so that we may reap the benefits of this "base mod + addon" scheme.

This "base mod + addon" scheme has the following advantages:

* The base mod provides a common platform for addon authors to work on independently of each other.
* The base mod can take up the responsibility of patching with other Windhelm overhaul mods like JK's/DoS, and addons should be largely isolated from these changes.
* The base mod can progress in parallel with addons. I will do the best I can at maintaining backwards compatibility with base mod updates.
* Addons are self-contained and isolated from each other, minimizing conflicts and patching needs between addons (as long as [guidelines are followed](/windhelm/guidelines.md))
* Addons are modular and composable, allowing for combinations of addons to be curated together into "addon packs" or simply be picked and chosen by users themselves.
* The overall scheme should minimize the baseline of responsibility addon authors need to assume. For a typical small sized addon there shouldn't be a need for the addon author to have to worry about patches or future maintenance. A lot of addon projects can be a "make it once and then forget" kind of thing. Hopefully this makes such addons novice-friendly modder projects.
* The overall scheme should end up giving addon authors a lot of flexibility. An addon could be of any size, so novice mod authors could pick up a small beginner project while highly interested prolific authors can attempt something really big and complex.
* The overall scheme should end up giving addon authors a lot of creative freedom to work on their own vision. There's no need to conform to a singular vision, and multiple addons that implement the same building could each have their own audience (see [Concerns Regarding Overlapping Content](#concerns-regarding-overlapping-content)).

When addons are complete, they are expected to be published independently, and potentially eventually merged into an "addon packs". From the player's perspective, a feature-complete Epic Windhelm Expansion would be a combination of the base mod and any number of addons or addon packs used together. Please see [Concerns Regarding Plugin Count](#concerns-regarding-plugin-count) for why addon packs are part of this plan.

This means I am encouraging and hoping for contributors to provide open permissions for myself or others to include their creative work in any "addon packs" I or others may curate eventually. Of course I cannot require this, but I do highly and heavily encourage it.

## What Can Addon Authors Work On?

Barring logistical issues (see [Concerns Regarding Dependencies Between Addons](#concerns-regarding-dependencies-between-addons)), contributors are free to work on any interiors, NPCs, quests, merchants, other dynamic gameplay content, and decor/clutter. For example:

* A small-scale addon mod that builds out a single interior and adds NPCs that live in it.
* A small-scale addon mod that builds out a single interior as a merchant shop, complete with NPCs with a shop schedule.
* A large-scale addon mod involving multiple related interiors, lots of NPCs, and large quests.
* A small-scale mod that simply adds decor and clutter to various places around the city, making it look prettier.
* A minimal mod that patches some other unrelated mod into the interiors of these buildings.

Basically, you are free to work on anything. All I ask is that you follow [these guidelines](/windhelm/guidelines.md). I also encourage you to keep your addons modular and self-contained. For example, if you are implementing 2 interiors, see if you can organize the work into two separate addons where at least one if not both could be self-contained and standalone. See [examples here](https://github.com/leontristain/modnotes/blob/main/windhelm/guidelines.md#please-keep-your-content-as-modular-and-self-contained-as-possible). (Also related: [Concerns Regarding Plugin Count](#concerns-regarding-plugin-count))

For interested folks, a good starting point is to read [the overview](/windhelm/overview.md) and then browse through [what buildings are available](/windhelm/details.md), maybe one or two of them would spark your imagination and interest. When you start, please feel free to let me know what you'll be taking a stab at, so that I am informed on the overall state of the community effort. I have also opened up the ["Forum" section in the base mod's NexusMods page](https://www.nexusmods.com/skyrimspecialedition/mods/40745?tab=forum), where folks can discuss ideas, share work, and potentially coordinate between multiple related addons, if necessary.

## What If I Want Something In The Base Mod Changed?

If you are a contributor and you feel strongly about something in the base mod that I asked you not to touch, let's chat. Also, if you feel like something you're about to change really should be the base mod's responsibility to be made available to everyone, let's also chat.

For example, if you feel the need to put an idle marker somewhere that the existing navmesh currently doesn't reach, please talk to me. I will be able to update the navmesh for you in the base mod.

Another example, if you want to add a market stall into one of the empty squares that look like it should be a market, but don't feel comfortable putting a stall there yourself due to potential conflict with another addon, let me know. I will try to figure something out. I may make the decision to put it directly into the base mod, or to start creating a base market addon that will satisfy your needs.

Another example, if you feel very strongly about a particular creative decision in the base mod that could be vastly improved, then let's chat. I may already agree with you, or I may be convinced by your arguments. If so, I will put it on my [list of future work](/windhelm/upcoming.md) to get to.

And if all else fails, you are always free to create a traditional patch or even fork my base mod. My permissions are fully open so you can do anything. Though if you do patch or fork my mod then know that you are taking up future maintenance responsibility for your patch or fork.

## Is Windswept Manor Commons Part Of The Base Mod?

[Windswept Manor](/windhelm/details/windswept/main.md) is the massive house in the Western District that is built into the mountains. I originally intended for it to be a player house, but got the feedback that the entire thing is far too large to be a single player house. We then discussed the issue and decided that it could have a cool back story involving a foolish Thane who once tried to build a house bigger than the Jarl's, and then later fell into financial ruin and couldn't pay his debts. The bank then forced the house to be subdivided into multiple units, leaving only the top floor being the actual thane residence.

Thus, what we currently have is that, when you enter Windswept Manor, you enter into the [Windswept Manor Commons](/windhelm/details/windswept/commons.md). This area is public space, and contains many doors that lead into individual interior spaces. The "commons" is already built out in the base mod (but lacking in clutter and decorations like much of the rest of the expansion). It's fully navmeshed, and I am currently treating it as part of the city layout / "infrastructure". This means going forward, I will include Windswept Manor Commons in potential base mod improvements and updates.

Thus, I am expecting folks to work on individual subdivisions or interiors further within Windswept Manor Commons, but treating Windswept Manor Commons the same as outside stuff - additive decorations and markers are great, but don't touch door links and don't touch navmesh, etc...

That being said, if you have an absolute killer idea that requires completely re-doing and replacing Windswept Manor Commons, I think you can still feel free to do that. You can, for example, relocate the Windswept Manor Commons interior door into your own cell, and go from there. All this will mean is that your addon will be incompatible with any other addon that tries to integrate into the existing Windswept Manor Commons, that's all.

## Concerns Regarding Dependencies Between Addons

Some addons may naturally depend on other addons.

For example, an addon that tries to build out an interior of one of the residences, and adds an NPC to live in it, may want the NPC to loiter around the market during the day, eat dinner at the [Meadhall](/windhelm/details/western/meadhall.md) in the evening, then head over to chill at the [Windhelm Bathhouse](/windhelm/details/western/bathhouse.md) for an hour, before heading home for the night. This addon would depend on a completed implementation of both the Meadhall and Bathhouse locations.

Since I am giving addon authors "free reign" in what they choose to work on, I am expecting these dependencies to manifest naturally. For example, folks working on residences may find that they are blocked initially until we have folks interested and then completing the communal buildings, which may naturally encourage folks to work on the communal buildings because they are not blocked by other dependencies.

If there is a need for authors of multiple related addons to coordinate, I've opened up the ["Forum" section in the base mod's NexusMods page](https://www.nexusmods.com/skyrimspecialedition/mods/40745?tab=forum) which might be a good place for discussions and coordination.

## Concerns Regarding Plugin Count

With a flexible "addon" ecosystem being attempted here, there is the concern that many addons may eat into the user's plugin count. This is expected to be mitigated in two ways:

First, addon authors are encouraged to release ESPFE (ESL-ified ESPs) plugins whenever possible. ESPFEs have a limitation of 2048 new records, however 2048 is likely enough for small-sized addons. For some examples to compare against: [Wares of Tamriel](https://www.nexusmods.com/skyrimspecialedition/mods/31519) has ~800 records. [Crossroads Inn](https://www.nexusmods.com/skyrimspecialedition/mods/1406) has ~1000 records, [Astronomer's Loft](https://www.nexusmods.com/skyrimspecialedition/mods/38059) has ~700 records. Also worth consider is that mid-sized addons too big for ESPFE might be splittable into multiple, smaller, standalone addons that can fit into ESPFE (See: [related part of the guideline](https://github.com/leontristain/modnotes/blob/main/windhelm/guidelines.md#please-keep-your-content-as-modular-and-self-contained-as-possible)).

Second, multiple addons can be merged together into "addon packs". See [How Contributions Will Be Managed](#how-contributions-will-be-managed). I am strongly encouraging, and hoping, for addon authors to provide permissions for their work to be eventually curated into addon packs. From the player's perspective, an addon pack could dramatically decrease the number of ESPs that need to be loaded.

Of course, authors are free to not give permission to include their work in addon packs. I would like to think that if an author want to keep tight control over their work, then the author must've created a large, extensive, high quality mod that took lots of time and effort. If so, then perhaps it is deserving of an ESP slot of its own. There are certainly mods that add one thing to a city that I as a user would not begrudge spending an ESP slot on, such as [Morskom Estate](https://www.nexusmods.com/skyrimspecialedition/mods/33408) or [Drengin's Blue Palace Terrace](https://www.nexusmods.com/skyrimspecialedition/mods/35180).

Standalone addons that cannot be merged into addon packs, of course, can still be used alongside addon packs, as long as they do not overlap.

Beyond this, of course users are free to merge their own mods, though this has a high technical bar so many users might not be able to do this.

## Concerns Regarding Overlapping Content

Multiple addons that change the same thing obviously are not compatible with each other. This is true, however I do not see it as a problem, since the users and addon pack curators can choose one among the two, and each addon can have its own audience. In contrast, if contributor work is managed the typical way as a singular overall project with a single vision, then only one person's creative vision will be realized.

Regarding "addon packs", while I plan to eventually curate and release my own "addon pack" out of the addons we get that provide permissions for it, I will release it as a separate mod from the base mod so to not advertise it as "official". From my perspective, anyone can curate their own addon pack and release it (assuming permissions are given), and any addon may be chosen by any addon pack to be included, and therefore the market should be fair for addons.
