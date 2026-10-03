---
title: "Jailbreak an old Echo Show: a €30 Home Assistant panel without Amazon's ads"
description: Which Echo Show models can be jailbroken, what they cost secondhand, how the LineageOS jailbreak works, and why I'd rather flash one than live with Amazon's ads.
category: home-assistant
tags: [echo-show, echo-show-5, echo-show-8, jailbreak, lineageos, view-assist, home-assistant, wall-panel]
project: panelkit
---

There are two Echo Shows in my house: an Echo Show 5 and a first-gen Echo Show 8. Neither runs Amazon's software anymore. Both are flashed with LineageOS and work as Home Assistant panels through [View Assist](https://github.com/dinki/View-Assist), the 8 with the View Assist Companion App (VACA).

If you run Home Assistant and want a panel somewhere in the house, I think an old Echo Show is currently the best deal out there. This post covers why, which models you can actually use, and where to find the guides I followed.

**Short version:** Three Echo Show models can be unlocked and flashed with LineageOS: the Echo Show 5 (1st and 2nd gen) and the first-gen Echo Show 8. I paid €30 and €35 for mine, secondhand. The jailbreak took me about an hour and a half the first time and under 30 minutes the second. Afterwards the device runs as a Home Assistant panel with View Assist, with no Amazon software and no ads.

## Where this started

I didn't figure any of this out myself. The jailbreak comes from [Rortiz2](https://xdaforums.com/f/amazon-echo.6148/) on the XDA forums, who found a way to unlock the bootloader on several older Echo devices in late 2025. The LineageOS builds for them come from bengris32, also on XDA.

