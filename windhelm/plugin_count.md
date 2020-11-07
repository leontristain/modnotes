# Thoughts Regarding Plugin Count

I'm asking folks to help with the project by contributing their content as addon plugins. One obvious downside of this approach is that from the user's perspective, to fully fill out the city we would end up with many plugins, so wouldn't it eat into a large portion of the plugin limit?

## Addon Authors Can Aim For ESPFE Plugins

To some degree, this can be mitigated with ESPFE (ESL-ified `.esp`) plugins, which do not contribute to the 255-ish limit for regular ESPs, and themselves having a sky-high limit of 4096.

However, an ESPFE plugin is limited to 2048 new records. To give some perspective, Wares of Tamriel has about 800 records, so an addon of its size could fit. Whereas, Haafingheim has about 5000 records, so an addon of its size would not fit. Overall I'm understanding this as "a simple, barebones shop containing a modest interior and an NPC" would probably be small enough, but anything bigger with more complex content would not fit.

So here, what I can encourage is for folks to try to keep addons lean and self-contained. Only add more records when they contribute value and don't accidentally or superfluously add stuff that don't really matter. If an ESPFE is possible, try to aim for it. Though I will recognize that when the content is worth it, we shouldn't sacrifice content quality just to squeeze into an ESPFE.

ESPFE plugins also have an issue where _new cells_ they add would break should the cell contents get further overridden by another plugin. For an typical addon, I don't think this is a concern. The point of this base + addon scheme is for addons to be self-contained and isolated from other addons, so it's not likely that _interior_ objects from an addon, which should be solely the opinion of that addon, to be further modified in a patch.

That said, I still encourage folks to try, as much as possible, to _reuse_ the interior cell stubs I provide in the base mod, instead of creating new cells in the addon. I recognize this isn't always possible. Sometimes you might need more cells than the stub provides. Sometimes you might want to split up a base mod interior into multiple cells. But when possible, it would be best to reuse the existing stub cell than to create a new one.

With the above, I can hope that perhaps the addons we end up getting are mostly small enough to be ESPFEs, with a few larger addons that are regular ESPs. Maybe at that point from a user's perspective it's not too bad. For example, if you end up having 20 ESPFE addons and 5 ESP addons, that means your Epic Windhelm Expansion would take up 5 slots, and maybe that's good enough already.

## Users Can Merge Addons

If ESPFEs are not enough, the next thing the _user_ can do is to merge the addons. I believe this can be done using zEdit.

Expecting users to merge addons, while a valid solution to the problem, has the downside that many users are not technical enough to know how to do this, or invested enough to make the additional manual labor worth the cost. It's certainly not an ideal expectation to have.

## There Could Be Addon Packs

If the above still isn't enough, then we can try addon packs. Essentially, anyone can merge together addons and release them as addon packs as long as all involved addon authors give permission. Then, users can download and install a single addon pack taking up 1 ESP slot instead of many individual addons taking up multiple ESP slots.

When interested addon authors let me know what they're working on, I can ask them whether they would allow their addon to be included in addon packs. Then, once plugin count becomes an issue among users, I can try to strategically curate some addon packs based on what permissions I have.

Any addon packs I curate and "release" would be independent of the base mod, so that they appear as "unofficial". Anyone else are also free to create addon packs if they have permission from addon authors involved. I also encourage authors of multiple addons to release their own wholesale addon packs.

If I ever work on addons of my own, I will provide fully open permissions so that they can be included in any addon pack.

Perhaps an addon pack would mean the user's Epic Windhelm Expansion would use up 2 slots:

* `EpicWindhelmBase.esp` (takes up 1 slot)
* `EpicWindhelm-AddonPackForBigAddons.esp` (takes up 1 slot)
* `EpicWindhelm-SmallESPFEAddon1.esp` (takes up 0 slot)
* `EpicWindhelm-SmallESPFEAddon2.esp` (takes up 0 slot)
* `EpicWindhelm-SmallESPFEAddon3.esp` (takes up 0 slot)
* ...

## Do You Have Other Ideas?

The above are all the ideas I have for how to deal with the plugin count concern while maintaining the base mod + addon scheme.

I suppose the alternative to the base mod + addon scheme is for me to manage this as a "community project" for a while - collecting volunteers, setting a singular vision, delegating tasks, and integrating results, and then once all done release it as a singular thing. The problem with this is I don't think I can commit enough time and energy to take on this role and see it all the way to the end. Hence the base mod + addon scheme, which not only gives addon authors more creative freedom, but also makes it more hands-off for me.

But if you have better ideas, I'd love to hear them so please do let me know.
