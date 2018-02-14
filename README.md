# Super NT Jailbreak

Custom "*Jailbreak*" firmware for the [Analogue Super
NT](https://www.analogue.co/pages/super-nt/) that allows loading ROMs
from the SD Card slot.

## Updating Firmware 

Place the firmware file `snt_firmware_verJB6.4.bin` into the root
directory of your SD card. Be sure the card is formatted as
[FAT32](https://en.wikipedia.org/wiki/FAT32) and that there is only
one firmware file in the root directory.

## Organizing ROMs

Create a folder called `SNES` at the root of your SD card. Drop all
your folders and subfolders of ROMs in here.  The system will default
to here, but if `/SNES/` does not exist, it will then default to the
root directory of the SD card.  There is a limit to how many files can
be in each directory which varies by the length of the filenames.
This equates to around 300-500 files depending on the length of the
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
said cartridge and it will find the updated saves.

It is a good idea to backup your saves before using this firmware.

When the game is exited back to the menu, it will write the save game
automatically to the SD card.  So to save your progress, be sure to
return to the file menu before turning the system off if you wish for
it to save your progress.

## Cores Supported

`SNES/SFC`

## Changelog

- JB6.4 2018-02-14 Initial release: Happy Valentine's Day :heart:
