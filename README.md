# libretro-script-launcher

(made this for personal use awhile ago, can't find the modified code so I'm working on recreating it; as such, this doesn't work yet at this moment. it should be done within a day or 2!)

Launch external scripts and programs from Retroarch!

With this core, you can launch any script or program you want! Now you can have your entire PC game library accessible from Retroarch!

Note: This is a big hack based on code from the [Libretro Dolohin Launcher](https://github.com/RobLoach/libretro-dolphin-launcher).

## Installation

1. Compile the core
    ``` bash
    git clone https://github.com/yzzyx/libretro-script-launcher.git
    cd libretro-script-launcher
    make
    ```

2. Copy the core file to the RetroArch cores directory
    ``` bash
    cp script_launcher_libretro.so /usr/lib/libretro/
    cp script_launcher_libretro.info /usr/share/libretro/info/
    ```
    ```

## Usage

0. (Recommended) Make a folder for any scripts, executables, and shortcuts you want in your library

1. Perform a manual scan on that folder in Retroarch 
    -you can specify any filetype, just make sure the file is executable
    -I recommend manually naming the playlist something appropriate (e.g. "Windows Games" or something)

2. (Optional) Create thumbnail images for the playlists to make them look pretty

And that's it!


## Contributors

- [yzzyx](http://github.com/yzzyx-network)
- [Rob Loach](http://github.com/robloach)
- [Alcaro](https://github.com/Alcaro)
