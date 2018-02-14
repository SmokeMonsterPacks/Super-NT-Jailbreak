# Super-NT-Jailbreak
Custom "jailbreak" firmware for the Analogue Super NT that allows loading ROMs from the SD Card slot.

JB6.4
2-14-2018

Loading ROMs - Create a folder called /SNES/ on your SD card. Drop all your subfolders and folders of ROMs in here.  The system will default to here,  but if /SNES/ does not exist, it will then default to the root directory of the SD card.  There is a limit to how many files can be in each directory which varies by the length of the filenames.  This equates to around 300-500 files depending on the length of the filenames.

Running ROMs - Select "browse SD card" from the main menu.   Hit "enter" on a filename to run it, or if it's a subfolder, it will enter said folder.  The menu hotkey will return to the file menu from the game.

Saves will go into /SAVES/SNES/ by default.  You can directly place an sd2snes or Super Everdrive SD card in, and it will properly detect this by checking for the requisite save game folders.

It will use these folders in this order, if found:

/SAVES/SNES/    (default)
/SPED/SAVE/     (everdrive)
/sd2snes/saves/ (sd2snes)

The Super Everdrive uses a 32K long save file no matter what, and is padded.  This functionality is retained.  It should be possible to swap your SD card into the unit from your sd2snes or Super Everdrive and the saves will work fine, then it can be put back into said cartridge and it will find the updated saves.

It is a good idea to back up your saves before using this firmware.

When the game is exited back to the menu, it will write the save game automatically to the SD card.  So to save your progress, be sure to return to the file menu before turning the system off if you wish for it to save your progress.

Updating Firmware - Place the .bin file into the root directory of your SD card. Be sure the card is formatted as FAT32 and that there is only one firmware file in the root directory.

Changelog -

JB6.4:
Initial release
Happy Valentine's Day <3
