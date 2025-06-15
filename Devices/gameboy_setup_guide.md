
# GAMEBOY SETUP GUIDE

* By: Sumeet Singh @ sumeet-singh.com
* Created: August 2024
* Version: 1.0 (September 2024)
* Description: This document outlines various ways to repair, build, modify, and program flashcarts, and find retro games for any Nintendo Gameboy model.
The purpose was to bring life to our old childhood consoles. I do not condone piracy nor performing any activity that renders breaking a EULA or 
Terms and conditions contract between a product vendor and customer. I recommend to buy official licensed games and hardware.

# TABLE OF CONTENTS
- [1. Terminologies](#terminologies)
- [2. Models](#models)
- [3. Architecture](#architecture)
- [4. Schematics](#schematics)
- [5. Repairing and Modding](#repairing-and-modding)
- [6. Accessories](#accessories)
- [7. Roms](#roms)
- [8. Flashcarts](#flashcarts)
- [9. Games to play](#games-to-play)
- [10. Programming](#programming)

# TERMINOLOGIES

GB: Gameboy
GBC: Gameboy Color
GBA: Gameboy Advance
TFT: A thin LCD display
OLED: A modern LCD display with pixels turning off in dark images leading to true blacks and power saving.
Dumping: The process of extracting the software/ROM file such as onto a computer.
Flashing: The process of adding a software/ROM onto a hardware, such as adding a custom game to a gameboy cartridge

# MODELS

There are several models of gameboy to buy each with release date, games played and pros and cons found here: 
https://www.nintendo.com/en-gb/Hardware/Nintendo-History/Nintendo-History-625945.html

# ARCHITECTURES

Gameboy and Color architecture is documented here: https://www.copetti.org/writings/consoles/game-boy/

If you want to learn electronics, especially using a Gameboy as examples this 15 minute video is the most impressive way to learn: https://www.youtube.com/watch?v=QS4fzElm8zk
You can follow along with the accompnying article here: https://there.oughta.be/a/wifi-game-boy-cartridge
A follow up showing how to use the above Wifi example to send full feature images, videos or streaming to the gameboy: https://there.oughta.be/gta5-for-the-game-boy

## MULTIPLAYER

The gameboy family use phyical Link cables connected to each other.

There are 4 link cable models;
4 pin 1 to 1 - for 2 players
6 pin 1 to 1 - for 2 players
4 pin 1 to 4 - for up to 4 players
6 pin 1 to 4 - for up to 4 players

Gameboy/color range use 4 pin physical link cables, while the advance series use 6 pin physical cables, thus connecting
the old series to the new series is incompatible.

The color series included an Infrared sensor for multiplayer usage in some games such as trading pokemon.

Gameboy advance did introduce wireless adapter which worked wih some games.

Alternatively you can setup an online multiplayer webserver see here to play over the internet: https://www.youtube.com/watch?v=KtHu693wE9o

## GAME SAVING

There are 2 methods of saving games on their own cartridges
Volatile - On board save requires a battery to provide constant power even when off. If the battery dies the save game is erased
Non-volatile - Requires no battery and save games are persistently saved in chip even when cartridge is powered off.

The gameboy family has 4 methods of saving games on their own cartridges

Flash Memory 
Type: non-volatile
Write/Read cycles Limit: 3,000 - 100,000 program/erase (P/E) cycles
Data Retention: 10 - 20 years

FRAM (Ferroelectric RAM)
Type: non-volatile
Write/Read cycles Limit: Exceeds >10 billion writes
Data Retention: 10 - 15 years

EEPROM (Electrically Erasable Programmable Read-Only Memory)
Type: non-volatile
Write/Read cycles Limit: ~1,000,000 writes
Data Retention: 10 - 20 years

SRAM (Static RAM)
Type: volatile
Write/Read cycles Limit: Unlimited
Data Retention: Data is retained only as long as constant power is supplied

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

Watch this video that demonstrates how to repair damaged pads: https://www.youtube.com/shorts/WCOVe0QKmPU

## REPAIR CONTACT STRIP PIN

https://www.circuitrework.com/guides/4-6-1.html

or

https://www.circuitrework.com/guides/4-6-2.html

## REPLACE CAPACITOR

The stock gameboy comes with electrolytic capacitors which for preventitive measures should be replaced every 30 years
as with most electronics. However if you replace it with a ceramic capacitor it could last your lifetime.

Watch this video that demonstrates replacing the correct capacitors: https://www.youtube.com/watch?v=NtiXFsPRK4s&t=1185s

## REPLACE SHELL

The modding consencous is to transfer over/replace stickers (serial/warranty) for authenticity.

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

Speakers have no polarity which means you can solder any wire to any side. You can buy aftermarket speakers which are usually refurbished from existing phones like Blackberrys 
like the IPS/OLED screens are, from a website such as Aliexpress and remove existing/replace speakers. 

You may want to paint them black and gold to match the original Nintendo stock speakers.

Test the speaker ideally after painting and before soldering by connecting a battery to it on any wire and seeing if there is any noise e.g; https://www.youtube.com/watch?v=pmU-KyxnYVA

A video guide on replacing the speaker is here: https://www.youtube.com/watch?v=83WY8LNXjV0

## TRIM SHELL

Watch this video guide: https://www.youtube.com/watch?v=CII21-B6lJ4




# ACCESSORIES

## SUPER GAMEBOY

To play games on a TV officially there are only 3 devices that can allow that. 

1. Super Gameboy: released as a cartridge on SNES which has a slot to plug in any gameboy game cartridge. Will play any non color gameboy game
by inserting the game into the cart and into the SNES and turning on. Allows multiple setting modifications in game and a prized collectors item for
all Gameboy and Nintendo enthusiests. Will accept flashcarts such as the EZ Flash JR but wont have SGB enhanced features unfortunately. 
Super gameboys are region locked so you cannot for example use a Super Famicom Super Gameboy, with a PAL SNES, however for between Japan and US 
regions may be compatible. Further research required.

2. Super Gameboy 2: The updated Super gameboy only released in Japan therefore region locked to those compatible consoles. Runs games at correct clock speed
and includes a link cable port to allow playing multiplayer as well as updated new borders.

3. The Gameboy Player: An attachement to the Gamecube that allows playing any Nintendo Gameboy family games.

## GAMEBOY PLAYER

The gameboy player is the second device other then the Super Gameboy officially released by Nintendo for public consumers to play Gameboy family games
on their TV. This accessory attachement which plugs into the base of the Gamecube allows playing any Nintendo Gameboy, Gameboy Color and Gameboy advance game cartridge,
even the rumble and gyroscope games. It also plays Gameboy games at the correct clock speed as it actually uses original gameboy advance hardware inside.

How it lacks the SGB enhanced features for Gameboy color games, and lacks abilities to customise borders and have many UI elements. It however does come with it's
own pack of borders.

It requires both the base hardware which is region free but not the required startup disc which is region locked. So you
can buy and attach any regions Gameboy Player base hardware to any region gamecube, but the startup disc has to match the Gamecube's region. The discs are also
very expensive to collect as they broke more often then the hardware.

Read full review guide here: https://forums.atariage.com/topic/29001-game-boy-player/

## GAMEBOY CAMERA

Gameboy included a camera game cartridge that had a swivelable lens that could take front selfie and back photos. Many aftermarket
versions exist to transplant the electronics into smaller or larger lens game shells but they forgoe the selfie front camera capability.

### TAKE COLOR IMAGES WITH TRICHROMATIC PHOTOGRAPHY

An video here: https://www.youtube.com/watch?v=vA125ypMdJ0
shows how to use filters to create color images. Possibly something to physically add to the Gameboy camera cartridge

### EXTRACT PHOTOS

Besides using a traditional Gameboy printer to physically print the photos, you can instead download digital copied of the photo files
by following steps below;

Step 1. Use a Game ROM backup hardware such as: INSIDEGADGETS GBXCART RW
Step 2. Connect game to the ROM backup hardware and connect it to a computer
Step 3. Install and start software "FlashGBX" 
Step 4. Click to read game's ROM dump. It will give options to save the images to your desktop/drive

## GAMEBOY PRINTER

A Gameboy printer is not the only device that can extract/print Gameboy camera photos. Images can be extracted by connecting any rom dumping hardware e.g, "INSIDEGADGETS GBXCART RW"
to your computer, and opening the .sav file with ope source trusted software here: https://github.com/MattGrayYes/GBCameraDump
to download the photos.

An exact dimension alternative to the official Gameboy printer paper exists called the: Seiko S-950 (example: https://www.youtube.com/watch?v=8CpA6znIkq0)

## PRO ACTION REPLAY

Pro action replay (PAR) is a game cartridge that has a slot to insert any gameboy or color game to allow inserting cheats into the games RAM. This works by 
users searching for known cheat codes in a game from the Pro action replay manual to insert before the game starts such as more in game lives, or more difficult enemies.

Modern aftermarket multicart flashcarts often support cheat codes without needing seperate hardware.

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

# ROMS

All gameboy family consoles, games and accessores are region free. However games language is default to the region e.g, Japanese cartrdige games use Japanese language.
Therefore you can use any game/ROM in any system.

ROM is read only memory. Cartridge based consoles such as old Sega Megadrives, or Gameboys used physical game cartridges which contained memory modules that held all the game code 
and when dumped meaning copied digitially from the catridge such as to a computer the resulting file is referred to as a ROM.

CD based consoles use disc images that have been ripped from the CD and can be in many formats such as .bin/.cue, .img, .chd, .rvz, .zso and many others. They are the same thing
conceptually as a ROM when it comes to a digital copy of a physical game.

There are 2 methods of getting roms dumping using hardware (see accessories) or downloading from online. Once you get the ROMS you can add them to a flashcart and then play them on real hardware

You can backup ROM saves using the dumping method also.

## TV REMOTE CONTROL | IR REMOTE

The Gameboy color came with a Infrared Receiver (IR) that was used by a specific game "Mission Impossible" to be able to use the Gameboy color as an TV Remote control.
Instead of buying or downloading the game instead a modder has created an ROM of the same software so that you can download it to flashcart and use it.
You can download the ROM from this link: https://bluecop.itch.io/gbc-remote

You need the remote control associated to the TV or a preprogrammed one, as the gbc-remote app copies the existing remote's buttons.

To use;

1. Start game rom "gbc-remote"
2. use "SELECT" button on gameboy to navigate to a page with a button you want to program e.g, press SELECT until you can see the "POWER" button on gameboy screen
3. Press "START + SELECT" on the gameboy, the gameboy screen will turn RED 
4. Then press the POWER button on the gameboy and the gameboy POWER button will turn RED.
5. Face the gameboys IR port to the remote control IR light
6. press then POWER button on the remote control. If successfull the power button on the gameboy will immediately change from Red to white indiating the button programmed.
7. Press the START and SELECT button to exit the LEARNING MODE and the gameboy game screen will go back to white. Now test the power button works on the gameboy remote app
by facing the TV and pressing it. The TV should switch off. If successfull repeat for all other buttons. You can program many buttons at once without exiting LEARNING MODE for a single page.

# FLASHCARTS

Flashcarts refer to 2 differnt related things.

1. An empty cartridge for use with adding a custom game ROM in, such as if you develop your 
own game or want to download a ROM hack into it to play on hardware
2. A Multi-game cartridge that usually has an OS and holds multiple games with usually an external 
storage such as MicroSD where you load multiple ROMS in it to play on hardware

You can load your own games (either your official game cart ROM Dumps, or homebrew ROM games) onto these devices to play on physical consoles.

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

When buying a flashcart ensure it has the hardware to support the ROM, e.g. a FRAM chip will support saving, or an Cell battery will support RTC so you can add ROM hacks of games that require RTC or FRAM on them.

USB-C or other related access directly to the gameboy cartridge allows programming on the go so you can easily add your own games to it without external hardware required for dumping/flashing.

Rumble feature flashcarts - https://shop.insidegadgets.com/product/gameboy-4mb-32kb-fram-flash-cart-ultra-low-power/

If unsure this link describes the differences in Flashcarts you need to add games to them - https://shop.insidegadgets.com/choosing-a-flash-cart/

## MULTI-CARTS

The list of multicarts used for adding multiple roms to play games on real hardware are all below.

1. Everdrive G3
* uses SRAM saving
* Plays gb/gbc roms
* includes Game Genie codes
* High quality
* power/battery saving
* full SGB compatability

2. Everdrive G5
* Same as G3
* uses FRAM saving
* Includes save state

3. Everdrive G7 - best flashcart for non GBA models
* Same as G5
* Includes RTC

4. EZ Flash jr 
* same G3
* uses PSRAM - a power hungry consumption non-volatile RAM
* includes RTC
* No cheats
* requires restart and confirmation to save
* No SGB compatability as of v1.04e. Use this custom kernel at own discretion see: https://gbatemp.net/threads/nitro2k01s-sgb-enabler-for-ez-flash-jr.592961/

5. Everdrive GBA mini
* Same as G7 
* Supports gba games/nes/sega master system/game gear ROMS
* Uses an emulator (Goomba/Jagoomba) to play GB games therefore cannot use widescreen, or colorise old GB games as feature tied to authentic hardware firmware on GBC/GBA models however does come with advantages such as using speed/turbo in game etc.,

6. EZ Flash Omega Definitive edition - best flashcart for GBA
* Same as G7
* Supports gba games/nes/sega master system/game gear ROMS and many more with installable third party emulators etc., (see GBATemp SimpleDE custom theme for more details)
* FRAM saving
* requires restart and confirmation to save
* Includes Slot2 features (GBA to DS trading/multiplayer, RAM Expansion, Rumble mode)
* Advanced computer like UI with ability to read many file types e.g, TXT, BMP, JPG etc., with proper file storage
* Game thumbails
* Customisable UI (see GBATemp SimpleDE custom theme for more details)
* Uses an emulator (Goomba/Jagoomba) to play GB games therefore cannot use widescreen, or colorise old GB games as feature tied to authentic hardware firmware on GBC/GBA models however does come with advantages such as using speed/turbo in game etc.,

### Everdrive G7 SETUP

CHEATS: Gameshark modifies the RAM whilst Game Genie modifies the ROM, and the Everdrive can't access the Gameboy's RAM. Thus only Game Genie codes are available.

TBA

### EZ FLASH JR SETUP

* To set sleep mode, enable from settings, then note the key combination below (default: L, R, Select), boot a game with addon then press the former sleep combination
to set the GBA to sleep and conserve battery. To wake press START + SELECT together
* To reset back to main menu from game you can press down on the cartridge while running a game and you will feel a click then let go.
* The battery is not used for saving. It's only used for clock functions in game such as Pokemon Crystal's 24 hour timer. It's not necessary to replace unless
you play a game that requires 24 hour in game clock
* To save game first save in game then restart the flashcart by clicking on it. When device reboots you will be prompted to press (so press) the A button to save
the game to the MicroSD card in the /SAVER folder. You can then plug your MicroSD card into your computer in the future and copy the save file to backup if you wish.
This also means you can take your saves everywhere with you even if the Flashcart dies.
* To use on a Super Gameboy plug it in as normal and press the reset button twice, you will see logo change each time
* Cannot play Gameboy Advance roms if plugged into a Gameboy Advance.
* If you're using this flashcart on a GBA model note that the GBA will output a smaller then normal screen which isn't ideal.
* To use with a Super Gameboy connect it and power the snes on, then press the reset button once until the "Super" logo appears, then press again to get it to boot to menu.
* No SGB compatability as of v1.04e. Use this custom kernel at own discretion see: https://gbatemp.net/threads/nitro2k01s-sgb-enabler-for-ez-flash-jr.592961/
* A bonus feature of a flashcart is the MicroSD card can be used as a storage for files. So you can keep text files/documents of your favourite game guides etc.,

#### EZ FLASH JR UPDATE FIRMWARE

1. To update to latest firmware click visit here and click the Download link under EZ-FLASH junior: https://www.ezflash.cn/download/
2. copy the 2 files "ezgb.dat" and "Update_FWx.gb" (where "x" is the latest version) to your MicroSD card
3. Copy all game roms into the MicroSD card. You can organise them into folders if you wish.
3. Add the MicroSD card to flashcart, insert into gameboy power on and click on the "Update_DWx.gb" file and click A and wait for the update to finish
i will ask you to power off, wait a minute and if it doesn't auto restart the software power off then on again which will take you back to main screen.
5. Test a game and if it works connect the MicroSD card back to your computer and delete the "Update_DWx.gb" file as it's no longer needed

### EZ FLASH OMEGA DEFINITIVE EDITION SETUP

1. Download the kernel file from here: https://www.ezflash.cn/download/
2. Format the microSD card to exFAT
3. Extract above folder and move the ezkernelnew.bin to the root of your microSD Card
4. Put the microSD card into your EZ Flash Omega Definitive Edition and put inside a Gameboy Advance
5. While booting hold down the R key. It should start installing the latest firmware and create a SAVER folder.
6. Remove the flashcart and place the mircoSD card back into your computer and delete the ezkernelnew.bin and SAVER files
7. Follow the offical thread link here to download SimpleDE.zip: https://github.com/Sterophonick/omega-de-kernel
8. Extract the following files from SimpleDE.zip into the root of your microSD card.
    * ezkernelnew-dark.bin (or light theme if you desire) and
    * SYSTEM 
    * BACKUPfolder
9. Then rename and remove the suffix "-dark" or "-light" from new kernel file to just ezkernelnew.bin
10. Download the cheats and thumbnails from this link https://www.ezflash.cn/download/ 
11. Unzip IMGS.zip and omegacheatlibrary.zip
12. rename omegacheatlibrary to CHEAT
13. Drag both IMGS and CHEATS into /SYSTEM folder in the MicroSD card
14. Insert the MicroSD card into the EZ Flashcart and place into the GBA then flash again by powering device on and holding R
15. Turn off and now add your ROM folders.
16. Place card and cart back in and enjoy your games

#### TROUBLESHOOTING EZ FLASH OMEGA DE

All troubleshooting answers are officially found here: https://gbatemp.net/threads/basic-repair-guide-of-current-ez-flash-products.601332/

White screen when booting game error - Are you playing a ROMHack? Make sure you applied the hack to the
correct region version of the game! Test the ROM on a normal emulator first and see if the same issue appears
https://visualboyadvance.org/download/vba-m/

#### OMEGA & OMEGA DEFINITIVE EDITION BOOTLOADER RECOVERY

FULL STEPS HERE: https://www.ezflash.cn/zip/recovery-en.pdf

1. Download and extract Recovery Image "omega-recovery.img" - https://www.ezflash.cn/zip/recovery-en.pdf
2. Download and install Win32 Disk Imager - https://sourceforge.net/projects/win32diskimager/
3. Connect microSD card to the PC
4. Choose omega-recovery.img and the microSD disk label.
5. Click Write .
6. Click YES if a warning window pop up.
7. After the write process done, press OK .
8. Put the microSD into OMEGA, and put OMEGA into game console, power up it.
9. Select Update BOOTLOADER
10. At error initialising SD Card remove SD card place in computer and follow original setup

# GAMES TO PLAY

Here is a author picked variety list of ~60 of the most popular, interesting, technically impressive, historically significant, rarest games and modded/hacked versions of
existing games for the Gameboy and Gamboy Color to collect. You can also find new games being made for Gameboy all the time such as on Itch IO here: https://itch.io/games/tag-gameboy-rom Try searching the Internet for "new gameboy games" and try a few out, a author suggestion is new game "The Machine" found here: https://themachinegame.com
Note some of the games below are hard to track down but Japanese copies are always cheaper so look online for them.

* Alleyway
* Battle City
* Castlevania Legends
* Cave Noire
* Densha de Go! 2
* Dr. Mario
* Dragon Warrior III
* F-1 Race
* Final Fantasy Adventure
* Game & Watch Gallery
* Game de Hakken!! Tamagotchi 2
* Ghosts 'N Goblins
* Kaeru no Tame ni Kane wa Naru
* Kirby's Dream Land 2
* Kirby's Dream Land
* Kirby's Pinball Land
* Konami GB Collection Vol.1
* Konami GB Collection Vol.2
* Konami GB Collection Vol.3
* Konami GB Collection Vol.4
* Legend of the River King
* Golf
* Tennis
* Mega Man 3
* Mega Man 5
* Mega Man Dr. Wily's Revenge
* Mega Man II
* Metal Gear Solid
* Metroid II - Return of Samus
* Mole Mania
* Nekketsu Kouha Kunio-kun Bangai Rantou Hen | Double Dragon 2
* Pocket Bomberman
* Pokemon - Blue Version
* Pokemon - Crystal Version
* Pokemon - Red Version
* Pokemon - Yellow Version - Special Pikachu Edition
* Pokemon Pinball
* Pokemon Trading Card Game
* Pop Up
* Prince of Persia
* R-Type DX
* Resident Evil Gaiden
* Resident Evil GBC
* Sakura Wars GB
* Shadowgate Classic
* Super Mario Land 2
* Super Mario Land
* Survival Kids
* Tamagotchi
* Tetris
* The Final Fantasy Legend
* The Legend of Zelda - Link's Awakening DX
* The Legend of Zelda - Oracle of Ages
* The Legend of Zelda - Oracle of Seasons
* Trip World
* Wario Land - Super Mario Land 3
* Wario Land II
* X


# HACKING ROMS | ROMHACKS

To hack a ROM e.g, to play fun user modifications to the original games like different colors, sounds, music, gameplay etc.,
1. first download Lunar IPS - https://www.romhacking.net/utilities/240/
2. On the same website or anywhere find the hack you want and download it
3. use Lunar IPS to target the IPS romhack file on the correct region ROM and click apply IPS patch
4. Done try the game out on a software emulator first before playing on real hardware to rule out
any issues - https://visualboyadvance.org/download/vba-m/


# PROGRAMMING

## CHECKSUMS | CRC-32

Checksums are a means of validating a digital file by examinig all the bytes/data of a file and using a CRC-32 a mathamatical formulae. There are different formulaes to use such as CRC-32, SHA1, or MD5 each with their own pros and cons listed below in order from best top to worse bottom.

SHA-256: Part of the SHA-2 family, it is much more secure and is increasingly recommended for cryptographic security.

SHA-1: More secure than MD5, but still vulnerable to certain attacks; it's also used for checksumming but is being phased out for sensitive applications.

MD5: Originally designed for checksums, it’s now often considered insecure against deliberate alterations but is still 
used for checksums in many applications due to its speed.

CRC-32: Good for detecting simple errors, fast, but not as secure against intentional tampering.

SUMMARY
Best for security: SHA-256
Decent for general use: SHA-1
Fast but insecure: MD5
Good for basic error-checking: CRC-32

### CRC-32

CRC-32 is a type of checksum which is a means of validating a digital file by examinig all the bytes/data of a file and using a CRC-32 a mathamatical formulae to come up with a value which defines a file. E.g, a ROM dump of "Tetris" for Gameboy will have a CRC-32 of the below depending on the region of the game;

* Tetris (World) (Rev 1) CRC-32: 46df91ad
* Tetris (Japan) (En) CRC-32: 63f9407d

So when the original game ROM file is altered/hacked e.g, for adding color to the game, or creating custom borders for Super Gameboy use, the CRC-32 will calculate a different value.

This creates a means of testing the originality of a file, and also track down variations of it.

This website https://emn178.github.io/online-tools/crc32_checksum.html can be used for drag and dropping any digital file such as "Tetris" for Gameboy and finding the CRC-32 value. E.g, 46df91ad . This number coresponds to the ROM I have copied is the original World region version as per above.

## CREATING A GAMEBOY GAME

There are 2 methods to program on gameboy for creating game roms either using GUI software such as "GB Studio" https://www.gbstudio.dev/ or programming yourself (hardcoding).

There are 2 languages to program Gameboy games in with mature development frameworks that can be implemented without too much difficulty Assembly (ASM) or C (No C++ as it's difficult for the onboard chip and c++ is too bloated)

### PROGRAMING WITH C

There are several courses to choose from to learn how to program on Gameboy using the C language. Try watching all to learn different methods
at coding

Course 1. CREATING FIRST HELLO WORLD ROM - https://www.youtube.com/watch?v=HIsWR_jLdwo
Course 2. https://www.youtube.com/watch?v=eYT9s9bvKYU

### PROGRAMMING WITH ASSEMBLY (ASM)

For those looking for a challenge, or simply want to program how the original gameboy games were mad, pushing the limits of the software, see the below courses to program in Assembly.

Course 1 - https://www.youtube.com/watch?v=Tn1rFUutkdo&list=PLp_QNRIYljFrNLNhKgIZQjMM9eaZd166O
