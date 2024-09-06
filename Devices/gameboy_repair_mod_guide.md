
# GAMEBOY REPAIR MOD GUIDE

* By: Sumeet Singh @ sumeet-singh.com
* Created: August 2024
* Version: 1.0 (September 2024)
* Description: This document outlines various ways to repair, build, modify, and program flashcarts, and find retro games for any Nintendo Gameboy model.
The purpose was to bring life to our old childhood consoles. I do not condone piracy nor performing any activity that renders breaking a EULA or 
Terms and conditions contract between a product vendor and customer. I recommend to buy official licensed games and hardware.

# TABLE OF CONTENTS
- [1. Terminologies](#terminologies)
- [2. Architecture](#architecture)
- [3. Schematics](#schematics)
- [4. Repairing and Modding](#repairing-and-modding)
- [5. Accessories](#accessories)
- [6. Roms](#roms)
- [7. Flashcarts](#flashcarts)
- [8. Games to play](#games-to-play)
- [9. Programming](#programming)

# TERMINOLOGIES

GB: Gameboy
GBC: Gameboy Color
GBA: Gameboy Advance
TFT: A thin LCD display
OLED: A modern LCD display with pixels turning off in dark images leading to true blacks and power saving.
Dumping: The process of extracting the software/ROM file such as onto a computer.
Flashing: The process of adding a software/ROM onto a hardware, such as adding a custom game to a gameboy cartridge

# ARCHITECTURES

Gameboy and Color architecture is documented here: https://www.copetti.org/writings/consoles/game-boy/

# SCHEMATICS

PCB Schematic layers for all consoles are located here: https://www.retrosix.wiki/gbc-board-scans

# REPAIRING AND MODDING

There are several online stores  to buy mods, aftermarket and replacement parts that I'm aware of in my limited research.
1. Aliexpress or any other similar chinese cheap online retailer
2. retrogamerepairshop.com for their catalogue of items
3. Inside Gadgets for the biggest range of unique parts: https://shop.insidegadgets.com/

The tools you will need to fix the gameboy are;
* 3.8mm gamebit screwdriver (buy a pack of oth 3.8/4mm+ and that will cover most retro consoles for $2 online)
* Tri-wing screwdriver (or replace with a standard straight head screwdriver)
* Flush cutters: the name of the cuting pliers to cut plastic etc.,
* Scoring knife: Those safety cutting knives for boxes etc.,
* Dremel: This is a pen like often portable sandpaper/drilling tool. It can be used to drill and expose traces on PCB's or mould plastic

## REPLACE BATTERY

Gameboy games use either CR1616 or CR2025 cell batteries that need resoldering every time they deplete e.g, after 10+ years.
When you replace the battery ensure you use a cell holder which is easier to replace the battery in the future without soldering.

## REPAIR PAD

Watch this video that demonstrates how to repair damaged pads: https://www.youtube.com/watch?v=SaBwdJLFVPU

## REPLACE CAPACITOR

The stock gameboy comes with electrolytic capacitors which for preventitive measures should be replaced every 30 years
as with most electronics. However if you replace it with a ceramic capacitor it could last your lifetime.

Watch this video that demonstrates replacing the correct capacitors: https://www.youtube.com/watch?v=NtiXFsPRK4s&t=1185s

## REPLACE SHELL

The modding consencous is to transfer over/replace stickers (serial/warranty) for authenticity.

## TRIM SHELL FOR NEW SCREEN

Watch this video guide: https://www.youtube.com/watch?v=CII21-B6lJ4

## REPLACE SCREEN

The GBC screen size is 2.3" TFT. Note that modding community concensous is that
the stock screen is too small. The author myself agrees. You may want to replace it
with a more larger and backlight display.

Their are 2 ways to replace your gameboy screen to date with a better option

1. Old method: V2 IPS Solderless screen e.g, https://retrogamerepairshop.com/collections/gbc-displays/products/game-boy-color-2-45-drop-in-backlight-lcd-kit?variant=41377297629356
These displays are refurbished from old Blackberry Q5 phones
Pros: 
    Keep original shell
    Keep old logo
Cons: 
    Touch sensor covers IR port so no IR features e.g, no trading pokemon in color Pokemon games/TV remote/multiplayer
    Bad battery performance ~ 5hrs (original display lasts 10hrs)
    Bad viewing angles

2. new method: OLED touch screen requiring 1 solder point e.g, https://www.youtube.com/watch?v=hcreLP72Wv0
These displays are refurbished from old Blackberry Q10 phones
Pros:
    Add touch screen
    Average battery performance ~7.5hs (original display lasts 10hrs)
    Better contrast, picture quality, and response time
    Bigger screen
    Better for recording on camera
    Flush bezel with in game black borders
Cons:
    Requires new shell (If you buy an aftermarket shell it's best to replace the buttons with the original)
    No logo
    Requires soldering
    Poor longetivity eventually burn in (require more frequent replacing)

In summary if you don't mind replacing the gameboy with a new OLED monitor in the future (as with capacitors every 30 years) then buy the OLED.
Nothing lasts forever and having the best screen for sharing the gameboy with others is priceless. 

## REPLACE SPEAKERS

Speakers have no polarity. Buy aftermarket from a website such as Aliexpress and solder
both wires to replace stock broken speakers.

A video guide is here: https://www.youtube.com/watch?v=zGMKTN90E8A

# ACCESSORIES

## GAMEBOY MINI CAMERA

A new Gameboy Camera the size of a standard cartridge has been invented see example here: https://www.reddit.com/r/Gameboy/comments/1c4v30w/famicom_game_boy_mini_camera/
It comes with a unique ROM for the new camera function software, but supports a 2nd ROM so you can dump and load the Gameboy Camera game onto it also

You can order from the author here (default black shell to indicate works on all gameboy models) - https://gameboycamera.super.site/projects/game-boy-mini-camera

To build it yourself will require the below;

The 3D model files can be ordered from here - https://ko-fi.com/s/2cdcc23790
PCB here - https://www.pcbway.com/project/shareproject/Game_Boy_Mini_Camera_25c50b6d.html
Free label here - https://github.com/supertazon/Game-Boy-Mini-Camera-Famicom-styled-label?tab=readme-ov-file
Gameboy camera desolder to soldering on new board guide: https://www.youtube.com/watch?v=rYTwGNGz8UI

Full build guide: https://www.youtube.com/watch?v=DN7vubOzrxo

### COLOR IMAGES

An video here: https://www.youtube.com/watch?v=vA125ypMdJ0
shows how to use filters to create color images. Possibly something to physically add to the Gameboy camera cartridge

## GAMEBOY PRINTER

An exact dimension alternative to the official Gameboy printer paper exists called the: Seiko S-950 (example: https://www.youtube.com/watch?v=8CpA6znIkq0)

## PRO ACTION REPLAY

Pro action replay (PAR) is a game cartridge that has a slot to insert any gameboy or color game to allow inserting cheats into the games RAM. This works by 
users searching for known cheat codes in a game from the Pro action replay manual to insert before the game starts such as more in game lives, or more difficult enemies.

### COMPARISON WITH OTHER CHEAT DEVICES: GAMESHARK OR GAME GENIE

Unlike other cheat trainers such as Game Genie or GameShark which are NTSC/PAL game specific with no large compatability with JAP games, the PAR accepts universal
codes which may work on any region releases of a game. Furthermore the PAR has a "code trainer" feature to dynamically search a game's cartridge for codes.
Out of all cheat embedding hardware it is the best in terms of features but also rare to aquire due to demand and small released supply.

### Code trainers

Code trainers enable users to search through a game’s memory for specific values or data that can be manipulated. For example, 
if you want to find a code to give yourself more lives or change another game parameter, you can use the code trainer to search for the relevant data.

Process: Typically, you would start by specifying a known value (like the number of lives you currently have). The code trainer then searches the game’s 
memory for that value. You can then modify that value in-game, and the trainer will help you find the new memory address where the value is stored. 
This feature allows for the creation of custom cheats beyond the pre-existing codes available in cheat code databases.

## INSIDEGADGETS GBXCART RW

If you own the physical game cartridge you can use hardware such as the "InsideGadgets GBxCart RW" to physically connect the cartridge to a computer 
and start the hardwares software and save a copy of the ROM e.g. "Cool game.gb" to your computer. You can also backup save files and also add save files
and write new ROM to the cartridge. Allowing you to create your own Gameboy game cartridges.

## ORANGE FM

A cartridge with a built in Radio antenna allowing to listen to FM music from the Gameboy. See here: https://shop.insidegadgets.com/product/orangefm/
Watch the full video here: https://www.youtube.com/watch?v=-lx9iyLkvwA


# ROMS

All gameboy family consoles, games and accessores are region free. However games language is default to the region e.g, Japanese cartrdige games use Japanese language.
Therefore you can use any game/ROM in any system.

ROM is read only memory. Cartridge based consoles such as old Sega Megadrives, or Gameboys used physical game cartridges which contained memory modules that held all the game code 
and when dumped meaning copied digitially from the catridge such as to a computer the resulting file is referred to as a ROM.

CD based consoles use disc images that have been ripped from the CD and can be in many formats such as .bin/.cue, .img, .chd, .rvz, .zso and many others. They are the same thing
conceptually as a ROM when it comes to a digital copy of a physical game.

There are 2 methods of getting roms dumping using hardware (see accessories) or downloading from online. Once you get the ROMS you can add them to a flashcart and then play them on real hardware

You can backup ROM saves using the dumping method also.

## TV REMOTE ROM

The Gameboy color came with a Infrared Receiver (IR) that was used by a specific game "Mission Impossible" to be able to use the Gameboy color as an TV Remote control.
Instead of buying or downloading the game instead a modder has created an ROM of the same software so that you can download it to flashcart and use it.
You can download the ROM from this link: https://bluecop.itch.io/gbc-remote

# FLASHCARTS

Flashcarts refer to 2 differnt related things.

1. An empty cartridge for use with adding a custom game ROM in, such as if you develop your own game or want to download a ROM hack into it to play on hardware
2. A Multi-game cartridge that usually has an OS and holds multiple games with usually an external storage such as MicroSD where you load multiple ROMS in it to play on hardware

Why they are used are for adding games you have created, or modified called hacked, into game aftermarket gameboy cartridges for you to play on hardware.

## SORTING FILES ALPHABETICALLY

When adding ROMS to a flashcart often they will not be in alphabetical order. If that is the case then use the below tools depending on the OS.

Windows: Download Drivesort, connect the SD card to PC: open software and click open drive and select the SD card, 
click sort, then click save then close and test: https://www.anerty.net/software/file/DriveSort/?lang=en

MacOS: Download Fatsort: https://fatsort.sourceforge.io/
connect SD card to PC, in terminal type: diskutil list
Find the SD card in the list of drives and note the disk #, for example: disk2s1
Then type: diskutil unmount /dev/disk2s1
Now run the program: sudo fatsort /dev/disk2s1
Be sure to use diskutil to unmount the drive and not the eject button in the finder, otherwise fatsort won’t work.

## EMPTY FLASHCARTS

For Empty flashcarts there are a variety of products to buy. This website lists many https://shop.insidegadgets.com/product-category/gameboy-flash-carts/

When buying a flashcart ensure it has the hardware to support the ROM, e.g. a FRAM chip will support saving, or an Cell battery will support RTC so you can add
ROM hacks of games that require RTC or FRAM on them.

USB-C or other related access directly to the gameboy cartridge allows programming on the go so you can easily add your own games to it without external hardware required
for dumping/flashing.

Rumble feature flashcarts - https://shop.insidegadgets.com/product/gameboy-4mb-32kb-fram-flash-cart-ultra-low-power/

If unsure this link describes the differences in Flashcarts you need to add games to them - https://shop.insidegadgets.com/choosing-a-flash-cart/

## MULTI-CARTS

There are 3 main product ranges of MULTI-CARTS to date that provide full feature emulation of gameboy family games on real hardware.

FOR GAMEBOY/COLOR GAMES ONLY

* Everdrive G3 - Plays gb/gbc roms, includes Game Genie codes, High quality, power/battery saving
* Everdrive G5 - Same as G3, Includes save state
* Everdrive G7 - Same as G5, Includes RTC
* EZ Flash jr - same G3, includes RTC, No cheats, requires restart to save, drains power/battery fast, cheap material

FOR EVERY GAMEBOY FAMILY GAME + OTHERS

* Everdrive GBA mini
    Same as G7
    Supports gba games/nes/sega master system/game gear ROMS, 
    Inclues Game Genie cheats
    Power/battery efficient
    Battery efficient
* EZ Flash Omega Definitive edition
    Same as G7
    Supports gba games/nes/sega master system/game gear ROMS,
    FRAM saving (Saves on chip for theoretical hundreds of years)
    Includes Slot2 features (GBA to DS trading/multiplayer)
    Includes rumble feature
    Mini computer OS (Web browser, RAM expansion slot, Better UI, Quality of Life features, Game thumbails, supports many file types, can install third party emulators etc., )
    drains power/battery fast

### WHICH MULTI-CARTS TO BUY?

In summary

For gameboy/color games only = Everdrive G7
For all Gameboy family games = EZ Flash Omega Definitive Edition

### Everdrive G7 SETUP

CHEATS: Gameshark modifies the RAM whilst Game Genie modifies the ROM, and the Everdrive can't access the Gameboy's RAM. Thus only Game Genie codes are available.

TBA

### EZ FLASH JR SETUP

* To reset back to main menu from game you can press down on the cartridge while running a game and you will feel a click then let go.
* The battery is not used for saving. It's only used for clock functions in game such as Pokemon Crystal's 24 hour timer. It's not necessary to replace unless
you play a game that requires 24 hour in game clock
* To save game first save in game then restart the flashcart by clicking on it. When device reboots you will be prompted to press (so press) the A button to save
the game to the MicroSD card in the /SAVER folder. You can then plug your MicroSD card into your computer in the future and copy the save file to backup if you wish.
This also means you can take your saves everywhere with you even if the Flashcart dies.
* To use on a Super Gameboy plug it in as normal and press the reset button twice, you will see logo change each time
* Cannot play Gameboy Advance roms if plugged into a Gameboy Advance.
* If you're using this flashcart on a GBA model note that the GBA will output a smaller then normal screen which isn't ideal. Use a EZ-FLASH OMEGA Definitive Edition.
* A bonus feature of a flashcart is the MicroSD card can be used as a storage for files. So you can keep text files/documents of your favourite game guides etc.,

#### UPDATE FIRMWARE

1. To update to latest firmware click visit here and click the Download link under EZ-FLASH junior: https://www.ezflash.cn/download/
2. copy the 2 files "ezgb.dat" and "Update_FWx.gb" (where "x" is the latest version) to your MicroSD card
3. Copy all game roms into the MicroSD card. You can organise them into folders if you wish.
3. Add the MicroSD card to flashcart, insert into gameboy power on and click on the "Update_DWx.gb" file and click A and wait for the update to finish
i will ask you to power off, wait a minute and if it doesn't auto restart the software power off then on again which will take you back to main screen.
5. Test a game and if it works connect the MicroSD card back to your computer and delete the "Update_DWx.gb" file as it's no longer needed

### EZ FLASH OMEGA DEFINITIVE EDITION SETUP

TBA

# GAMES TO PLAY

Here is a author picked variety list of ~60 of the most popular, interesting, technically impressive, historically significant, rarest games and modded/hacked versions of
existing games for the Gameboy and Gamboy Color to collect. You can also find new games being made for Gameboy all the time such as on Itch IO here: https://itch.io/games/tag-gameboy-rom
Try searching the Internet for "new gameboy games" and try a few out, a author suggestion is new game "The Machine" found here: https://themachinegame.com

NAME | DESCRIPTION

Aliens - Thanatos Encounter                      
Alleyway: Launch title
Alone in the Dark: The New Nightmare: Technically impressive use of prerendered images for graphics
BattleCity: Multiplayer game
Castlevania (Any game in series): There are 3 games in the series on Gameboy, and 2 remakes in color for Gameboy color, each is historically important in the series
Catrap
Commander Keen: The last game in a historically popular western PC game series
Densha de Go! 2: Largest gameboy game by filesize
Donkey Kong
Dragon Warrior III: Technically Impressive NES Port
Elevator Action EX
F-1 Race: First gameboy racing game
Final Fantasy Legend: The first game in the SaGa e.g, "Romancing Saga" JRPG series 
Final Fantasy Adventure: The first game in the mana e.g, "Secrets of Mana" JRPG series
Game & Watch Gallery: First international gameboy gallery game knows as "Gameboy Gallery 2" in PAL release
Ghosts 'N Goblins: Technically impressive port of NES game with
Heroes of Might and Magic II
Kirby's Dream Land 2 DX: Colorised hacked modded game
Kirby's Dream Land DX: Colorised hacked modded game
Legend of the River King
Lufia The Legend Returns
Mario Golf: Highest rated Gameboy golf fame
Mario Tennis
Mega Man World 3 DX: Colorised hacked modded game
Mega Man World Dr. Wily's Revenge: Colorised hacked modded game
Mega Man World II: Colorised hacked modded game
Metal Gear Solid
Metroid II - Return of Samus
Mole Mania
Nekketsu Kouha Kunio-kun - Bangai Rantou Hen
Perfect Dark
Pocket Bomberman
Pokemon - Blue Version
Pokemon - Crystal Version
Pokemon - Red Version
Pokemon - Yellow Version - Special Pikachu Edition
Pokemon Pinball
Pokemon Trading Card Game
Pop Up
R-Type DX
Rampage - World Tour
Resident Evil Gaiden
Resident Evil GBC: unreleased prototype port of the same game released on Playstation.
Sakura Wars GB
Shadowgate Classic: Technically impressive port of PC game
Shantae: Technically impressive of any Gameboy color game released during Gameboy Color End of life period
Super Mario Land 2 DX: Colorised hacked modded game
Super Mario Land DX: Colorised hacked modded game
Survival Kids: Rare game
Tetris DX
The Legend of Zelda - Link's Awakening DX
The Legend of Zelda - Oracle of Ages
The Legend of Zelda - Oracle of Seasons
Towers - Lord Baniff's Deceit
Trip World: Rarest PAL game
V-Rally - Championship Edition
Wario Land - Super Mario Land 3 DX: Colorised hacked modded game
Warlocked
X: Canonically part of the Metroid Series story.

# PROGRAMMING

There are 2 methods to program on gameboy for creating game roms either using GUI software such as "GB Studio" or hardcoding.

There are 2 languages to program Gameboy games in with mature development frameworks and that can be implemented without too much difficulty
Assembly (ASM) or C (No C++ as it's difficult for the onboard chip and c++ is too bloated.)

## PROGRAMING WITH C

There are several courses to choose from to learn how to program on Gameboy using the C language. Try watching all to learn different methods
at coding

Course 1. CREATING FIRST HELLO WORLD ROM - https://www.youtube.com/watch?v=HIsWR_jLdwo
Course 2. https://www.youtube.com/watch?v=eYT9s9bvKYU

## PROGRAMMING WITH ASSEMBLY (ASM)

Honestly for the average person and even programmer it's not worth programming in ASM. For starters the language was used to push the original cartridges
to the limit, but now with aftermarket and official devices with plenty of memory, and performance upgrades, such as new flashcarts, Gameboy Color, and Advance range
there's plenty of processing/storage/ram power to utilise without sacificing coding in a higher langauge like C.
