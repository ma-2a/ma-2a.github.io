---
title: My smart home had exactly one user. Me.
description: Why the smartest thing I added to my Home Assistant setup was an old smart display that anyone in the house can use without an app.
category: smart-home-for-everyone
tags: [home-assistant, view-assist, wall-panel, family-friendly]
project: panelkit
---

I had automated everything. Cameras with person detection. Multi-room audio. Lights, calendars, sensors, scripts. Months of work.

And the other adult in this house had not installed a single app for any of it.

To be clear: that was not their failure. It was mine.

## The part we don't talk about

We build smart homes for ourselves. Five apps, three dashboards, one automation that only works if you know to flip the other switch first. We call it a hobby, so the complexity feels like a feature.

For everyone else in the house, that same complexity is a door that stays shut.

My toughest user doesn't want to know what an entity ID is. They want to know who's at the door, put music on in the kitchen, and see what's happening today. That's the entire feature request.

Every extra step between them and those three things is a step where the system fails.

## A smart home isn't smart until everyone can use it

That's the whole idea behind what I'd call democratizing the smart home, and it has nothing to do with open standards or cheap hardware.

It's this: the complexity belongs to the person who enjoys it. Everyone else gets a surface they never have to think about.

If your household needs a tutorial, you didn't build a smart home. You built a hobby with a thermostat attached.

## Why an old smart display turned out to be the answer

The solution was already sitting in millions of kitchens: a small smart display.

Think about why these things got adopted in the first place. They sit on a counter. They show the time. You glance at them. You tap them. Nobody needs onboarding for a clock.

No app to install. No login to remember. No "where did you put the icon again?" It's furniture that happens to be useful.

Used ones go for very little, because plenty of people have one sitting in a drawer.

The twist: there's no voice assistant from the manufacturer on mine anymore. I flashed it with LineageOS and run it as a Home Assistant panel through [View Assist](https://github.com/dinki/View-Assist). Familiar hardware, my interface, everything local.

## What it actually does now

At rest it shows a large clock, the weather, and the next few things on the calendar. Useful without being touched, which is most of the time.

When the outdoor camera detects a person, a small banner appears on that same screen. One tap opens the live view.

Down the right edge there are five icons: home, camera, music, lights, calendar. Every function is exactly one tap away. After a while, everything returns to the clock by itself.

No menus. No settings. Nothing you can break by poking at it.

Here's how you know it worked: nobody talks about it. Nobody comments on a thing that just works. That silence is the whole point.

## Four rules I'd keep for any panel

**One device, one fixed place.** The value comes from never having to look for it.

**The idle screen has to be useful on its own.** If you only get value by touching it, you've built an app, not a panel.

**Nothing is more than one tap away.** The moment there's a second level of navigation, you've lost everyone but yourself.

**Hide everything that isn't a daily need.** No configuration, no diagnostics, no entity names. The nerd surface lives somewhere else.

## The honest part

Flashing a smart display isn't for everyone. It only works on specific models and firmware versions, it takes a few evenings, and if it goes wrong you have an expensive paperweight. There's no gentle way to say that.

But it's a one-time cost paid by one person. Everyone else just gets a screen that works, every day.

That trade is the best one in my entire setup.

## What's next

I'm putting what I built into the open. [PanelKit](https://github.com/ma-2a/panelkit) is a visual editor for View Assist dashboards: pick your screen, lay out the grid, drop in your cards, copy the YAML. You can [try the builder here](https://ma-2a.github.io/panelkit/builder/).

The full build, step by step, from flashing the device to the last bit of polish, is coming in the next post.
