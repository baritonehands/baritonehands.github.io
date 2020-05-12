---
layout: post
title:  "My Remote Board Game Video Rig"
date:   2020-05-11 17:00:00-0500
permalink: remote-board-game-video-rig
categories: [jitsi, zoom, board games]
---

I've been occupying much of my time during quarantine with tabletop gaming. I
quickly became obsessed with making it work, and was able to scrape together the
components so I can continue to enjoy my sizable physical board game collection.

## Choosing a Game

When it comes to picking a game for remote play, it really comes down to public
vs private information. Any game that has private information is going to be
difficult to convey in a shared video chat session. Any game that requires
large amounts of individual board management or reading of cards would be difficult
as well.

So mostly I've been playing cooperative games that are easily managed by me, or
where the card list is available online. Surprisingly, I do have a decent amount
of games that fit that criteria.

### Games I Have Tried

Here is a list of all the games and some notes about what works and what doesn't:

* [Mansions of Madness](https://boardgamegeek.com/boardgame/205059/mansions-madness-second-edition) (2nd Edition)
  * Cooperative
  * Large amount of text and cards, but all are available online
  * Companion app is easy to stream from my machine via the video compositor software
  * Companion app allows saving the game to continue in a future session
  * Only the "Insane" condition has hidden information, which we chose to ignore
* [Star Wars: Imperial Assault](https://boardgamegeek.com/boardgame/164153/star-wars-imperial-assault)
  * Cooperative
  * Large amount of text and cards, but board state doesn't change often so a single
high quality photo is good for each player
  * [Fandom Wiki](https://imperial-assault.fandom.com/wiki/Imperial_Assault_Wiki)
has all the cards for viewing
  * Companion app for streaming and saving games for later
  * It worked but my friend said it wasn't very fun over video
  * I have not attempted the normal setup with dedicated imperial player
  * Only imperial player (or app) has hidden information
  * It is also good for solo play
* [Alien Frontiers](https://boardgamegeek.com/boardgame/48726/alien-frontiers)
  * Competitive
  * Small amount of text on powers and cards, [available online](https://www.ultraboardgames.com/alien-frontiers/index.php)
  * Good option, 90-120 min play time
* [Tiny Epic Defenders](https://boardgamegeek.com/boardgame/155708/tiny-epic-defenders)
  * Cooperative
  * No hidden information
  * Small amount of text on cards, but mostly unchanging. Hi-res photo will suffice.
  * Shorter play time (< 60 min for experienced players)

### Games I Plan to Try

These games should work, just haven't had the opportunity to try them:

* [Castles of Burgundy](https://boardgamegeek.com/boardgame/84876/castles-burgundy){:target="_blank"}
  * Competitive
  * Similar mechanics to Alien Frontiers
  * Very little text on the board, all of it is in the manual
* [Tiny Epic Kingdoms](https://boardgamegeek.com/boardgame/148951/tiny-epic-kingdoms){:target="_blank"}
  * Competitive
  * All the Tiny Epic games are similar in design, likely to work well
  * No hidden information
  * Small amount of text on cards, unchanging, requiring a hi-res photo
  * Shorter play time
* [Burgle Bros.](https://boardgamegeek.com/boardgame/172081/burgle-bros){:target="_blank"}
  * Cooperative
  * No hidden information
  * Little text or changing board state
  * Shorter play time
* [Pandemic](https://boardgamegeek.com/boardgame/161936/pandemic-legacy-season-1){:target="_blank"} (Original/Legacy/Expansions)
  * Cooperative
  * No hidden information
  * Little text, not critical for players to read
  * Shorter play time
* [Forbidden Island](https://boardgamegeek.com/boardgame/65244/forbidden-island){:target="_blank"} (or Desert, or Sky)
  * Cooperative
  * No hidden information
  * Little text, not critical for players to read
  * Short-medium play time (varies between Island/Desert/Sky)

## The Video Rig

Setting up the video is the most challenging part of this, requiring several
cameras and special software to composite all of them into one feed. It was
an additional challenge during quarantine due to webcams being sold out at many
online retailers. I had to be creative to work it at short notice.

### Traditional Webcam

If you have one or two lying around, decent quality will suffice. Anything over 720p
is good enough for low detail shots like an overhead shot of the board. Small text
or elements are hard to make out, but are probably not important.

### Current or Old Smartphone

I was forced to use these simply because I had them lying around. I have a recent
iPhone (XR) and a 4-5 year old Android (Galaxy S7 Edge). Both need to be mounted
overhead and connect to the video compositor software.

* iPhone XR
  * [EpocCam App](https://apps.apple.com/us/app/epoccam-webcamera-for-computer/id435355256){:target="_blank"}
for using the phone as a webcam
  * Connects via WiFi, USB, or NDI (requires additional PC/Mac free app)
  * 1080p quality (free version only supports 640x480 and WiFi)
* Galaxy S7 Edge
  * [EpocCam App](https://play.google.com/store/apps/details?id=com.kinoni.webcampro){:target="_blank"}
  * Connects via WiFi only
  * 1080p quality (free version only supports 640x480)

#### Mounting the Phones

I had to be creative here as well. I bought a small flexible phone mount, but
ultimately to get the height and angle I had to build my own hacky rig.

Some options:
* [AMS Universal Cell Phone Holder](https://www.amazon.com/gp/product/B01CXRBNYY/ref=ppx_yo_dt_b_asin_title_o06_s00?ie=UTF8&psc=1){:target="_blank"}
  * Pretty wobbly
  * I clipped to a standard camera tripod for height
* Selfie Stick
  * Mine was free swag from a tech conference
  * Used a small clamp to fix to a stepstool sitting on my table (yes for real!)
* Camera Tripod
  * Mine is a standard camera tripod I had lying around
  * Approx. 5 feet maximum height

Ultimately you will have to find something that works for you and your space.

<img alt="Clamp Rig" src="/assets/video-rig/clamps.jpeg" class="screenshot" />
<img alt="Tripod Rig" src="/assets/video-rig/tripod.jpeg" class="screenshot vertical" />

### Video Mixing

To mix all the video sources together into a single stream, I'm using [OBS](https://obsproject.com/){:target="_blank"}.
It supports Windows and macOS, and has many plugins to do all sorts of advanced
operations. The feature I care about is mixing together video capture devices
as well as application windows. I also needed [NDI Studio Monitor](https://ndi.tv/tools/){:target="_blank"}
for the iPhone source.

Here's how I have mine set up on my 13-inch 2018 MacBook Pro:

#### Apps to Install

* [OBS](https://obsproject.com/){:target="_blank"}
* [Kinoni macOS Drivers](https://www.kinoni.com/){:target="_blank"} (requires restart)
* [NDI Studio Monitor](https://ndi.tv/tools/){:target="_blank"} (only if you have two smartphone sources)
* [iOS EpocCam App](https://apps.apple.com/us/app/epoccam-webcamera-for-computer/id435355256){:target="_blank"} and/or [Android EpocCam App](https://play.google.com/store/apps/details?id=com.kinoni.webcampro){:target="_blank"}

#### OBS Setup

The first time you start OBS, it'll run a setup wizard. I chose these settings:

* Optimize for recording
* Base canvas: 1280x720, FPS: 30 (Balance between resolution and bandwidth)
* Then it will test the settings and you can click Apply

#### Add Sources

Click the + button under "Sources" in OBS.

* First smartphone (Android for me):
  * EpocCam App: No special config, just running. I had to have OBS open for it to connect.
  * OBS Sources: Video Capture Device -> EpocCam (Preset 1280x720)
* Second smartphone (only iOS app can use NDI):
  * EpocCam App: Connection method: NDI, 1280x720 (only one source can use WiFi/USB)
  * NDI Video Monitor: File -> iPhone -> EpocCam
  * OBS Sources: Window Capture -> [NDI Video Monitor] iPhone (EpocCam)
* Companion app (if needed):
  * Steam: Run companion app in windowed mode, at a resolution that will fit on your screen
  * OBS Sources: Window Capture -> Name of app window (might have empty name,
and require you to click that checkbox)
* Your laptop camera:
  * OBS Sources: Video Capture Device -> FaceTime HD Camera
  * Any additional webcams can also be added this way

Then you'll have to resize each of the sources so they fit in the frame. This
will largely depend on camera positioning and visibility of the game. You can
also rotate and adjust the frame of each source, for example if one camera was
oriented horizontally when it should be vertical, or 180 if it's upside down.

Play around with it a bit, there's lots of things you can do, including adding
Scenes for transitioning between different views.

#### Share Screen

In your video chat software, all you need to do is share your screen, and pick
the OBS preview window.

To open OBS Preview:

* Click anywhere off to the left or right side in OBS to deselect your sources
* Ctrl-Click (or two finger click) and select "Windowed Projector (Preview)"
* Opt-Click the green button to maximize the preview window
* Select that window to share in your video chat software

## The Final Result

<img alt="Mansions of Madness" src="/assets/video-rig/mansions-of-madness.png" class="screenshot" />
<img alt="Imperial Assault" src="/assets/video-rig/imperial-assault.png" class="screenshot" />

Stay healthy and play some games!
