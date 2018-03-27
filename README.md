# Super NT Jailbreak

Custom "*Jailbreak*" firmware for the [Analogue Super
NT](https://www.analogue.co/pages/super-nt/) that allows loading ROMs
from the SD Card slot and an expanded featureset. 

## Updating Firmware 

Format a 2GB (or larger) SD card as
[FAT32](https://en.wikipedia.org/wiki/FAT32) (FAT16 and exFAT are not
supported). In Windows, you must use a tool for cards larger than
32GB, such as
[fat32format](http://www.ridgecrop.demon.co.uk/index.htm?guiformat.htm).

Place the firmware file
[snt_firmware_verJB6.6.bin](https://github.com/SmokeMonsterPacks/Super-NT-Jailbreak/releases/download/v6.6/snt_firmware_verJB6.6.bin)
into the root directory of your SD card.  Be sure that there is only
one firmware file there.  Insert the card into your Super NT and power
on. The firmware will be flashed to the console. This process may
take a few minutes.

While the firmware is flashing the LED will turn red and flicker,
followed by a considerable pause and HDMI signal blackout.  Do not
power off.  The main menu will boot when it has finished. Delete the
firmware file from your card after flashing.

The SNT is protected from bricking as a result of firmware updates,
but please still follow the above precautions to be safe. 

## Organizing ROMs

Create a folder called `SNES` at the root of your SD card, and drop
your folders and subfolders of ROMs inside (see [SmokeMonster's
database](https://github.com/SmokeMonsterPacks/EverDrive-Packs-Lists-Database)
for a curated [list of valid SNES
ROMs](https://github.com/SmokeMonsterPacks/EverDrive-Packs-Lists-Database/raw/master/EverDrive%20Pack%20SMDBs/Super%20EverDrive%20%26%20SD2SNES%20SMDB.txt)).
The system will search for ROMs in the `/SNES/` folder first, or the
root directory of the SD card if there is no `/SNES/` folder.  The
maximum number of files (ROMs and subfolders) that can be placed in a
given folder is around 300-500, depending on the length of the
filenames.

## Running ROMs

Select **browse SD card** from the main menu.  Hit **enter** on a
filename to run it, or if it's a subfolder, it will enter said folder.
The menu hotkey will return to the file menu from the game.

## Saves

Saves will go into `/SAVES/SNES/` by default.  You can directly place
an [SD2SNES](http://sd2snes.de/) or [Super
Everdrive](https://krikzz.com/store/home/13-super-everdrive-v2.html)
SD card in, and it will properly detect this by checking for the
requisite save game folders, in this order:

- `/SAVES/SNES/` (default)
- `/SPED/SAVE/` (Super EverDrive)
- `/sd2snes/saves/` (SD2SNES)

The Super Everdrive uses a 32-kilobyte long save file no matter what,
and is padded.  This functionality is retained.  It should be possible
to swap your SD card into the unit from your SD2SNES or Super
EverDrive and the saves will work fine, then it can be put back into
said cartridge and it will find the updated saves (with a `.sav` file
extension, other extensions are not recognized).

NEVER insert or remove cartridges while your SNT is powered on. Doing so
may risk damaging the console and/or losing saves. It is good practice to 
backup saves before updating firmware.

When a game is exited to the menu, it will prompt you to save. Return to
the file menu and save your progress before powering down.

## Changelog
- [JB6.6](https://github.com/SmokeMonsterPacks/Super-NT-Jailbreak/releases/download/v6.6/snt_firmware_verJB6.6.bin) 2018-03-27:
  - All official v4.5 fixes plus:
  - Added CopySNES. Lets you dump carts/save RAM to the SD card. Files 
    are placed into /COPYSNES/. The directory is created if it does not
    exist. See the [text](https://github.com/SmokeMonsterPacks/Super-NT-Jailbreak/releases/download/v6.6/CopySNES.Instructions.txt)
    file for full instructions.
  - Star Ocean 96mbit works now.
  - Changed menu operation so that if you enter the settings menu in the
    file browser, it can be exited back to the file browser by hitting select (or backing all the way out using the back button).
  - Changed file browser operation so that if you attempt to back out of it, 
    you get warned that the running game will be ended and you cannot save any more.
  - In JB mode, `tools` menu appears on the main menu which has copysnes and cheat codes.
  - `Cheat codes` in moved into the file browser settings menu.

- [JB6.5](https://github.com/SmokeMonsterPacks/Super-NT-Jailbreak/releases/download/v6.5/snt_firmware_verJB6.5.bin) 2018-03-04:
  - includes all fixes from official firmware v4.4, which should
    solve most DMA-related random crashes
  - adds a `menu bounce` option (reinstated)
  - adds a new `Save?` dialog box
  - fixes both SRAM bugs (firmware 6.4 only saved once and had a nasty
    corruption bug). Please test it again so we can be sure the save
    functionality works as expected. Any save made on the jailbreak
    firmware 6.4 should be considered as potentially corrupted and
    must be discarded
  - fixes glitch with some games disabling the `return to menu`
    shortcut
    
- [JB6.4](https://github.com/SmokeMonsterPacks/Super-NT-Jailbreak/releases/download/v6.4/snt_firmware_verJB6.4.bin) 2018-02-14 Initial release: Happy Valentine's Day :heart:

## Known Issues

- game-specific [bugs](https://github.com/SmokeMonsterPacks/Super-NT-Jailbreak/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+glitches)
- hotkey problems with 8bitdo receiver [#12](https://github.com/SmokeMonsterPacks/Super-NT-Jailbreak/issues/51)
- hq2-4x scaler settings slightly change the color pallet [#78](https://github.com/SmokeMonsterPacks/Super-NT-Jailbreak/issues/78)
- using `BACK` to exit SD browser while in-game breaks functionality of select button [#6](https://github.com/SmokeMonsterPacks/Super-NT-Jailbreak/issues/6)
- using `BACK` to exit SD browser while in-game breaks save function [#48](https://github.com/SmokeMonsterPacks/Super-NT-Jailbreak/issues/48)

## Cores Supported

`SNES/SFC`

## Problem Reporting and Community Chat

The custom firmware is not coded by
[SmokeMonsterPacks](https://github.com/SmokeMonsterPacks) or
[frederic-mahe](https://github.com/frederic-mahe), but please do
report problems here at Github for support. Priority will be given to
jailbreak-specific problems (using ROMs through the SD card slot
rather than through the cartridge slot). You can join the [discord
server](https://discord.gg/EX57xnF) if you want to chat with the Super
Nt community.

Use at your own discretion. We are not responsible for any damage 
or data loss caused by custom firmware installation or use.
