# Doom 64 EX+

Doom 64 EX+ is a continuation project of Samuel "Kaiser" Villarreal's Doom 64 EX aimed to recreate DOOM 64 as closely as possible with additional modding features.

## Differences from Kaiser's C++ version of EX on GitHub:

* Support for the IWAD from Nightdive Studios' official remaster
* Support for the Lost Levels campaign
* Support for loading PWADs
* Better performance (especially when compared to Nightdive Studios' official version which is slow as hell)
* Messages for discovering secret areas
* Support of MAP slots up to MAP40
* The "medkit you REALLY need!" message fix
* Many bugfixes
* KEX - This is pretty much removed.  The only remnants are some comments with [kex] and the rendering stuff that is used in later versions. I wanted to keep Doom 64 EX+ very close in format to other source ports for familiarity purposes and for ease of porting code from Erick's DOOM64-RE project.

There are a few bugs still present, which I am slowly fixing.

This GitHub repo is the same as: https://sourceforge.net/projects/doom64ex-plus/ but if any contributors wish to help, then GitHub is a better place for it.

## Mod Support

For modders wanting to make their mods work with EX+, there are a few things that deviate from ancient EX:

1. DM_START and DM_END tags are used (like the remaster) instead of DS_START and DS_END.
2. G_START and G_END graphics tags aren't implemented (like the remaster).

Instead:

* The **first** tag for graphics **MUST BE** called SYMBOLS.
* The **last** tag for graphics **MUST BE** called MOUNTC.

They can either be a tag or a graphic.  This is due to me not flat-out reading all PNGs in a WAD but instead, to support the official IWAD, I read the content like this to catch all the graphics that EX+ needs from the IWAD.

No other changes are needed.

## Dehacked Support

For modders interested in dehacked for DOOM64EX+, please refer to the 'modding' directory for reference.

## Dependencies

* SDL2
~~* SDL2_net~~
* zlib
* libpng
* FluidSynth

## Compiling

Clone this repo

    $ git clone https://github.com/atsb/Doom64EX-Plus

### Linux or Cross Plataform Compilation

Use the `build.sh` script for a native build and the `build_win_cross.sh` script for cross compilation for Windows.

### Windows

Use the Visual Studio solution and project files provided in the `Windows` directory of the repository for both 32-bit or 64-bit builds.

## Usage

Doom 64 EX+ needs the DOOM 64 asset data files to be present for you to be able to play the game. The data files are:

* `DOOM64.wad`
* `doom64ex-plus.wad`
* `doomsnd.sf2`

### Linux 

You can place the asset data described above to any of the following directories:

* The directory in which `doom64ex-plus` resides
* `$XDG_DATA_HOME/doom64ex-plus` (eg. `~/.local/share/doom64ex-plus`)
* `/usr/local/share/games/doom64ex-plus`
* `/usr/local/share/doom64ex-plus`
* `/usr/share/games/doom64ex-plus`
* `/usr/share/doom64ex-plus`

Then, you can start playing:

    $ doom64ex-plus

**NOTE for Linux users:** As of Feb. 24, 2016, the save data is located in `$XDG_DATA_HOME/doom64ex-plus` (typically `~/.local/share/doom64ex-plus`) and not in `~/.doom64ex-plus`. The files can be safely moved to their new home.

### Windows

The asset data files need to be located in the same directory as `Doom64EX-Plus.exe`.

Then, you can start playing by launching `Doom64EX-Plus.exe` (or optionally by using `Doom64EX-Plus Launcher.exe` instead).
