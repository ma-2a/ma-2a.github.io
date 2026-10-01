---
title: My smart home had one user, and it was me
description: How an old Echo Show 5, flashed and turned into a Home Assistant panel, became the part of my setup the rest of the household actually uses.
category: smart-home-for-everyone
tags: [home-assistant, view-assist, echo-show, wall-panel]
project: panelkit
---

My Home Assistant setup grew the way these things usually grow. A Reolink camera outside with person detection. Sonos speakers in several rooms, playing from Spotify. Calendars synced from iCloud. Lights. Automations I was quietly proud of.

At some point I noticed that the other adult in this house used almost none of it. Most of the apps were never installed, and how the pieces fit together was a complete mystery to them. Which is fair. I never explained it, and honestly, I wouldn't know where to start.

Look at what I was implicitly asking for. One app for the camera, one for the speakers, one for the calendar, each with its own login and its own idea of where the buttons go. Then Home Assistant on top, the thing that supposedly ties it all together, as long as you know which dashboard to open. For me that's a hobby. For everyone else it's just complicated.

## What the rest of the house actually needs

When I wrote down what my toughest user wants from all that hardware, the list was short: see who's outside, put on music, check what's happening today, maybe switch a light.

None of that needs an app. It needs a screen that's already there, already on, in a spot everyone walks past.

## The device that was already accepted

We already had an Echo Show 5 on the counter. Nobody had to be talked into using it. People read the time off it and tapped it without thinking. In a shared home, that kind of acceptance is harder to get than any feature.

So instead of adding another device, I changed what this one does. I flashed it with LineageOS, which replaces Amazon's software, and installed the companion app for [View Assist](https://github.com/dinki/View-Assist). Now it's a Home Assistant panel. Same device, same spot, a completely different screen.

## What's on it

The default screen is a clock you can read from across the room, with the weather and the next appointments underneath. The background color shifts with the time of day. Most of the time that's all anyone needs from it, and nobody has to touch anything.

When the Reolink detects a person, a banner appears on that clock screen. Tapping it opens the live stream, with a button for the floodlight next to it.

A bar on the right holds five icons: home, camera, music, lights, calendar. The music page controls the Sonos speakers, one room or several, with large volume buttons and the next songs in the queue. The calendar page shows the week from the shared iCloud calendars.

After a short while without a touch, the panel goes back to the clock on its own.

## Four rules I'd apply to any panel

**The idle screen has to be worth a glance.** If the panel only becomes useful once you start tapping, it's just another app on a stand.

**Everything sits one tap away from the clock.** Anything that needs a second level of navigation is something only I will use. That belongs in the regular Home Assistant dashboard, not on the panel.

**No settings, no entity names, no status pages.** When something breaks, I fix it from my laptop. The panel doesn't need to explain itself.

**It always returns home.** Whoever walks by next shouldn't find a music page someone left open an hour ago.

## What it costs

Flashing only works on specific Echo Show models and firmware versions. It takes a few evenings, and if something goes wrong the device may not boot again. On top of that, View Assist and the custom cards I use mean a fair amount of YAML.

All of that lands on one person, once. Everyone else gets a screen that just works. That's the trade I wanted.

## Next

The full setup goes in the next post: flashing, View Assist, every integration, every card, and the places I got stuck.

In the meantime I've been turning the YAML part into something less painful. [PanelKit](https://github.com/ma-2a/panelkit) is a visual editor for View Assist dashboards: pick your screen, lay out the grid, drop in your cards, copy the result. You can [try the builder here](https://ma-2a.github.io/panelkit/builder/).
