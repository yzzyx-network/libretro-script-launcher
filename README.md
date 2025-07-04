# libretro-script-launcher

Launch external scripts and programs from Retroarch!

With this core, you can launch any script or program you want! Now you can have your entire PC game library accessible from Retroarch!

Note: This core works on Linux, and it should work on MacOS as well. I don't think it will work on Windows unfortunately, but I don't have a Windows computer to test that. It should be very simple to make a Windows version, I just don't know its commands as well.
Note 2: This is a big hack based on code from the [Libretro Dolphin Launcher](https://github.com/RobLoach/libretro-dolphin-launcher). I only changed a few lines to make this, so there's still some code and comments referencing Dolphin.

## Installation

#### Method 1 (Linux Only)

1. Download the core from the [Releases](https://github.com/yzzyx-network/libretro-script-launcher/releases) page

2. Extract files to the locations specified in the included `readme.txt`

#### Method 2 (MacOS & Linux)

1. Compile the core
    ``` bash
    git clone https://github.com/yzzyx/libretro-script-launcher.git
    cd libretro-script-launcher
    make
    ```

2. Copy the core file to the RetroArch cores directory
   
   ```bash
    cp script_launcher_libretro.so ~/.config/retroarch/cores/
    cp script_launcher_libretro.info ~/.config/retroarch/cores/
    ```
    or
    ``` bash
    cp script_launcher_libretro.so /usr/lib/libretro/
    cp script_launcher_libretro.info /usr/share/libretro/info/
    ```

## Usage

0. (Recommended) Make a folder for any scripts, executables, and shortcuts you want in your library

1. Perform a manual scan on that folder in Retroarch 
    -you can specify any filetype, just make sure the file is executable
    -I recommend manually naming the playlist something appropriate (eg. "Windows Games" or something)

2. (Optional) Create thumbnail images for the playlists to make them look pretty

And that's it!

## Example Script

With scripts, you can execute multiple programs and perform multiple tasks.

This example is one of my scripts, it accomplishes a few things:

1. Opens a controller mapping program with a specific remap file
2. Sets variables for Wine
3. Navigates to the folder with the executable
4. Launches a game
5. After the game is closed, it automatically closes the controller mapping software

```bash
#!/bin/bash
antimicro --tray ~/.config/antimicro/touhou.dpadfix.gamecontroller.amgp &
COMPATPATH="/home/yzzyx/.steam/steam/steamapps/compatdata"
TOUHOUPATH="/home/yzzyx/Games/Touhou/Touhou 8 - Imperishable Night"
export WINEPREFIX="${COMPATPATH}/2989464801/pfx"
export WINEARCH="win64"
cd "$TOUHOUPATH"
wine th08.exe
killall antimicro
```
Once the script has finished running, Retroarch should come back up on its own!


## Example Playlists

Here's just a couple examples of custom icons/thumbnails I made for my playlists.

(These specific icons are included in the Images folder for anyone interested!)
![](https://github.com/yzzyx-network/libretro-script-launcher/blob/master/Images/linuxplaylistsample.jpg)
![](https://github.com/yzzyx-network/libretro-script-launcher/blob/master/Images/wineplaylistsample.jpg)

To add icons like this, follow these steps:

1. Make sure you have a custom playlist for your games
2. Navigate to the png assets folder for the theme you use
    (eg. `~/.config/retroarch/assets/xmb/systematic/png`)
3. Place the icons in that folder
    -The icon used for the playlist should have a filename that matches the playlist name
    -The icon for the games in the playlist should have "-content" added to the filename
        (eg. `Windows - Wine.png` and `Windows - Wine-content.png`)

## Contributors

- [yzzyx](http://github.com/yzzyx-network)
- [Rob Loach](http://github.com/robloach)
- [Alcaro](https://github.com/Alcaro)