Two videos got me to actually try it. Dammit Jeff's [Why you NEED to Jailbreak your Amazon Echo](https://www.youtube.com/watch?v=h0-MlJ38BXw), where he unlocks a first-gen Echo Show 8, puts LineageOS on it and runs Home Assistant. And Mark Watt Tech's [full walkthrough for the Echo Show 5](https://www.youtube.com/watch?v=5CCRIzcgKuM).

## Why buy an old Echo Show? Reason 1: they're cheap

Echo Shows were sold in huge numbers, and plenty of them now sit in drawers. Some people upgraded, some got tired of Alexa, some got tired of the ads (more on that below). The result is that older models are all over eBay and the usual classifieds.

I paid €30 for my Echo Show 5 and €35 for the Echo Show 8, both secondhand from eBay and local classifieds. Prices move, so check the sold listings for the exact model and generation before you buy, but that's roughly the range to aim for.

## Reason 2: the hardware is made for this job

Strip away the software and an Echo Show is an Android device built to do exactly what a wall or counter panel needs to do. A touchscreen designed to be read from across a room and tapped in passing. Decent speakers and microphones. A stand that's part of the case. A power supply instead of a battery, so it can run all day, every day, without anything swelling or wearing out.

Compare that with the usual alternative, an old tablet on a stand with a cable hanging out of it, and the Echo Show simply looks like it belongs in a home.

It's not a powerful device, though. The first-gen Echo Show 8 has a MediaTek MT8163, 1 GB of RAM and 8 GB of storage. That's enough for a clean dashboard, a clock, controls and a camera stream. It's not enough for heavy visual effects or a dashboard with forty cards on it. Keep things simple and it runs fine.

## Reason 3: getting away from the ads

This is the one that annoys me most.

Echo Shows show sponsored content on the home screen, and you can't switch it off. On Amazon's own forum, a staff member told a customer in 2024 that sponsored content cannot be removed from the Echo Show. In October 2025 it got noticeably worse: [owners reported full-screen ads](https://www.ghacks.net/2025/10/13/amazons-echo-show-devices-are-displaying-full-screen-ads/) between their photos and content cards, still with no opt-out. Amazon's position is that you can swipe past them or leave feedback.

With Kindles, Amazon at least sells versions without ads, for more money. For the Echo Show there isn't even that.

I don't think the Kindle model is acceptable either. I already pay a good amount of money for a device like this, and with that I've bought it. It's mine. Paying extra on top, just so the company that made it stops deciding what shows up on my screen, gets it backwards. Once I've bought a device, the manufacturer shouldn't control what's on it at all. Flashing is the only way I've found to get that control back.

## Which Echo Show models can be jailbroken?

This is the most important part of the post, because only a few models can be unlocked:

- **Echo Show 5, 1st gen (2019)**, codename *checkers*
- **Echo Show 5, 2nd gen (2021)**, codename *cronos*
- **Echo Show 8, 1st gen (2019)**, codename *crown*

The **Echo Show 8 2nd gen does not work.** It uses a different chip that isn't vulnerable to the exploit. Anything newer, or anything not on this list, assume it won't work either.

When buying secondhand, listings often don't mention the generation. One way to tell: the 2021 refresh came with better cameras, 2 MP on the Echo Show 5 2nd gen and 13 MP on the Echo Show 8 2nd gen. If a listing for an Echo Show 8 mentions 13 MP, that's the one you don't want. When in doubt, ask the seller for the model number or a photo of the label.

## How does the Echo Show jailbreak work?

I'm not going to rewrite the guides here. They are maintained by the people who built this, and they get updated when something changes. But here's the shape of it, so you know what you're getting into:

1. **Unlock the bootloader.** Rortiz2's tool for this is called amonet. You download the release for your exact model, put the device into a special boot mode, and run the script from a computer over USB. This step also installs TWRP, a custom recovery.
2. **Flash LineageOS.** LineageOS 18.1 (Android 11) gets installed through TWRP. After this, nothing from Amazon is left on the device.
3. **Set up View Assist.** Install the companion app on the Echo Show and the View Assist integration in Home Assistant. From then on, everything is configured from Home Assistant, not on the device.

One detail from the unlock thread that's worth knowing: once the device is unlocked and TWRP is installed, Amazon can't undo it with an update, because TWRP protects the partitions the exploit depends on.

## What are the risks?

You can brick the device. The guides are explicit that interrupting certain steps will permanently brick it, and they ask you to read the whole thing before you start. Do that. Twice.

The LineageOS builds are unofficial, and early builds had known issues with things like audio, Bluetooth and sensors. Read the release notes in the ROM thread for your model before you decide what you want to use the device for.

And it takes time. The first device took me about an hour and a half. The second one was done in just under 30 minutes.

## Guides and links

The XDA threads, one per model. These are the actual guides:

- [Echo Show 5 1st gen (checkers)](https://xdaforums.com/t/unlock-root-twrp-unbrick-amazon-echo-show-5-1st-gen-2019-checkers.4762900/)
- [Echo Show 5 2nd gen (cronos)](https://xdaforums.com/t/unlock-root-twrp-unbrick-amazon-echo-show-5-2nd-gen-2021-cronos.4772596/)
- [Echo Show 8 1st gen (crown)](https://xdaforums.com/t/unlock-root-twrp-unbrick-amazon-echo-show-8-1st-gen-2019-crown.4766687/)

The LineageOS builds have their own threads, for example [LineageOS 18.1 for the Echo Show 5 1st gen](https://xdaforums.com/t/rom-unofficial-11-checkers-lineageos-18-1-for-the-amazon-echo-show-5-2019.4763475/). The [Amazon Echo section on XDA](https://xdaforums.com/f/amazon-echo.6148/) has all of them in one place.

The videos that got me started:

- [Why you NEED to Jailbreak your Amazon Echo](https://www.youtube.com/watch?v=h0-MlJ38BXw) by Dammit Jeff
- [Echo Show 5 walkthrough](https://www.youtube.com/watch?v=5CCRIzcgKuM) by Mark Watt Tech

Further reading:

- [Hackaday on Dammit Jeff's Echo Show 8 build](https://hackaday.com/2026/01/02/jailbreaking-the-amazon-echo-show/)
- [A detailed Echo Show 8 write-up with VACA and View Assist](https://localsmarthomeguide.com/articles/echo-show-8-lineageos-home-assistant-voice-satellite/) from Local Smart Home Guide
- [View Assist on GitHub](https://github.com/dinki/View-Assist)

## FAQ

### Can you turn off the ads on an Echo Show without jailbreaking it?

No. Amazon's own support says sponsored content can't be removed. You can swipe past an ad or leave feedback, and that's it.

### Does Alexa still work after the jailbreak?

Not with LineageOS. It replaces Fire OS completely, so Alexa and every other Amazon service are gone. The XDA guides also describe keeping Fire OS with root access, but I haven't tried that route.

### Can Amazon undo the jailbreak with an update?

According to the unlock thread, no. Once the device is unlocked and TWRP is installed, the partitions the exploit depends on can't be overwritten by an update.

### Can I brick my Echo Show?

Yes. Interrupting the process at certain steps will permanently brick the device. Read the guide for your exact model completely before you start.

### What do I need besides the Echo Show?

A computer with a USB connection to run the unlock script, a running Home Assistant instance, and the View Assist integration installed in Home Assistant.

## More

If you want to know what the result looks like in daily use, I wrote about that in [Democratizing the smart home](/blog/democratizing-the-smart-home/). And if you'd rather click your View Assist dashboard together than write the YAML by hand, that's what [PanelKit](https://ma-2a.github.io/panelkit/builder/) is for.
