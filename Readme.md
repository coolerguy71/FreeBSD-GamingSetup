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
> Happy gaming!

> Documentation By: coolguy71

> Mizuma by Alexander88207

> linux-steam-utils by shkhln

> Minecraft doc from pog5: (updated by coolguy71 on this guide)

===================================================
