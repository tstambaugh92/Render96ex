# Please note this is mostly not my work

This is Render96ex alpha (which seems to have the 60fps patch already applied) with Extended.Moveset.v1.04a.Render96.patch also applied.

The only reason I'm uploading this is I had to un-patch some code in camera.c because it broke changing the camera to Mario's view when hitting R. I'm sure they had a reason for this but I don't like it and want this ready to go in the future if I need to redownload.

My make command:
make BETTERCAMERA=1 EXTERNAL_DATA=1 NODRAWINGDISTANCE=1 TEXTURE_FIX=1 EXT_OPTIONS_MENU=1 DISCORDRPC=1 -j$(nproc)

All other Render96ex instruction follow.

# Extended Moveset for SM64

This is a mod for Super Mario 64 that attempts to add various new moves for Mario from games like Sunshine and Odyssey without replacing any existing ones. The aim is for to have each addition be balanced, natural, fitting, and (most of all) fun to use. Many of these changes were inspired by (and in some cases direct recreations of) Kaze's moveset changes for Super Mario Odyssey 64 and Super Mario 64 Land, but there's some new stuff here too.

## Changes

* **Wall Slide** ([video](https://imgur.com/zBjdMZN)) - Works much like Sunshine. Your reflected angle going at the wall is maintained after jumping off, and firsties are still possible. Going at the wall too fast (e.g. by doing a long jump) will bonk, but you still have the opportunity to do the old-style wall kick input during it. It's like a skill check for those trying to wall jump with a lot of momentum.
* **Dive Hop** ([video](https://imgur.com/07gii0H)) - Taken from Sunshine (uses the same Y-speed values too!). Done by pressing B while belly sliding.
* **Ground Pound Dive** ([video](https://imgur.com/QQTZMSa)) - Taken from Odyssey. Press B while in ground pound to do a somewhat slow dive with a bit of height. This move was also added in Kaze's hacks, but I was never a fan of the fact that it put you at full speed - it obsoleted the normal dive almost entirely. Now its clear use is to get that last-ditch bit of height/distance.
* **Ground Pound Jump** ([video](https://imgur.com/xTkY8FH)) - Taken from Odyssey. Jumping just after landing from a ground pound will do a straight-up jump with a height between a backflip/sideflip and a triple jump.
* **Roll** ([video](https://imgur.com/letp7qt)) - Taken from Odyssey, trying to be as close to it as possible. You can enter it by crouching and pressing R. You can gain speed by repeatedly pressing R (star particles indicate a speedup). You can also enter it by holding crouch (Z) before landing after long jump or dive. Additionally, pressing R just after landing from a ground pound will start a roll with a great amount of speed. During the roll, you can press A to cancel into a long jump or B to cancel into a dive recover. Letting go of R will also cancel the roll after a short lockout period (which won't occur if you accidentally triggered roll from long jump or dive for a couple frames). Cancelling this way will lift your firm speed cap slightly until you switch actions (explained further below).
* **Spin Jump** ([video](https://imgur.com/tz71HgT)) - Taken from Sunshine. The way gravity works should be to-the-numbers accurate, but it goes as high as a ground pound jump. Perform it by rotating the control stick a little more than half a circle, then jumping. Remember that you can choose the direction you want to face after the jump just before pressing A. You can also turn almost any jump into a spin jump after the fact by doing a spin input. You cannot grab ledges during it.
* **Spin Pound** ([video](https://imgur.com/ysYiMTw)) - Adapted from Odyssey. Simply press Z during a spin jump. You'll immediately plummet down much like a normal ground pound. When you land, you'll face the direction you're holding with the analog stick. You can do this very quickly after spin jumping, and you can roll after landing just like a normal ground pound... Meaning yes, you can [bump](https://smo-speedrun.fandom.com/wiki/Spinpound) like you're doing an Odyssey speedrun!
* **Underwater Ground Pound (+ Stroke and Jump)** ([video](https://imgur.com/tgaRiM6)) - Taken from Odyssey. You can now do a ground pound underwater! This helps you descend into the depths faster. Additionally, if you press A during it, you'll do a stroke straight forward that's decently quick. If you land the ground pound underwater, pressing A will do an underwater ground pound jump. Ground pounding into water will now carry into the underwater version, and ground pound jumping underwater to the surface will carry into a jump out of the water.
* **Ledge Parkour** ([video](https://imgur.com/4C563j2)) - Adapted from Super Mario Run (of all places). When grabbing ledge when going at least full walking speed, pressing B within a 3 frame window will vault you over the ledge. It'll maintain your speed prior to grabbing ledge and give you a little bit more as well. If the level geometry was a perfectly-made set of stairs, you could continually parkour over each ledge, accumulating ludicrious speed in the process...
* **Modified Tight Controls Patch** ([video](https://imgur.com/67xK6i3)) - The Tight Controls patch by Keanine is a great idea - being able to easily change directions without doing awkward half/circles is a great idea. However, with this patch, if you're on the ground with a lot of backwards speed, pressing back will change your direction, but you'll still be going backwards in that new direction. This looks and feels very strange, so I've modified it to also convert your speed into forward speed when changing directions due to Tight Controls. Additonally, since it feels a little limiting to have a bunch of speed only for it to be limited by the hard walking speed cap, I've decided to significantly raise that hard cap and also turn the old cap into a "firm" cap. Over that "firm" cap, you'll lose speed twice as fast normal. Doing this maintains a bit of that feeling of riding the insane momentum backwards from a slope in vanilla while still getting the benefits of a more responsive normal control.

[(Gallery containing all videos from above)](https://imgur.com/a/kuPPS9V)

## Installation:

### PC Port

Just apply the `.patch` file from the Releases page in this repo like so:

```sh
git apply --reject --ignore-whitespace "Extended Moveset.patch"
```

Then recompile:

```sh
make -j16       # if your CPU has 16 cores
```

### N64 ROM

Apply the `.xdelta` patch from the Releases page in this repo onto a clean SM64 ROM using your favorite Xdelta patcher (e.g. some online one like [this one](https://hack64.net/tools/patcher.php) or [this one](https://www.marcrobledo.com/RomPatcher.js/)).

If you have any bug reports, suggestions, etc. Please feel to let me know! Thanks for trying out the mod!

Original README begins below:

# Render96ex
Fork of [sm64ex](https://github.com/sm64pc/sm64ex)

Check the wiki out on how to build and some [developer notes](https://github.com/Render96/Render96ex/wiki)

This is meant to be a fork where the team can upload their code.
If you want to help sm64ex then go to their repo. 
If you want to help us out then message me on discord DorfDork#4516
