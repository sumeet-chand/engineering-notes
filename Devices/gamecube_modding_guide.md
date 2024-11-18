
# GAMECUBE MODDING GUIDE

* By: Sumeet Singh @ sumeet-singh.com
* Created: October 2024
* Version: 1.0 (October 2024)
* Description: This document outlines various ways to repair and mod your gamecube including playing backups of Gamecube game roms or setup
Gameboy Interface to allow upscaling of Gameboy games to play on your TV. The purpose was to bring life to our old childhood consoles. 
I do not condone piracy nor performing any activity that renders breaking a EULA or Terms and conditions contract between a product vendor 
and customer. I recommend to buy official licensed games and hardware.

# TABLE OF CONTENTS
- [1. REQUIREMENTS](#requirements)
- [2. TERMINOLOGY](#terminology)
- [3. REPAIRING](#repairing)
- [4. MODDING](#moddingy)

# TERMINOLOGY
TF Card = Trans Flash card. The old name of SD cards, before it was standardised. They refer to the same thing.
SDGecko = An old device which can be substituted for any clone device from Aliexpress, but it's slow and best
to use the Serial port 2 device
Action Replay disc + exploit: Old exploit method. The discs are rare and expensive. Don't bother with this option.

# REPAIRING

## REPLACE BATTERY

See gallery here: https://imgur.com/a/gamecube-clock-battery-replacement-Ydxo96l

See this video on how to replace the battery: https://www.youtube.com/watch?v=Gj-l_o7hY8Y

If an error message on gamecube appears that date/time has reset it's best time to change your Gamecubes battery.
Open up and desolder the existing, and replace with a CR2032 cell holder with pins and insert a CR2032 battery and done.

# MODDING

## REQUIREMENTS
* DOL-001 - original gamecube with the digital AV port
* Buy a memory card from eBay with the below game exploit for your region preconfigured. Contact seller to ask.
The memory card will have the hacked game + Swiss installed on it. Swiss is the new Gamecube OS you will use.
* An game to exploit of any region, in this case Zelda Wind walker
* MicroSD Card at least 32GB FAT32 formatted
* A serial port 2 MicroSD card adapter e.g, SD2SP2 Pro ($15 AUD from amazon.com)
* A memory card of black size and up

# SWISS EXPLOIT STEPS
1. Follow this video https://www.youtube.com/watch?v=1mZQeCzvy6E&t

## PLAY BACKUP GAMES AND ROMS
1. Add .iso or .nkit.iso roms to FAT32 formatted MicroSD card, 
2. connect to SD2SP2 or similar device
then connect to serial port 2 underneath your device ensuring it's an original DOL-001 model Gamecube.
3. Boot into swiss using any exploit method as above, then change to MicroSD folder and play any game

## GAMEBOY INTERFACE SETUP

If you want to play Gameboy games on your display such as a TV with your original saves also, you can plug in your cartridge
into a Gamecube accessory called a Gameboy player, which outputs the games display to the TV/screen allowing you to also
use bonus analog controls, change borders, and have other fun features. You can also play flash carts such as EZ flash series 
with the Gamecube Player and Interface.

However this requires the use of both the hardware and the expensive Gameboy player disc that's region locked.

If you don't have a Gameboy player disc and dont want to purchase due to rarity and cost, you can use Gameboy
Interface which is a homebrew software run through Swiss that allows mimicing the Gameboy player disc functionality.
It also adds more functions with allowing upscaling not present in the former disc meaning it's the definitive way
to play Gameboy family games on a external monitor/TV.

Remember if your Gameboy player disc is scratched you can always have it rebuffed which is a professional job
for at least $10 AUD that a professional just removes a extremely thin layer of the disc to make it perform better.
It's not an issue if it's done once, but multiple times can cause it to be brittle, but it's a suggestion if you
want to just keep using the disc for authenticity.

Gameboy interface is a folder and files placed on the MicroSD card device connected to serial port 2.
Once you boot using the game exploit into Swiss menu, you can navigate to the MicroSD card and just run GBI.
Full steps are here: https://www.youtube.com/watch?v=6LBdHJ8xpv8&t

1. Plug in any gameboy game into the Gamecube
2. Click download main package here: https://www.gc-forever.com/wiki/index.php?title=Game_Boy_Interface
3. Extract the folder, copy the app folder into the MicroSD card and connect to the Gamecube e.g, using a Serial port 2 adapter as above
4. Plug into your gamecube, boot into swiss using exploit steps above, then navigate to the MicroSD app folder card start the relevant .dol executable.
The wiki shows the 3 versions
standard (gbi.dol) = Standard best for lcd/oled but also works fine with CRT
speedrunning = best for crt however untested by author
high-fidelity = best for use with upscalers however untested by author
5. The game will now start in the best picture quality mode then what the standard Gameboy Player disc coul ever produce.

## ZOOMING + CHANGING DISPLAY OFFSET

Using the Gamecube controller press X then press either L or R to zoom in or out. This way you can fill the entire contents of the display.
If the game is offset, press the X button and the directional pad in any direction to change the offset then press B or X again to cancel.
