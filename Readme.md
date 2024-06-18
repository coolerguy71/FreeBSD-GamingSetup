===================================================

# Start gaming on FreeBSD!

V, 0.1

> *RUN ALL (Installer) COMMANDS BELOW AS ROOT!

> TO BECOME ROOT, RUN: 

```
 su
```
> Password:

```
(The root password you set)
```

> TO GO BACK TO A REGULAR USER:

```
su 'username'
```

===================================================
## WINE-based Game Launcher:

# Mizuma:

```
pkg install mizuma
```

## Steam Linuxulator Launcher:

```
pkg install linux-steam-utils
```

===================================================
## PROTON

Wine-Proton:

```
pkg install wine-proton && /usr/local/wine-proton/bin/pkg32.sh install wine-proton mesa-dri
```
To use Proton, do:

```
/usr/local/wine-proton/bin/wine /path/to/your/application.exe --no-sandbox
```
> (many apps are broken without the --no-sandbox flag)
Example:

```
/usr/local/wine-proton/bin/wine /home/coolguy/Downloads/EpicGamesLauncher.exe --no-sandbox
```

===================================================

## Minecraft
> It's a popular game, and isn't too hard to get running natively!

> (now's probably a good time to update your ports tree, there are many new thingimajigs you need)

```
pkg install git && rm -rf /usr/ports && git clone --depth 1 -o freebsd -b main https://git.FreeBSD.org/ports.git
```

> Install all the necessary Prism Launcher and Minecraft dependencies! (A lot, I know.)
```
pkg install qt5 qt6 cmake kf5-extra-cmake-modules openjdk8 openjdk17 openjdk21 lwjgl lwjgl3 git && git clone --recursive https://github.com/PrismLauncher/PrismLauncher.git && cd PrismLauncher && cmake -S . -B build -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX="/usr/local" -DCMAKE_PREFIX_PATH=/usr/local/lib/qt5/cmake -DENABLE_LTO=ON && cd build && sudo make -j$(nproc) install 
```
> We now need GLFW with an option enabled to get Minecraft working!

```
cd /usr/ports/graphics/glfw && make install clean
```

> Now wait, make sure to select the PREEDIT option when you are given the fancy TUI (Terminal User Interface)!

<details>

<summary>Accidentally clicked passed it? Try this!</summary>

```
pkg remove glfw && cd /usr/ports/graphics/glfw && make clean && make rmconfig
```
> Then try the previous steps again!

</details>

> Okay, moving on, let's get minecraft-runtime set up! (Run this as a regular user, not root!)

```
cd && mkdir .lwjgl3 && cd .lwjgl3 && git clone https://github.com/coolerguy71/FreeBSD-GamingSetup.git && cp FreeBSD-GamingSetup/minecraft-runtime ~/.lwjgl3 && rm FreeBSD-GamingSetup
```
(UNIFINISHED, WILL BE UPDATED SOON!)

===================================================
> Happy gaming!

> Doc By: coolguy71

> Mizuma by Alexander88207

> linux-steam-utils by shkhln

> Minecraft doc from pog5: (updated by coolguy71 on this guide)

===================================================
