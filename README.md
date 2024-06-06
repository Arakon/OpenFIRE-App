###### pretty screenies here

# OpenFIRE App
### Reference configuration utility for the [OpenFIRE light gun system](https://github.com/TeamOpenFIRE/OpenFIRE-Firmware), written in Qt & C++.

## Features:
 - **Cross-platform Qt application,** portable across Linux & Windows desktops & Raspberry Pi systems.
 - **Simple to use:** select the gun from the dropdown, and configure away!
 - See and manage current pins layout, toggle on and off custom mappings, set other tunables, and change the gun's USB identifier (with built-in decimal-to-hex conversion for your convenience!) all on the fly.
 - Also serves as a testing utility for button input, solenoid/rumble force feedback, and camera.

## Running:
Boards flashed with OpenFIRE *must be plugged in **before** launching the application.* The app will notify if it can't find any compatible boards connected.

### For Linux:
##### Requirements: Anything with QT5 support.
 - Arch Linux: **TODO: Aur PKGBUILD when public**
 - Other distros: [Try the latest binary](https://github.com/TeamOpenFIRE/OpenFIRE-App/releases/latest) (built for Ubuntu 20.04 LTS, but should work for most distros?)
 - Make sure your user is part of the `dialout` group (`# usermod -a -G dialout insertusernamehere`); you'll be notified on startup if this is necessary.

### For Windows:
##### Requirements: Windows 7 and up (64-bit only).
 - Download the [latest release zip.](https://github.com/TeamOpenFIRE/OpenFIRE-App/releases/latest)
 - Extract the `OpenFIREapp` folder from the archive to anywhere that's most convenient on your system - `OpenFIREapp.exe` should be sitting next to `Qt5Core.dll` and others, as well as the `platforms` and `styles` folders.
 - Start `OpenFIREapp.exe`

## Building:
### For Linux:
#### Arch: requires `qt-base` `qt-serialport` `qt-svg`
#### Debian: requires `qttools5-dev` `libqt5serialport-dev` `libqt5svg-dev` (for Qt5)
 - Clone the repo:
   ```
   git clone https://github.com/TeamOpenFIRE/OpenFIRE-App
   ```
 - Setup build directory:
   ```
   cd OpenFIRE-App
   mkdir build && cd build
   cmake .. -DCMAKE_BUILD_TYPE=Release
   ```
 - Make:
   ```
   make
   ```
 - And run:
   ```
   ./OpenFIREapp
   ```
### For Windows:
#### Requires the Qt SerialPort extension to be installed from the Qt Installation Wizard or Qt Maintenance Tool
 - Should be buildable through CMake w/ msys2 (follow Arch Linux instructions) or the Qt Creator IDE.
###### TODO: check for accuracy

### TODO:
 - Implement version comparison to latest OpenFIRE GitHub release (or at least latest as of the GUI version).
 - Add one-click firmware installation/updating from GUI (for both already flashed guns AND RP2040 devices in bootloader mode).

### Special Thanks:
 * Samuel Ballentyne, Prow7, and co. for their work on the SAMCO system & derivatives, and supporting work and conception of OpenFIRE.
 * Odwalla-J, mykylegp, RG2020 & lemmingDev for prerelease consultation, bug testing and feedback.
 * All early IR-GUN4ALL testers and ArcadeForums users whom provided early testing and feedback.
