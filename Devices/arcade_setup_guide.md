
# ARCADE MACHINE SETUP GUIDE

By: Sumeet Singh @ sumeet-singh.com

Updated: August 2024

Description: This free document outlines various ways to repair, build, modify, and setup with emulators/retro games various arcade machine cabinets.

Disclaimer: I do not condone piracy nor performing any activity that renders breaking a EULA or Terms and conditions contract between a product vendor
and customer. I recommend to buy official licensed games and hardware and dump the software yourself.

# TABLE OF CONTENTS
- [1. Understanding Screen sizes](#understanding-screen-sizes)
- [2. Repairing Arcade machines](#repairing-arcade-machines)
- [3. Building Arcade machines](#building-arcade-machines)
- [4. Modifying Arcade1UP machines](#modifying-arcade1up-machines)
- [5. Retroarch Install Steps](#retroarch-install-steps)
- [6. MAME Retroarch Setup](#mame-retroarch-setup)
- [7. Retroarch Configuration](#retroarch-configuration)
- [8. Launchbox Frontend Setup](#launchbox-frontend-setup)
- [9. Selling Arcade machines](#selling-arcade-machines)
- [10. Credits](#credits)

# UNDERSTANDING SCREEN SIZES

## CRT VS MODERN TV e.g, LCD/LED/PLASMA

Many people choose to use older CRT (Cathode Ray Tube) style TV's to use in Arcade machines to get an authentic retro gaming experience.
Thus many people option for buying and installing a CRT TV. Although fun CRT TV's are not commercially viable and what parts exist
are usually heavy, expensive, rare and difficult to repair. Regardless the emulator software's dont care what screen you use so if you 
don't want the hastle of dealing with an old CRT TV theirs nothing wrong with using a modern style Flatscreen TV. Note the build guides below
have optional schematics for CRT retro style cabinets and modern flatscreen style.

Choose whichever CRT or LCD cabinet you prefer. Note CRT cabinets are bigger as they are meant to hold
the weight of the CRT TV and in general use older Retro style cabinets, whereas Flatscreen uses more flatscreen style.

For the most authentic retro arcade cabinet results you would generally want a "4:3 aspect ratio Composite input TV". More info on
what those terms mean are below;

For reference a TV or Monitor in general refer to the same technology, though in reality each has small differences such as latency, delay, 
performance or apps, such as when watching a sport game on TV and seeing a ball get kicked on high latency/delay devices the ball will be blurred.
During this guide when talking about a TV in general it will refer to the same type of Monitor technology also. E.g, CRT TV = CRT Monitor.

## EXAMPLE CRT VS MODERN TV GAME

The following shows both the left CRT image and the right perfect pixel image
https://www.reddit.com/r/crtgaming/comments/owdtpu/thats_why_crt_is_unbeatable_crt_vs_pixel_perfect/

## OLED

In OLED monitors the LED to control that pixel turns off when the image is meant to display black. Thus it's a true black representation.
e.g, if you are watching a movie about space and seeing the sky, the stars will be light up by the OLED display but the blackness of space
will have the LED pixels turns off showing darkness. Thus OLED is a modern energy efficient, true display representation display technology.

## TV INPUTS

When wanting to connect a device to an CRT TV monitor to output video (or even use the TV or Monitors Speakers) you will need to connect
to the TV's inputs.

CRT TV/Monitors from the last decades of production generally supported the following input technologies

Composite (3 cables) = White (Left/Mono Audio), Red (Right Audio) and Yellow (Video)
Component (5 cables) = Red, Blue, Green (Video cables) and Green, Blue (Audio cables)
Scart = Big connector

In general most 20th centure retro game consoles use composite cables. As long as you connect your device with an adapter or propriety
cable to a CRT TV's with Yellow cable you can view video output. If you're device such as your using for game emulation has it's own USB/3.5mm
headphone jack you can output the audio to that instead of the White and Red Mono/Stero audio output on the TV.

Mono Audio refers to sound coming out of all a TV's speakers in one direction, whereas Stero audio refers to Audio coming out from either Left
or Right (or more if you have a surround sound speaker setup such as in a Movie Theatre) directions. This is more immersive but not strictly 
necessary as retro games don't usually have stero audio and it wont cause gameplay issues playing only mono audio.

## ASPECT RATION & RESOLUTIONS

Aspect ratio & resolution refer to the field in which you view something. A 1:1 aspect ratio means a square field, whereas a 16:9 field
is a rectangular viewing field. On larger and wider Monitors that handle higher aspect ratios such as 16:9 with higher resolutions 1920 x 1080p 
you can view lower aspect ratio and resolution content within it causing black bars to appear in the unused spaces.

Resolutions are a number representation of a viewing angles pixels width and height which maintain the specified aspect ratio 
by keeping the width and height proportional. Thus a aspect ratio of 1:1 square has a pixel width and height equal as it's a square
e.g, 5000 w by 5000 h or 500 w by 500h thus the aspect ratio of 4:3 supports any resolutions that are squares.

For example a Widescreen Modern (16:9) with 1920x1080 resolution playing a game in 4:3 800x600 resolution. The sides are unused.

+------------+--------------+------------+ 
| +-----------+------------+-----------+ |
| |           |            |           | |
| |           |   Hello    |           | |
| |           |   World    |           | |
| |           |            |           | |
| +-----------+------------+-----------+ |
+------------+--------------+------------+
                   | |
                   | |
                 __+_+__


Why this is important is because many old games were developed in the CRT TV era with 4:3 aspect ratio and squarish resolutions.
Playing any game developed in resolutions for 4:3 ratios in a bigger aspect ratio/resolution monitor causes the images to 
be stretched out. If you are emulating a game in a modern monitor with a high resolution this isn't an issue as it will add black bars on 
the side to compensate.

However when building an retro inspired arcade machine cabinet and wanting an authentic look you will usually be limited to using 4:3 monitors.
Often as this cannot be found you will find many companies subsitute with 5:4 more common newer models (such as Arcade1up reproductions)
however this can cause the game to be stretched. Note some arcade games prefer different orientations also such as Pacman/Galaga/Early arcade
titles being vertical 19" monitors.

This wont cause gameplay issues if using emulator software but is something to keep in mind. If building a retro style arcade machine 
use a 4:3 CRT TV monitor, and if building a modern style, pick the highest resolution as the emulation software will compensate by 
creating bars, or artwork to hide the unused portions of the viewing display while playing a game.


Common Aspect ratio & resolutions

Square (1:1)

640 x 640 pixels
720 x 720 pixels
1080 x 1080 pixels
+------------+
|            |
|            |
|            |
|            |
+------------+
+------------++------------+
     30cm          60cm

Arcade/CRT (4:3):

800 x 600 pixels (SVGA)
1024 x 768 pixels (XGA)
1280 x 960 pixels (SXGA-)
1400 x 1050 pixels (SXGA+)
+--------------+
|              |
|              |
|              |
|              |
+--------------+
+------------++------------+
     30cm          60cm

Updated (5:4):

1280 x 1024 pixels (SXGA)
1600 x 1280 pixels (UXGA-)
+----------------+
|                |
|                |
|                |
|                |
|                |
+----------------+
+------------++------------+
     30cm          60cm

Widescreen Modern (16:9):

1280 x 720 pixels (HD or 720p)
1920 x 1080 pixels (Full HD or 1080p)
2560 x 1440 pixels (QHD or 1440p)
3840 x 2160 pixels (4K UHD)
7680 x 4320 pixels (8K UHD)
+----------------------------------+
|                                  |
|                                  |
|                                  |
|                                  |
|                                  |
|                                  |
+----------------------------------+
+------------++------------+
     30cm          60cm

## DEGAUSSING CRT

Many TV's have inbuilt degaussers within them either from a setting option, or from turning on or off. For many extremely older style
CRT devices you will have to degauss which means fix the imperfections of the display when the TV is turned off such as odd colouring.

## DEAD VS STUCK PIXEL

On CRT monitors pixels often become stuck.

A Stuck pixel is a always on red, green, blue or white pixel that doesn't change when viewing different content. Restarting often or 
seeing if your TV/Monitor has inbuilt menu options for restarting can fix this issue.

On LED monitors a pixel can be stuck or dead.

A dead pixel appears as a black dot. The actual pixel is dead. Dead pixels cannot be repaired in most circumstances but can go away on
their own which can take any indefinite time e.f, from a few weeks to a lifetime.


# REPAIRING ARCADE MACHINES

Watch this 18 minute video that will teach the complete way to repair/restore an Arcade machine: https://www.youtube.com/watch?v=rZpSh59Qglw

REQUIREMENTS
* Borax (sodium tetraborate): For any water damage, apply a thick water/borax paste all over damaged area, dry overnight then sand.
* Acrylic Water-Based  Primer: 1st coat.
* Acrylic Latex Paint: 2nd coat.
* Waterproofing Sealent: 3rd coat.
* Vinyl (Artwork): 3rd coat.

## REPAIRING PIXELS

See SCREEN SIZES section for more information.


# BUILDING ARCADE MACHINES

Why collect, mod, or build arcade machines/cabinets? because they are fun and you learn lots of skills.

These steps outline how to build your own custom arcade machine from scratch either yourself or with a carpenters help
to cut the wood (machine) the parts so you can put together, as well as various ways to paint the cab. Once the cab is built
and all electronics added you can skip to the Retropie Setup steps to finally add retro game emulation on it

Benefits of building your own machine include being able to have 1 of each game type (e.g. Fighting, seated racing, or gun arcade cabinet)
that you can customise however you want.

If you feel this is too much effort you can always buy Arcade1UP arcade machines and use the below modding guide to customise.

NOTE: 
* Arcade joystick cables are called "2.8mm Terminal Quick Connects" arcade cables.
* Arcade button holes are 28mm diameter, as well as the buttons diameters, and for grommets etc.,

There are schematics here for many original authentic cabinets you can use to build your own here: https://www.classicarcadecabinets.com/

The steps below can be used to build any generic arcade cabinet but I've included schematics for a CRT, Flatscreen and racing simulation/cockpit
cabinet that you are free to print out, cut and use for simplicity sake. When you see steps for CRT/for Flatscreen mentioned
they are referring to the default designs below;

Remember either option you choose you can swivel the TV to face any angle or orientation you want. With CRT It's a matter of adding
wooden base in cabinet and with flatscreen you can swivel the VEGA bracket. Regardless if you choose a custom orientation it's
best to pair with a black cardboard/wood cutout and/or acrylic glass to match.

EXAMPLE BELOW

175cm, 27" flatscreen panel, PACMAN custom cabinet painted 1: sun yellow gloss, 2: black gloss, with diamond kickplate, and the coin buttons
replaced with 33mm wide (28mm internal diameter) grommet to cut and feed controller cables through also for charging phones.

      +--------------------------------+
      |    __   __   _  _  ____  ____  |
      |  _(  ) /  \ / )( \/ ___)(_  _) |
      | / \) \(  O )) \/ (\___ \  )(   |
      | \____/ \__/ \____/(____/ (__)  |
      +--------------------------------+
      |    /\                    /\    |
      |    \/                    \/    |
      |  +--------------------------+  |
      |  |                          |  |
      |  |                          |  |
      |  |                          |  |
      |  |                          |  |
      |  |                          |  |
      |  |                          |  |
      |  +--------------------------+  |
      |                                |
      |--------------------------------|
      |     O O              O O       |
      |       O O O            O O O   |
      |     X O O O          X O O O   |
      |--------------------------------|
      |                                |
      |                                |
      |--------------------------------|
      |                                |
      |                                |
      |                                |
      |         +------------+         |
      |         |  |      |  |         |
      |         |  _      _  |         |
      |         | |_|    |_| |         |
      |         +------------+         |
      |                                |
      |                                |
      |                                |
      |                                |
      |                                |
      |                                |
      |XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX|
      |XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX|
      |XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX|
      +--------------------------------+

## WOOD CHOICE

For anywhere remotely outdoor usage or with extreme tempratures, then "Marine Plywood" is the most water, humidity, rotting, cracking and warping resistant material.
It's made of many layers of waterproof glued together, and due to being made by humans is free from void when glueing and each board is wrapped
opposite grain the former so it's interlocked and strenghtened.

Timber is strong and heavy and costs more, but is quality material.

MDF is the cheapest and has it's use cases but is prone to weather damage.

## WOOD CUTTING SERVICES LOCATIONS

For Marrickville, Sydney, Australia see: https://lasercuts.com.au/laser-cutting/

## METHEDOLOGY

1. Cut 18mm wood with t-moulding (t-moulding will overhang on 16mm size cabinets) using schematics below.
Note: control panel top does need to be sanded once placed.
Note: For cutting control panel inputs for coin you can just skip and route cable to coin door, or cut holes on top of control panel alongside
player 1 and 2 buttons.
* For CRT cabinets: __________________________________________________________
schematics and images are in archive```/xxxxxxxxxxxxxxx```
FEATURES:
     * _____________________________________
     * _____________________________________
* For Flatscreen cabinets schematics and images are in archive ```/27inch-flatscreen-arcade-machine-plans.rar```
FEATURES:
     * 170cm tall
     * Supports Flatscreen tv up to 27"
3. Print vinyl
Common vinyl wraps and artwork for arcades are below

PACMAN: https://arcarc.xmission.com/Web%20Archives/Pac%20Man/Pacman%20Graphics/PACANAC.htm

4. Paint cabinet
Common paint codes are below

PACMAN

Option 1: Buy "Krylon sun yellow" spray paint or something similar
Option B: Codes are below;

#### Pacman color
This Paint was LOWES American Tradition/Interior Semi Gloss Latex

YELLOW
BASE:  B 4-40240
COLOR                    AMOUNT
103                            .5
104                          1.5
113                         20.5
114                         11Y25.5

RED
BASE : B 4-44975
COLOR                    AMOUNT
109                          1.5
113                            6
114                         42.5
116                         1Y45

BLUE
BASE : B 4-44975
COLOR                    AMOUNT
101                           2.5
102                         45.5
103                            17
113                         1Y29.5

5. Purchase adapters
For CRT cabinets: you will need to purchasea "HDMI to RCA Converter" or "HDMI to Scart" (If your TV supports the superior display quality SCART input on certain old CRT TV models) to plug into Raspberry Pi/PC.
6. Purchase light guns - buy "Sinden Light gun with recoil 2 packs" which work on any screen https://www.sindenshop.com/
7. 3D print the Sinden Lightgun holsters x 2 without the logo version from here https://www.printables.com/model/228065-sinden-lightgun-holster-for-arcade
8. Add screw on small standard rubber wheels to base for easy transport/moving arcade
9. Adjust CRT TV/Flatscreen orientation/angle to your liking
10. Optional - Add diamond tread kickplate to front, and possibly sides (this is the metal plate to prevent kicking damage to wood)
11. Add Marquee - print/cut out a marquee for your cabinet e.g, "Joust" then add LED wardrobe lights
12. Add t-moulding
13. Add joystick and buttons to encoder
14. Optional Add double coin door with mechanism with lights. if no lights are available you can buy addon lights e.g, https://www.retroblast.com/articles/coindoor.html additionally you will need to adjust the coin mechanism to accept your desired regions coins e.g, https://www.youtube.com/watch?v=09J4fO1yC8w
You will need to purchase a 30mm lock for the arcade which are often purchased alongside or just google search "30mm arcade coin door lock" and buy (with the key of course)
if adding a coin door, then you may want to add a "cable grommet" in place of an existing "coin" button, so you can use for an controller cable to play console
games e.g, Megadrive/Genesis controller.
15. Add speakers
16. Add TV
17. Cutout TV screen size from black thick paper/cardboard cutout to cover TV sides
18. Cut acrylic glass to match black cutout size to cover TV
19. Setup the computer with emulator following EMULATOR SETUP

### BUILDING SEATED RACING CABINET

1. Simplest option is to buy a "full motion racing cockpit simulator" by searching on Google e.g, https://dofreality.com/
2-axis is the cheapest and 6-axis full motion is the most expensive. Consider buying universal controls for Racing & Flying 
e.g, https://dofreality.com/product/universal/universal-motion-platform-6-axis-hero-h6/
2. Then add your TV, console/PC, connect it together using the EMULATOR SETUP
3. Get wood cut and ordered using the schematics here ____________________ and assemble
4. Print and place vinyl wrap

# MODIFYING ARCADE1UP MACHINES

If you have an existing Arcade1up cabinet the following steps outline the ways to improve the cosmetic and functional aspects of it.
Once the cab is built and all electronics added you can skip to the Retropie Setup steps to finally add retro game emulation on it

1. BUILD CUSTOM RISER

If the height of the Arcade1UP cabinets are too short you can increase with custom risers. The steps below outline different size comparisons
and different options depending on the generation/model of cabinets you have.

Size comparisons located in this file: /Arcade/Arcade1up-size-comparisons.jpg

3/4 cabs: varies (h)
Deluxe cab: 155cm (h)
XL cab: 165cm (h) + 3" wider

Both 3/4 and Deluxe cabinets share same length and width dimensions and fit same riser
https://www.reddit.com/r/Arcade1Up/comments/167qcsp/can_the_deluxe_cabinets_be_put_on_risers/ 
XL cabs are also authentic but they are huge. Deluxe provide the middle ground authentic footprint arcade experience.

FOR DELUXE CABINETS

OPTION A - Flush riser

Buy a flush riser then put metal diamond tread kickplates on all sides to prevent wear and tear
Cons are it will cause balance instability and exhuberate the rocking issue with these top heavy tall cabs (serious consideration)
Prepurchase: https://www.gijoelgaming.com/product/arcade1up-inline-riser
Example: https://www.youtube.com/watch?v=wlPyo3gw3MA

      +------------------------+
      |     MORTAL KOMBAT      |
      |                        |
      +------------------------+
      | +--------------------+ |
      | |                    | |
      | |                    | |
      | |                    | |
      | |                    | |
      | |                    | |
      | |                    | |
      | +--------------------+ |
      |                        |
      |------------------------|
      |   X O O O   X O O O    |
      |------------------------|
      |                        |
      |                        |
      |                        |
      |       +---------+      |
      |       |  |   |  |      |
      |       |  _   _  |      |
      |       | |_| |_| |      |
      |       +---------+      |
      |                        |
      |                        |
      |                        |
      |                        |
      |                        |
      |                        |     
      +------------------------+
      |    Flush Riser (4")    |
      |                        |
      +------------------------+

OPTION B - non flush riser

Buy a no flush riser then put metal diamond tread kickplates on all sides to prevent wear and tear, base adss stability.
Prepurchase: https://www.buystuffarcades.com/products/mini-riser-for-deluxe-arcade1up-cabs

      +------------------------+
      |     MORTAL KOMBAT      |
      |                        |
      +------------------------+
      | +--------------------+ |
      | |                    | |
      | |                    | |
      | |                    | |
      | |                    | |
      | |                    | |
      | |                    | |
      | +--------------------+ |
      |                        |
      |------------------------|
      |   X O O O   X O O O    |
      |------------------------|
      |                        |
      |                        |
      |                        |
      |       +---------+      |
      |       |  |   |  |      |
      |       |  _   _  |      |
      |       | |_| |_| |      |
      |       +---------+      |
      |                        |
      |                        |
      |                        |
      |                        |    
      |                        |
      |                        |
     +--------------------------+
     |   Metal Kickplate (4")   |
     |                          |
     +--------------------------+

FOR 3/4 CABINETS

As Arcade1up 3/4 cabinets are too short by 15cm (6") by personal testing and most reports 
https://www.reddit.com/r/Arcade1Up/comments/sdjj7n/even_with_riser_arcade_games_are_not_high_enough/ we then add that to the
custom riser measurements below to either extend the existing riser by 15cm or make a new riser for 49cm;

Aracde modder example dimensions - breakdown - https://www.reddit.com/r/Arcade1Up/comments/hql8o3/riser_specs/
4 x Outer panels 51cm (l) x 34cm (h)
2 x Inner panels 48cm (l) x 29cm (h)
2 x Weight bearing panels 48cm (l) x 5cm (w)

OPTION A - Buy Riser extender

Buy a riser extender (diamond kickplate pattern best) and use the dimensions

Prepurchase: https://www.buystuffarcades.com/products/riser-booster-for-arcade1up-arcades?variant=40523236540576
Example: https://www.youtube.com/watch?v=2bcejhZNyBA&lc=Ugzya6nEhq4Rz2VvC5F4AaABAg.A6OuP1Pj09KA6PBk7JDYHM

      +------------------------+
      |     MORTAL KOMBAT      |
      |                        |
      +------------------------+
      | +--------------------+ |
      | |                    | |
      | |                    | |
      | |                    | |
      | |                    | |
      | |                    | |
      | |                    | |
      | +--------------------+ |
      |                        |
      |------------------------|
      |   X O O O   X O O O    |
      |------------------------|
      |                        |
      |                        |
      |                        |
      |       +---------+      |
      |       |  |   |  |      |
      |       |  _   _  |      |
      |       | |_| |_| |      |
      |       +---------+      |
      |                        |
     +--------------------------+
     |                          |
     | Arcade1up Riser (13.25") |      
     |                          |
     |                          |     
     +--------------------------+
     |     Custom Riser (4")    |
     |                          |
     +--------------------------+

OPTION B: Build custom riser

Example here https://www.youtube.com/watch?v=B4P6Nuofftg

      +------------------------+
      |     MORTAL KOMBAT      |
      |                        |
      +------------------------+
      | +--------------------+ |
      | |                    | |
      | |                    | |
      | |                    | |
      | |                    | |
      | |                    | |
      | |                    | |
      | +--------------------+ |
      |                        |
      |------------------------|
      |   X O O O   X O O O    |
      |------------------------|
      |                        |
      |                        |
      |                        |
      |       +---------+      |
      |       |  |   |  |      |
      |       |  _   _  |      |
      |       | |_| |_| |      |
      |       +---------+      |
      |                        |
     +--------------------------+
     |                          |
     |   Custom Riser (13.25")  |      
     |                          |
     |                          |     
     +--------------------------+

2. ADD DIAMOND TREAD KICKPLATE
To protect the bottom of the arcade cabinet from being damaged from repeated kicks such as in commercial settings you can
tape or glue a metal sheet at the front following this example guide https://www.youtube.com/watch?v=Wf4RVx3Bs-o

3. HACK SOFTWARE TO ADD EMULATORS | ANY GAME
Arcade1up new cab models that have a MicroSD card slot have an Android Operating System.
The OS cab be customised so that you can install any application manually from SD Card (Not
from the Google Play Store as Google hasn't authorised any cab models to allow this functionality).
follow this guide to learn more https://www.youtube.com/watch?v=m1gkwDe9c7w

4. LIGHT UP COIN DOOR
https://www.youtube.com/watch?v=lsZ99HHl2U0

5. ADD REAL COIN DOOR
First purchase an "2.8mm Terminal Quick Connects split arcade cables" then follow this guide https://www.youtube.com/watch?v=kSyySSv1ywQ

6. ADD CUSTOM LIT MARQUEE

7. FIX LOW LEVEL SPEAKER STATIC
The static can be fixed, I bought a better quality 12v power supply off Amazon and a TRRS Male to Female Stereo Audio Jack Extender 
Aux Extension Adapter Cords with Volume Control. Its a pain that they have the gain too high off the PCB and a noisy power supply, 
this way I can turn the gain down manually and it lowers the noise floor. The other fix is the reroute the headphone jack which is 
line level out and connect the speakers to that but I wanted to be able to still use headphones. It is kinda weird / lazy that they
have not fixed an annoying problem that has a relatively cheap fix. - Youtube commenter @user-pi6cs3ue4s 
August 2024 https://www.youtube.com/watch?v=alf4X3mJsHQ

8. ADD LINK CABLE FOR MULTIPLAYER
https://www.buystuffarcades.com/products/ridge-racer-and-outrun-mod-kit

9. REPLACE JOYSTICK BUTTONS
You can choose to replace the stock cheap Arcade1up buttons on the non XL models with better products. You will need to buy
Sanwa style arcade buttons
1. Follow this to replace buttons - https://www.youtube.com/watch?v=09DQCOr6zQM

10. ADD BIGGER SCREEN
To add a different size monitor or TV to an existing Arcade1up cabinet such as increasing the screen size for shooter games
you need the below;
1 x Geekworm HDMI to LDVS 20 (a.k.a 2.0) adapter - https://geekworm.com/products/lvds-to-hdmi-adapter-board-converter-with-lvds-cable
1 x HDMI cable
1 x TV/Monitor
1 x VEGA bracket support frame
STEPS
a. Disconnect the Arcade1up PCB board from the stock monitor and connect to LDVS conveter in Channel 1
ensure the twisted ribbon style cable you connect has the dot on it's plastic seated in the same PCB dot reference (PIN 1)
Optionally, Seperate the board from the LCD with cardboard and double sided tape to prevent electrial shorting
b. add HDMI cable to LDVS and TV and turn on game and test. If flickering/drop outs occour then test with Channel 2 position
d. Once desired position is kept add the Wood/VEGA frame to Arcade cabinet and TV and connect all back together and test

11. COMPLETE BUILD GUIDE - RASPBERRY PI + SPEAKERS + BUTTONS
https://www.youtube.com/watch?v=09DQCOr6zQM



# RETROARCH INSTALL STEPS

If you want an graphical software that has emulators that represent various game consoles to play games on such as Atari, or Sega, then
you need to generally install a software like "Retroarch". Retroarch is a multi emulator front and backend software which can be installed 
on many operating systems such as windows, mac or various linux distributions or even as a Steam game app and allows you to download various 
consoles such as Sega Megadrive within it. 

Once installed point to a file location containing various games known as roms, 
setup key bindings, set to download game artwork and launch Retroarch and get started choosing a retro or modern game console and game to play. 
The guide below advises how to setup Retroarch on Windows, Mac and Linux distro's and get BIOS for game consoles.

Note that when installing Retroarch through Retropie it automatically installs an frontend GUI software called "Emulation Station".

Note some users may choose to install an additional frontend ontop of the basic graphical interface of Retroarch. Once such example is
Launchbox which is discussed in the following section. 

## BIOS

What is a BIOS and why is it needed?

BIOS represent the Operating System of a console. Old retro consoles like gameboys don't have an OS like modern consoles
such as Playstation, therefore retro console emulators can run games without a need for a BIOS.

To obtain a bios requires dumping (extracting) the files from your existing console. Considering you own the consoles
already you can conveniently find a list of all BIOS needed for Retroarch here: https://github.com/Abdess/retroarch_system
download the files and put them in the default /retroarch/system/ folder 
e.g. on Windows If you want to play Playstation games on Retroarch then dump from your own console or for ease download the bios folder from above link 
for Playstation then add the files below
C:\RetroArch-Win64\system\scph5500.bin
C:\RetroArch-Win64\system\scph5501.bin
C:\RetroArch-Win64\system\scph5502.bin

## CORES

Cores are the individual emulator softwares that are downloaded and installed within Retroarch. So instead of managing multiple software
to emulate different consoles you can add them all to a single software like Retroarch.

For Arcade games MAME is the arcade emulator. MAME versions are backwards compatible so it's always recommended to have the latest up 
to date installed (or downloaded as a core as part of Retroarch). In Retroarch download core "Arcade (MAME)" this always refers to the 
latest version of MAME which works with the latest ROM verions.

You can install MAME standalone as a software on an PC without Retroarch, or in Retroarch add the latest version of the installed
MAME on the PC as a core to then play the latest versions of the games.

For all consoles that you will want on Retroarch, you will need to download the Cores for e.g, if you want to play Playstation 1 games
on your arcade machine then in Retroarch download "Sony Playstation (beetle)" then add the BIOS "See section BIOS" and add games to ROM folder
and import the content/scan the games, set the default core and start a game.

## ROMS

We do not condone piracy of games. If you require games (roms) then you will need legally own and dump the games or search online
for them if you already own them.

### PAL OR NTSC/JAP | REGION DIFFERENCES

ROM is read only memory. Cartridge based consoles such as old Sega Megadrives, or Gameboys used physical game cartridges which contained memory modules that held all the game code 
and when dumped meaning copied digitially from the catridge such as to a computer the resulting file is referred to as a ROM.

CD based consoles use disc images that have been ripped from the CD and can be in many formats such as .bin/.cue, .img, .chd, .rvz, .zso and many others. They are the same thing
conceptually as a ROM when it comes to a digital copy of a physical game.

Their are 2 major types of retro ROMS to download PAL vs NTSC/JAP. Most retro classic games were made in Japan or North America and thus
were created to run at a 60hz TV refresh rate, contrasted to PAL regions which are everywhere else e.g, Europe, Australia, South America
the TV's run at 50hz.

What this means is when you play a NTSC/JAP game it runs at the intended full speed of 60 Frames per second which their TV's can handle.
But old PAL CRT TV's and Consoles are often too slow to run at the 60FPS (Frames per second) and thus are reduced to 50 FPS. So playing
a PAL game is often slower if it's not a modern optimised version.

Their is also an incompatability between running the opposite region game on a region locked console e.g, playing Sonic 1 (NTSC)
on a Australian PAL Megadrive will have issues playing.

Thus the correct ROM version to buy/download/play is subjective It really depends on the console/TV refresh rate/game regional differences.

EXAMPLE 1: PAL Megadrive console is locked to playing any game at 50hz regardless of cartrdige/rom used in it.
EXAMPLE 2: Gameboy era games run at 60hz and not frame locked so you can get any version of the game you prefer.

So really it depends on your console, if your using emulator, what TV refresh rate your using and the game itself, and if theirs region locking on the game
and finally games themselves have translation/localisation differences such as cencorship or removing/adding content.

In general when using an emulator it's best to use NTSC/JAP Roms for all games, but when using retro hardware it's a case by case basis depending on your Console/TV/Cartrdige hardware setup.

If your unsure still you can always dump both versions of the ROM as long as you own them, or you can seperate into 2 different folders so that way 
it's easier to manage e.g, folder 1: megadrive (PAL), and folder 2: megadrive (NTSC JAP)


## BITS

In the past (pre year 2000) game consoles were judged on bits.

Bit refers to the size of data used in input and output (like pipes) of a computers brain (called the CPU) and it's related hardware. They are used for game logic, 
drawing images/sprites and colours and controller inputs. Thus the more bits the more things can happen in a game and more complex games you can make.

In the past we really only had the CPU doing all the hard work.

Now it doesn't matter because we have specialised chips to do certain tasks e.g. GPU = Graphic Card for drawing graphics on a screen. NPU = chip for Artificial 
Intelligence/Machine Learning tasks like what chess move to perform, and of course the good old CPU which is the brain of everything has less work these days.

## WINDOWS INSTALL STEPS

Install Retroarch from here: https://www.retroarch.com/

## MAC INSTALL STEPS

Install Retroarch from here: https://www.retroarch.com/

## LINUX INSTALL STEPS

Setting up Retroarch on Linux is often difficult and time consuming, you can choose to setup yourself using below link
Install Retroarch from here: https://www.retroarch.com/ 
or use Retropie which runs on may Linux distro's (not just Raspberry Pi) which runs a bunch of scripts that installs and configures; 
1. User account "pi" with all necessary permissions
2. Default drivers (if RaspberryPi)
3. Retroarch
4. All emulator cores (even for PS1 games to work without BIOS if not yet added)
5. All ROM folders, etc.,
6. Emulation Station (from git pull ./make not from apt)
7. Autoboot to "emulationstation" launcher

So you can see it does quite alot. If you want a dedicated linux emulator device
then best use RetroPie to automatically do it all.

## RETROPIE SETUP STEPS

1. INSTALLING FROM IMAGE
```bash
1. Use PI imager - Select Raspberry Pi OS - Select storage medium e.g, Micro SD Card - Enable SSH during setup - Enable Wifi and add login details - 
Install - Plug Micro SD card into Pi then done. 
2. Find the IP address of the Raspberry PI e.g. either from router or arp -a command if on same network 
```

2. OPTIONAL. CHANGING WIFI PASSWORD IF FORGOT TO ADD TO IMAGE ABOVE
```bash
/etc/wpa_supplicant/wpa_supplicant.conf # edit this file

network={
    ssid="YourNetworkName" # update this with your wifis name
    psk="YourPassword" # add your wifis password here
}
```

3. ACCESS PI VIA SSH
```bash
ssh pi@IP_GOES_HERE
password %: raspberry
```

4. UPDATE PI
```bash
sudo apt update
sudo apt upgrade -y
```

5. OPTIONAL - FOR PI 5 BOOT FROM NVME M.2
```bash
a. Connect a compatible m.2 hat for the Pi 5 and add connect NVME m.2 storage media and to the pi
b. In Raspberry Pi imager "you can reopen it if you closed it" click Storage then select the NVME m.2 storage media
follow instructions
c. sudo raspi-config
d. Advanced Options
e. Boot Order
f. NVME/USB Boot
g. sudo nano /boot/firmware/config.txt
h. insert line below
dtparam=pciex1_gen3
i. sudo reboot now
```

6. INSTALL RETROPI
```bash
# 1. Run code below
cd ~
git clone --depth=1 https://github.com/RetroPie/RetroPie-Setup.git
cd RetroPie-Setup
sudo ./retropie_setup.sh

# 2. At the installation screen select - basic installation - yes/continue
# 3. Installation will continue. For an estimation it took ~60 minutes on a Raspberry Pi 5 with at least 20MBps Wifi, so older models will take  much longer
# 4. Reboot device with command ```sudo reboot now```
```

7. OPTIONAL - INSTALL FTP AND OPEN PORT 21 FOR FILE TRANSFER (ONLY IF NOT SETUP DURING BOOT IMAGE ADDITIONAL STEPS)
```bash
sudo apt install vsftpd
sudo nano /etc/vsftpd.conf
Uncomment local_enable=YES # to allow local users to log in.
Uncomment write_enable=YES # to allow write access to the FTP server.
netstat -tuln # check if port now open
sudo systemctl restart vsftpd # then restart service and view port 21 now available for FTP
pi@retropi:~ $ tcp6       0      0 :::21                   :::*                    LISTEN 
```

8. OPTIONAL CHANGE ROMS FOLDER AND MOUNT USB
```bash
# 1. When a storage drive is connected to a linux computer, it will either appear under. If the below entries are empty the device needs to be mounted first.

ls /mnt
ls /media

# 2. Run code below to find mounts

pi@retropie:~ $ lsblk
NAME        MAJ:MIN RM   SIZE RO TYPE MOUNTPOINTS
sda           8:0    1 233.1G  0 disk
└─sda1        8:1    1 233.1G  0 part
mmcblk0     179:0    0  29.2G  0 disk
├─mmcblk0p1 179:1    0   512M  0 part /boot/firmware
└─mmcblk0p2 179:2    0  28.7G  0 part /

# 3. We can see under ```/sda/sda1``` there is the unmounted USB storage. To mount first create a directory for it, then mount the unmounted drive to it

sudo mkdir /mnt/romusb
pi@retropie:~ $ sudo mount /dev/sda1 /mnt/romusb
pi@retropie:~ $ ls /mnt/romusb
 ROMS  'System Volume Information'

# 4. Run below code to change the default emulationstation rom search path for each core to the new mounted path in this file ```/etc/emulationstation/es_systems.cfg```

sudo sed -i 's|<path>/home/pi/RetroPie/roms/|<path>/mnt/romusb/ROMS/|g' /etc/emulationstation/es_systems.cfg

# verification below
pi@retropie:~ $ sudo nano /etc/emulationstation/es_systems.cfg

<?xml version="1.0"?>
<systemList>
  <system>
    <name>amstradcpc</name>
    <fullname>Amstrad CPC</fullname>
    <path>/mnt/romusb/ROMS/amstradcpc</path>
    <extension>.cdt .cpc .cpr .dsk .m3u .tap .zip .CDT .CPC .CPR .DSK .M3U .TAP .ZIP</extension>
    <command>/opt/retropie/supplementary/runcommand/runcommand.sh 0 _SYS_ amstradcpc %ROM%</command>
    <platform>amstradcpc</platform>
    <theme>amstradcpc</theme>
  </system>
```

9. OPTIONAL IF USING SDCARD AS ROM STORAGE - TRANSFER GAMES FROM STORAGE MEDIA (e.g, USB) TO MICROSD
IMPORTANT: PS2 games come in single .iso (DVD games) or a older 2 files together .bin/.cue (CD-ROM) style
a. Find the "Rom Folder" names for each emulator you want e.g. for Gameboy
the emulator Rom Folder name is "gb" from official docs - https://retropie.org.uk/docs/Game-Boy/ 
b. Make the folders on a USB and fill them with roms that you dumped from your own cartridges
c. Plug the USB into any USB slot of the raspberry pi and first see which usb folder it's in
e.g. /media/usb or usb1 - 4
d. Copy all the folders over. You can also use FileZilla or any FTP software to do the same thing with a GUI interface easily
```bash
cp -r /media/usb1/* /home/pi/RetroPie/roms 
```

10. OPTIONAL - Read section "LOADING MULTIPLE DISCS | MULTI DISC GAMES | CHANGE DISC" to setup file for multi-disc games if available

11. ADD BIOS
(Necessary for PS1 and all CD based modern retro consoles)
a. Find the BIOS somewhere e.g. by dumping your own consoles BIOS
or here if you legally own the console: https://github.com/Abdess/retroarch_system/releases/
b. Put all files (e.g. for PS1) in ```/home/pi/RetroPie/BIOS``` either with command below or using a simple GUI software like Filezilla
```bash
cp scph5500.bin, scph5501.bin, scph5502.bin /home/pi/RetroPie/BIOS
```

12. CONSOLE BOOT SOUND
a. Edit config to set boot sound for whichever core e.g. ps1 to start
If the below is not available don't worry, in Retroarch install core for PS1 then do the below
```bash
nano /opt/retropie/configs/all/retroarch-core-options.cfg
pcsx_rearmed_show_bios_bootlogo = "disabled"
# change to
pcsx_rearmed_show_bios_bootlogo = "enabled"
```

13. SETUP - START EMULATION STATION (THE FRONTEND SOFTWARE) OR START GAME ON BOOT
```bash
# 1. add code below

nano /opt/retropie/configs/all/autostart.sh
# To start any rom on startup type/replace the core and rom path with the game 
/opt/retropie/supplementary/runcommand/runcommand.sh 0 _SYS_ mame-libretro ~/RetroPie/roms/mame-libretro/sf2ce.zip &&$
# emulationstation #auto


# 2. To reverse the above change comment the top and uncomment the bottom.

pi@retropie:~ $ cat /opt/retropie/configs/all/autostart.sh
# /opt/retropie/supplementary/runcommand/runcommand.sh 0 _SYS_ mame-libretro ~/RetroPie/roms/mame-libretro/sf2ce.zip && emulationstation
emulationstation #auto
pi@retropie:~ $
```

# MAME RETROARCH SETUP

1. See section RETROARCH INSTALL STEPS to install Retroarch to manage MAME (Easiest method)
2. In Retroarch install core : Arcade (MAME)
This is always the latest up to date verion of MAME
3. Dump all the ROMS, conveniently you can download from here: https://r-roms.github.io/megathread/retro/
In this scenario we will be using ROM set 0.265 so follow link above to here
https://archive.org/details/mame-merged
and download the following into the same ROM folder as all other Retroarch games are pointing to; or make a new folder to store these games if not using retroarch
4. MAME BIOS Sets: https://archive.org/download/mame-merged/BIOS/
5. MAME ROM Set (Merged) - No CHD: https://archive.org/download/mame-merged/mame-merged/
ROMS represent the game dumps for simple games like mspacman.zip
6. MAME CHD (Merged): https://archive.org/download/MAME_0.225_CHDs_merged (Maintained by @lollo_220)
CHD's are ROM's that are in CD format for newer games
7. Find the DAT file which coresponds to the version of MAME you are using from going to this link and clicking DOWNLOAD for DAT https://www.progettosnaps.net/dats/MAME/)
8. Extract DAT folder and open XML folder and copy and paste the .xml file to the same folder as above with all MAME games in it
The XML file is used below to convert the ROM zip names into identifiable expanadable database names e.g, hotd.zip to House of the Dead, in order to find Thumbnails, artwork, cheats etc.,  
9. Start retroarch then click "import contents" - "manual scan" and set the below parameters
Content Directory = select your rom folder with the mame games
System Name: "MAME"
Scan Inside Archives: OFF
Arcade DAT File: MAME XML database
Arcade DAT filter: ON
Default core to: "Arcade (MAME)"
Then scroll to bottom and press start scan.
10. Once done and games show in playlist in main menu, select the playlist and select use default core "Arcade (MAME)" now start and test a game

# RETROARCH CONFIGURATION

NOTE: If using Retropie to access Retroarch settings In main menu (core/emulator section) select RetroPie - RetroArch (will open a new menu)

### ADD GAMES
Settings - Import contents - select the individual folders which have your game roms then click scan directory.
Games will then automatically be added to Playlists

### ADD UNLICENSED AFTERMARKET ROMS
Some third party games e.g, itch.io gamejam/fan-made gameboy games will not add to playlists due to not being in the Retroarchs game CRC checksum 
database. To get around this perform the below;
Import content - Manual scan - Content Directory (Select the folder containing the third party roms) - System Name & Default Core 
(select the default core to use [e.g, Gambatte for Gameboy]) - select Start scan. Now third part games will appear in appropriate playlist

### DELETING GAMES | REMOVE ENTRY FROM PLAYLIST
You can delete a game by deleting the file from the text terminal when you SSH into the device if Ubuntu, or from going to the game
in retroarch and in menu clicking remove game. However it may still appear in your playlist. To fix perform below;
Settings - Playlist - Manage Playlist - select the playlist - cleanup playlist

### CHANGE RETROARCH THEME
Settings - User interface - Menu - choose whatever (ozone is default, rgui is the Playstation like clone)

### SWAP A/B BUTTONS
Settings - Input - Menu Controls
b. Set "Menu swap OK/Cancel buttons" to ON. This will change A/B buttons (or X/O on playstation controller)
c. Go back to Main menu - configuration - save current configuration
d. Done

### SETUP HOTKEYS (TURBO + SAVE STATES + EMULATOR MENU)
Settings - Input - Hotkey Binds
b. scroll down to Hotkey - set to PS button on Playstation controller 
(e.g. the PS logo on Dualshock 5)
c. Select Fast Forward (Toggle) to be R3 (use in game with Press PS button + R3 (Hold down))
d. Menu toggle gamepad combo - select "Start + Select" (use in game with Press Start + Select)
e. Go back to Main menu - configuration - save current configuration
f. Done

### SETUP BOTH ARCADE BUTTONS/JOYSTICK
note you can keep a ps controller or keyboard plugged in while setting up the 2 arcade sticks
To setup any controller just hold down any button on it and it will detect
just that controller, then setup any buttons and skip any you cant do
a. https://www.youtube.com/watch?v=uL3K8sZIuWo

### ADD GAME ARTWORK | THUMBNAIL IMAGES
a. In main menu where you select your emulators press start
b. Press scrapper
c. Press to configure by having user not worry about conflicts (automatically find images)
d. Press to start and it will download all images by itself
e. If Some images are skipped you can go back and choose the second scrapper which scraps images
from a different website and complete the remaining images

### SET DEFAULT CORE FOR PLAYLIST
Instead of manually choosing a core everytime you load a game, if you click start
on a playlist you can select choose default core and set it to the related core.

### KEEP MOUSE LOCKED TO ACTIVE GAME SCREEN (NO BORDERLESS)
a. set hotkey mouse (toggle) to any button e.g. double quotation mark (").
in game press that button and mouse will lock to screen.

### EMULATOR BOOT SOUND e.g, PLAYSTATION STARTUP SOUND
As long as you have the bios in the /system folder when starting a game it will autodetect
and play the startup audio/video

### GAMEBOY GAMES CHANGE COLOUR PALETTE

Old gameboy games may not have color codes in which case start game - go to core options - set GB colorization to "GBC"
otherwise it will default if left on "Auto" to the "Internal Palette" which is the default "GB - DMG" green screen.

For any other game the "Auto" option will automatically select the best palette.

Recap - for green gameboy old games - set GB Coloirzation to "GBC"

### LOADING MULTIPLE DISCS | MULTI DISC GAMES | CHANGE DISC

If the ROM/game has multiple Disc's such as playstation 1 games then do the following.
From experience it's best to do this step before playing the game and creating a save file as it may not be found (citation needed.)
1. Create a file with the ROM/games name and save with the file extension .m3u  e.g, "Cool Game.m3u" within the same folder as all other ROM files
2. Edit the file and add the discs (.cue) files of the game e.g,
"
Cool Game (Europe) (Disc 1).cue
Cool Game (Europe) (Disc 2).cue
"
3. Start Retroarch - Import content - select the ROM folder (which also has he .m3u file) - and you will see only 1 game to select from in the Playlist. You can now play the game.
4. In game when advised to change discs - go to quick menu - Disc Control - Eject Disc - select the new disc from the Index by scrolling left/right to change to next index number e.g, from "1" to "2"
then click "Insert disc" - then go back to game

Note if you add games this way then you must always use "Manual Scan" option to combine all CD's into 1 game in Retroarch.

### MULTIPLAYER GAMES

For example to host and join a game of Joust on MAME using RetroArch, follow these steps:

Ensure port 55435 is not blocked through firewall for host or client

HOST SETUP GAME STEPS

1. Both you and your friend need to have the same version of RetroArch installed.
2. Ensure that both players have the same ROM file for Joust and are using the same MAME core (e.g., MAME 2003, MAME 2010, etc.).
3. Both players should also have the same version of the MAME core loaded in RetroArch.
4. The host player (e.g., in New Zealand) should ensure that their router has port forwarding enabled for RetroArch's default port (55435) to their local machine.
This can be done by accessing your router's settings and adding a port forwarding rule that forwards traffic on port 55435 to your internal IP address (the IP of the machine running RetroArch).
5. The host player should note down their public IP address (e.g., 110.10.10.10). You can find this by searching "what is my IP" in a search engine.
6. Open RetroArch and load the MAME core.
8. Load the Joust ROM using the MAME core.
9. Go to the Quick Menu "START + SELECT" - "Netplay" - "Start Netplay Host"
You will now be hosting the game on your public IP and the default port (55435)

CLIENT JOIN GAME STEPS

1. Open RetroArch and load the MAME core.
2. Load the Joust ROM using the MAME core.
3. Go to the Quick Menu "START + SELECT" - "Netplay" - "Connect to Netplay Host"
4. Enter the public IP address of the host (110.10.10.10) and the port (55435).
5. Retroarch will attempt to join the game

### SWAP D PAD MOVEMENT FOR LEFT ANALOG STICK

For some games e.g, Playstation 1, which only use d-pad for movement such as Xenogears, you can go into the quick settings "START + SELECT"
- Controls - Port 1 Controls - Analog to Digital type - set to Left Analog. Now you can control movement with the stick.s

### AI LANGUAGE TRANSLATIONS

You can use the power of AI to translate foreign while playing a game using an running AI on your computer
and with the Retroarch Hotkey for AI services pressed. See more here: https://docs.libretro.com/guides/ai-service/

# LAUNCHBOX FRONTEND SETUP

As discussed earlier within retroarch section, it's optional to install a frontend graphical user software
on top of retroarch. (Note Retropie already installs "Emulation Station" as a frontend GUI software for simplicity. You can choose to replace if you desire).

Launchbox is an innovative frontend GUI because it allows using a second monitor (e.g, a physical marquee LCD screen above your primary display)
as a digital marquee. E.g, https://www.reddit.com/r/Arcade1Up/comments/o2nvtg/my_modded_a1us_final_form_lcd_dynamic_marquee/

If you like the design you can follow the steps below to install it over Retroarch.

STEPS

# SELLING ARCADE MACHINES

## IF USING LINUX CLEAR WIFI PASSWORD
```bash
/etc/wpa_supplicant/wpa_supplicant.conf # edit this file

network={
    ssid="YourNetworkName" # Remove your Wifi name
    psk="YourPassword" # Remove your wifi password
}
```


# CREDITS

      Thanks to retromash.com for teaching us how to build our dreams

      Thanks to everyone in the Arcade1UP Reddit & YouTube community for keeping this hobby alive.

      Thanks to the dedicated Arcade1UP staff who fight to give us the best product possible.

      Thanks to my canine companion Porus for always being there for me.

      And finally thanks to people like you that read this and continue to keep the hobby alive for others to experience.
