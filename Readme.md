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

> Happy Gaming!

===================================================

> Doc By: coolguy71
> Mizuma by Alexander88207
> linux-steam-utils by shkhln
===================================================

===================================================
