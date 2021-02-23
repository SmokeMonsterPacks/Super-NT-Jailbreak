# Super Nt Jailbreak

Custom "*Jailbreak*" firmware for the [Analogue Super
Nt](https://www.analogue.co/pages/super-nt/) (regular and *ghostly*
models) that allows loading ROMs from the SD Card slot and an expanded
featureset.

## Updating Firmware 

Format a 2GB (or larger) SD card as
[FAT32](https://en.wikipedia.org/wiki/FAT32) (FAT16 and exFAT are not
supported). In Windows, you must use a tool for cards larger than
32GB, such as
[fat32format](http://www.ridgecrop.demon.co.uk/index.htm?guiformat.htm).

Unzip
[snt_firmware_verJB7.0zip](https://github.com/SmokeMonsterPacks/Super-NT-Jailbreak/blob/master/firmware/snt_firmware_verJB7.0.zip)
into the root directory of your SD card.  Be sure that there is only
one firmware file there.  Insert the card into your Super Nt and power
on. The firmware will be flashed to the console. This process may take
a few minutes.

While the firmware is flashing the LED will turn red and flicker,
followed by a considerable pause and HDMI signal blackout.  Do not
power off.  The main menu will boot when it has finished. Delete the
firmware file from your card after flashing.

The Super Nt is protected from bricking as a result of firmware
updates, but please still follow the above precautions to be safe.

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

NEVER insert or remove cartridges while your Super Nt is powered
on. Doing so may risk damaging the console and/or losing saves. It is
good practice to backup saves before updating firmware.

When a game is exited to the menu, it will prompt you to save. Return to
the file menu and save your progress before powering down.

## CopySNES

[CopySNES](https://github.com/SmokeMonsterPacks/Super-NT-Jailbreak/releases/download/v6.6/CopySNES.Instructions.txt)
backs up (AKA "dumps") cartridge ROMs and save RAM to the SD card.

<details>
  <summary>Click to expand full CopySNES instructions</summary>
<BR>

CopySNES is designed to be an easy to use way to back up cartridge
ROMs and save RAM data. Most types of cartridges are supported, and if
it isn't specifically supported or for some reason the cartridge
header is bad, the settings can be changed.

How to use it:

* Power the system off
* Insert cartridge
* Power the system on
* Select `CopySNES` on the tools menu

At this point, CopySNES will query the cartridge and grab the header
and attempt to detect what kind of cartridge it is.

You have two options at this point:

1. hit `enter` to accept the settings and proceed to saving.
2. hit `start` to edit the detected settings

(note: editing the name will happen during the save step, skip to
`filename entry` below)

If you wish to edit the settings, use `up` and `down` to select one of
the settings, then use `left` and `right` to adjust it. You can select
between 32 kilobytes and 16 megabytes of ROM to dump, and between 0
(i.e. none) and 32 kilobytes of RAM.

Finally, you can select the type of mapper it is, i.e. LOROM, HIROM,
EXHIROM, or EXLOROM. There is also a `FLAT` setting which will let you
dump the entire SNES cartridge space if desired. `FLAT` starts at
address 00:0000 and will dump the specified amount of memory.

While you can dump say, 8 megabytes of LOROM or HIROM, doing so most
likely won't be very useful.

This `manual` mode is useful when dumping things that do not have a
valid or any header such as the *Game Genie* BIOS (it reports 0 kilobyte
of ROM and is actually 64 kilobytes) or the *Sufami Turbo* (again, it
reports 0 kilobyte of ROM even though it's really 1 megabyte).

When you are done adjusting the settings, and are ready to dump, hit
`select`.

Filename entry:

At this point the filename can be edited.  It will directly copy the
ROM header name in here. For some Japanese titles, there may be no
valid ASCII characters in the header (or if there's no header at all)
so any invalid characters for a filename are replaced with spaces. If
there's no name at all, it will default to "GAME".  Use `up`/`down` to
change the character's value and `left`/`right` to select a
character. Press `enter` to accept the filename and begin the dumping
process.

The game's actual size will be determined at this point (i.e. a
2-megabyte game reported in the header might only be 1.5 megabytes, so
this will be detected now).

Finally, the ROM and RAM are dumped to the SD card.

Now that the dump is complete, you are returned to the tools menu. The
system can be powered off and a new cartridge inserted to dump, and so
on until all the carts are dumped that you wish to dump.

The following things have been tested:

* LOROM   (ROM + RAM)
* HIROM   (ROM + RAM)
* EXHIROM (ROM + RAM)
* SDD-1   (ROM + RAM)
* SA-1    (ROM + RAM)
* CX4     (ROM)
* DSP1-4  (ROM + RAM)
* S-RTC   (ROM,  RAM is dumped but it is unknown if it works)
* ST010   (ROM)
* ST011   (ROM)
* ST018   (ROM)
* OBC-1   (ROM + RAM)
* SPC7110 (ROM + RAM, but RAM has not been verified to work)
* GSU-1/2 (ROM + RAM)

(note: for SuperFX (GSU), the RAM is always dumped as 64 kilobytes.
This is because games such as *Yoshi's Island* have RAM, but the
headers for all the games show 0 kilobyte of RAM.  This 'larger' RAM
will work with the major emulators, and can be trimmed down later if
needed.)


Note: Testing with `no$sns` it will not use the saves on certain games
such as *Chrono Trigger* I don't know why, the saves are good and work
on the Super NT itself.

</details>

## Fonts

Since Super NT firmware version JB6.9, the **System -> Font** menu allows you to select your own font in place of those which come with the console. The load font option will bring you to the file browser. If you have a directory called `/FONT/` at the root of your SD card, it will default to that directory to load a font file. The font must use an 8x8 text box and must be represented in binary in a 1-bit per pixel format. Each character will take eight bytes to represent in this format. The file must be 768 or 1024 bytes in size and use the extension .fnt. The characters in the file will have to start at ASCII 20 (space) and end at ASCII 7F (delete). Font files 1024 bytes in size will not show the first 32 characters which would be stored in the first 256 bytes of that file. A set of user-created fonts compiled by [Sho](https://archive.org/details/@zreport) is available [here](https://archive.org/details/shos-font-pack-v-3). Utilities to convert Analogue font files to/from bitmap files are available [here](https://archive.org/details/analogue-font-utilities).

## Changelog
- [JB7.0](https://github.com/SmokeMonsterPacks/Super-NT-Jailbreak/blob/master/firmware/snt_firmware_verJB7.0.zip) 2020-02-22:
 - Added SPD HDMI packet to identify as "Super Nt"
 - Added Dejitter checkbox added to suppress the shorter scanline every other frame
 - Added option to press start to skip the bootup sequence
 - Fixed video settings (scanlines, etc) not applying when running games
 - Fixed non-visble top scanline in HDMI
 - Fixed non-centered picture when horizontal/vertical position sliders are centered
 - Fixed Final Fantasy III (US)/Final Fantasy VI (Japan) graphics corruption bug
 - Fixed Final Fantasy V graphics bug
 - Fixed Bahamut Lagoon graphics bug
 - Fixed CX4 shifter for faster wireframe sequences in Mega Man X2 & X3

- [JB6.9](https://github.com/SmokeMonsterPacks/Super-NT-Jailbreak/raw/master/firmware/snt_firmware_verJB6.9.zip) 2019-08-09:
  - includes all fixes from official firmware v4.9:
    - Added user font loading
    - Added RGB sliders for standby colour
    - Added SPC player
    - Fixed top missing scanline
    - Added new scanline system
    - Added DAC
    - Added light gun support with DAC
    - L/R audio input on cartridge was flipped
    - Fixed "you cannot use a mouse with this game" on Panic Bomber World
    - Fixed Star Wars pausing bug
    - Many small fixes and changes
  - plus:
    - Added DSP1,2,3,4 support
    - Added OBC1 support
    - Added ST010, ST011 support
    - Added CX4 support
    - Sped up file loading
  
- [JB6.6](https://github.com/SmokeMonsterPacks/Super-NT-Jailbreak/releases/download/v6.6/snt_firmware_verJB6.6.bin) 2018-03-27:
  - includes all fixes from official firmware v4.5,
  - fixed: *Star Ocean* 96mbit works now.
  - changed menu operation so that if you enter the settings menu in
    the file browser, it can be exited back to the file browser by
    hitting select (or backing all the way out using the back button).
  - changed file browser operation so that if you attempt to back out
    of it, you get warned that the running game will be ended and you
    cannot save any more.
  - changed: `Cheat codes` is moved into the file browser settings
    menu.
  - added CopySNES. Lets you dump carts/save RAM to the SD card. Files
    are placed into `/COPYSNES/`. The directory is created if it does
    not exist. See the
    [text](https://github.com/SmokeMonsterPacks/Super-NT-Jailbreak/releases/download/v6.6/CopySNES.Instructions.txt)
    file for full instructions.
  - added: in jailbreak mode, `tools` menu appears on the main menu
    which has CopySNES and cheat codes.

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

- some [special-chip games](https://en.wikipedia.org/wiki/List_of_Super_NES_enhancement_chips#List_of_Super_NES_games_that_use_enhancement_chips) are not supported,
- game-specific [bugs](https://github.com/SmokeMonsterPacks/Super-NT-Jailbreak/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+glitches),
- hotkey problems with 8bitdo receiver [#12](https://github.com/SmokeMonsterPacks/Super-NT-Jailbreak/issues/51),
- hq2-4x scaler settings slightly change the color pallet [#78](https://github.com/SmokeMonsterPacks/Super-NT-Jailbreak/issues/78)

## Cores Supported

`SNES/SFC`

## Problem Reporting and Community Chat

The custom firmware is not coded by
[SmokeMonsterPacks](https://github.com/SmokeMonsterPacks) or
[frederic-mahe](https://github.com/frederic-mahe), but please do
report problems here at Github for support. Priority will be given to
jailbreak-specific problems (using ROMs through the SD card slot
rather than through the cartridge slot). You can join the [discord
server](https://discord.gg/UDu5ztY) if you want to chat with the Super
Nt community.

Use at your own discretion. We are not responsible for any damage 
or data loss caused by custom firmware installation or use.
