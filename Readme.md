===================================================

# Start gaming on FreeBSD!

> *RUN ALL (Installer) COMMANDS BELOW AS ROOT!

> TO BECOME ROOT, RUN: 

```
 su -
```
> Password:

```
(The root password you set)
```

> TO GO BACK TO A REGULAR USER:

```
exit
```

===================================================
# WINE-based Game Launcher:

## Mizuma:

```
pkg install mizuma
```

# Steam Linuxulator Launcher:

## Linux Steam Utils:

```
pkg install linux-steam-utils
```
**Currently broken, wait a couple weeks! (6-29-24)

===================================================
# PROTON

## Wine-Proton:

```
pkg install wine-proton && /usr/local/wine-proton/bin/pkg32.sh install wine-proton mesa-dri
```
To use Proton, do:

```
/usr/local/wine-proton/bin/wine /path/to/your/application.exe --no-sandbox
```
> (no sandbox fixes Electron and Chromium apps, if running anything other than this, you may disable.)
Example:

```
/usr/local/wine-proton/bin/wine /home/coolguy/Downloads/EpicGamesLauncher.exe --no-sandbox
```

===================================================

# Minecraft
> It's a popular game, and isn't too hard to get running natively!

> (now's probably a good time to update your ports tree, there are many new thingimajigs you need)

```
pkg install git && rm -rf /usr/ports
```
```
git clone --depth 1 -o freebsd -b main https://git.FreeBSD.org/ports.git /usr/ports
```

> We now need GLFW with an option enabled to get Minecraft working!

```
cd /usr/ports/graphics/glfw && make install clean
```



> Now wait, make sure to select the PREEDIT option when you are given the fancy TUI (Terminal User Interface)!

    ┌────────────────────────────────────────┤glfw-3.4├─────────────────────────────────────────┐
    │ 'F1' for Ports Collection help.                                                           │  
    │ ┌───────────────────────────────────────────────────────────────────────────────────────┐ │  
    │ │new [X] DOCS     Build and/or install documentation                                    │ │  
    │ │new [X] EXAMPLES Build and/or install examples                                         │ │  
    │ │new [X] PREEDIT  Add patches for run Minecraft (https://github.com/glfw/glfw/pull/2130)│ │  
    │ │─────────────────── Window creation platform [select at least one] ────────────────────│ │  
    │ │new [X] WAYLAND  Wayland (graphics) support                                            │ │  
    │ │new [X] X11      X11 (graphics) support                                                │ │  
    │ └───────────────────────────────────────────────────────────────────────────────────────┘ │  
    ├───────────────────────────────────────────────────────────────────────────────────────────┤  
    │                                   [  OK  ]     [Cancel]                                   │  
    └───────────────────────────────────────────────────────────────────────────────────────────┘  
      
<details>

<summary>Accidentally clicked the above command? Try this!</summary>

```
pkg remove glfw && cd /usr/ports/graphics/glfw && make clean && make rmconfig
```
> Then try the previous steps again!

</details>
(not the below step)

> Install all the necessary Prism Launcher and Minecraft dependencies! (A lot, I know.)
```
pkg install qt5 qt6 cmake kf5-extra-cmake-modules openjdk8 openjdk17 openjdk21 lwjgl lwjgl3 git && git clone --recursive https://github.com/PrismLauncher/PrismLauncher.git && cd PrismLauncher && cmake -S . -B build -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX="/usr/local" -DCMAKE_PREFIX_PATH=/usr/local/lib/qt5/cmake -DENABLE_LTO=ON && cd build && make -j$(nproc) install 
```

> Okay, moving on, let's get minecraft-runtime set up! (Run this as a regular user, not root!)

```
cd && git clone https://github.com/pog5/minecraft-freebsd.git && mkdir .minecraft && cd minecraft-freebsd && tar xf lwjgl3.tar.gz && cp ~/minecraft-freebsd/lwjgl3/minecraft-runtime ~/.minecraft && cd && rm -rf minecraft-freebsd
```

> **Note that this minecraft-runtime can only go up to about Minecraft 1.20.4?? (Not sure but somewhere around this), but to play newer versions of Minecraft (1.20.5??) and above, (including 1.21), we will have to modify minecraft-runtime.

```
ee ~/.minecraft/minecraft-runtime

change the 4th line to this:

export JAVA_HOME=/usr/local/openjdk21
```

> Now, after all of this, let's move into Prism Launcher! Select your language, and go through setup, and follow below!

![image](https://github.com/coolerguy71/FreeBSD-GamingSetup/assets/168948679/793382a4-c435-46c0-ab35-66bae1aa97ac)
> *image is outdated, instead of .lwjgl3, pretend it's .minecraft :)

Log in with your Microsoft account, and you're good to go!

===================================================
> Happy gaming!

> Documentation By: coolguy71

> Mizuma by Alexander88207

> linux-steam-utils by shkhln

> Minecraft doc from pog5: (updated by coolguy71 on this guide)

===================================================
