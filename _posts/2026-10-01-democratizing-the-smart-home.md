---
title: Democratizing the smart home
description: My smart home had one real user, and it was me. What it took to change that, and why an old Echo Show 5 turned into the most important part of the setup.
category: smart-home-for-everyone
tags: [home-assistant, view-assist, echo-show, wall-panel]
project: panelkit
---

My Home Assistant setup grew the way these things usually grow. A Reolink camera outside with person detection. Sonos speakers in several rooms, playing from Spotify. Calendars synced from iCloud. Lights. Automations I was quietly proud of.

At some point I noticed that the other adult in this house used almost none of it. Most of the apps were never installed, and how the pieces fit together was a complete mystery to them. What I got instead was the same question, again and again: can you dim the lights? In this room, in that room. I had turned into the remote control for my own smart home.

Which is fair. I never explained any of it, and honestly, I wouldn't know where to start.

## What I mean by democratizing the smart home

When people talk about democratizing the smart home, they usually mean cheaper devices or open standards that let everything talk to everything. Both matter. But they solve the problem for the person who sets things up. In a lot of homes, mine included, that person was never the bottleneck.

The bottleneck is everyone else who lives there. A smart home where one person holds all the knowledge isn't shared, it's run. Everybody else depends on that one person, and the dimming question is what that dependency sounds like day to day.

So for me, democratizing the smart home means something narrower and more practical: everyone who lives in the house can use it, without help, without installing anything, and without understanding how it works underneath.

Looking at my own setup, that breaks down into three things it was failing at.

**Access.** If using the house requires an app, a login and the right dashboard, most people won't use it. Not because they can't, but because there's no reason to bother when you can just ask.

**Legibility.** You should understand what you're looking at in a glance. Entity names, device lists and status icons make sense to the person who built them and to nobody else.

**Independence.** Dimming the lights shouldn't need me. Neither should checking who's outside or putting on music. Every time someone has to ask, the system failed.

## The device that was already accepted

What made the difference wasn't new hardware. We already had an Echo Show 5 on the counter, and nobody had to be talked into using it. People read the time off it and tapped it without thinking. In a shared home, that kind of acceptance is harder to get than any feature, and it covered access and legibility before I'd changed a single thing.

So instead of adding another device, I changed what this one does. I flashed it with LineageOS, which replaces Amazon's software, and installed the companion app for [View Assist](https://github.com/dinki/View-Assist). Now it's a Home Assistant panel. Same device, same spot, a completely different screen.

## What's on it

The default screen is a clock you can read from across the room, with the weather and the next appointments underneath. The background color shifts with the time of day. Most of the time that's all anyone needs from it, and nobody has to touch anything.

When the Reolink detects a person, a banner appears on that clock screen. Tapping it opens the live stream, with a button for the floodlight next to it.

A bar on the right holds five icons: home, camera, music, lights, calendar. The lights page is the direct answer to the dimming question: each room, each light, large enough to hit without aiming. The music page controls the Sonos speakers, one room or several, with large volume buttons and the next songs in the queue. The calendar page shows the week from the shared iCloud calendars.

After a short while without a touch, the panel goes back to the clock on its own.

## Four rules I'd apply to any panel

These are the rules I'd give anyone building a panel for a household rather than for themselves.

**The idle screen has to be worth a glance.** If the panel only becomes useful once you start tapping, it's just another app on a stand.

**Everything sits one tap away from the clock.** Anything that needs a second level of navigation is something only I will use. That belongs in the regular Home Assistant dashboard, not on the panel.

**No settings, no entity names, no status pages.** When something breaks, I fix it from my laptop. The panel doesn't need to explain itself.

**It always returns home.** Whoever walks by next shouldn't find a music page someone left open an hour ago.

## What it costs, and who pays

Democratizing the use of a smart home doesn't democratize building it. Flashing only works on specific Echo Show models and firmware versions. It takes a few evenings, and if something goes wrong the device may not boot again. On top of that, View Assist and the custom cards I use mean a fair amount of YAML.

All of that still lands on one person. The difference is that it lands once, during setup, instead of every evening as a question about the lights. That's a trade I'd make again.

The setup side is where I think the next step is. Not every household has someone willing to write YAML for weeks, and that's the part I'm trying to make smaller.

## Next

[PanelKit](https://github.com/ma-2a/panelkit) is my attempt at that: a visual editor for View Assist dashboards. Pick your screen, lay out the grid, drop in your cards, copy the result. You can [try the builder here](https://ma-2a.github.io/panelkit/builder/).

The full setup goes in the next post: flashing, View Assist, every integration, every card, and the places I got stuck.
