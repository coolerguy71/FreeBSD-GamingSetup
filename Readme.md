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

## Steam BSD Runtime:

```
https://github.com/es-j3/Steam-BSD-Runtime/
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

> Documentation By: es-j3 (coolguy71 is old account)

> Mizuma by Alexander88207

> Steam BSD Runtime
===================================================
