# FreeSO Web Installer (experimental)
Web-based installer that uses a lightweight desktop utility to install the game via https://beta.freeso.org/install

## Technical details
Hosted at https://beta.freeso.org/install, this web installer uses a small Node.js program (a WebSocket server) that the user can run to handle the installation. All interactivity with the installer is made through the online web interface at beta.freeso.org, which calls the WebSocket server hosted via the desktop utility.
* This approach has been used in (and has been proven to work), for example, in Dell's Driver installation website: https://www.dell.com/support/home/en-us?app=drivers

### Advantages 
* Smaller and more efficient than using a full desktop program.
* Cross-platform (Windows, macOS, linux)
* Precise - it installs just the necessary software for the game to run.
* More compatible - less points of failure.
   > By removing the dependency on desktop GUI frameworks like Electron, there are less points of failure. The utility includes precisely what is needed for it to function: Node.js and a C++ library for invoking a native file/folder picker. This maximizes compatibility for desktop devices.

### Architecture
A monorepo consisting of 4 packages:
* **desktop-core** - Core Typescript library used in the desktop-utility and web-installer packages. Should be used by the launcher in the future.
* **desktop-native** - Node.js bindings for native C++ libraries
  (for splash-screen and file/folder picker dialogs).
* **desktop-utility** - Node.js program that hosts the WebSocket server on the user's machine.
* **web-installer** - Frontend web app hosted @ beta.freeso.org, communicates with desktop-utility via WebSockets.

## Preview 1 - Modified signup page
* The web installer would be the preferred installation method, since it's just quicker and less of a hassle than installing and using a full desktop program. 
* The download button would now take to the web installer. 
* The launcher would now become optional, with a button added at the end of the web installer (see Preview 5).

![Desktop - 1](https://github.com/ItsSim/freeso-web-installer/assets/35347872/1e3881f5-6830-4811-a436-ab7bf264f085)

## Preview 2 - Download and run the desktop utility
* The user will have to download the executable and run it.

  ![image](https://github.com/ItsSim/freeso-web-installer/assets/35347872/aba53072-ca20-4c5c-8b32-bab3a5115bef)

* The utility will host a web server locally which can be called by the online website.
* The online interface will only allow the user to continue if the utility has been detected as running.

![Desktop - 3](https://github.com/ItsSim/freeso-web-installer/assets/35347872/4375f0f3-f931-40c7-987e-c2313efe6856)

## Preview 3 - Desktop utility has been detected
* The user can now pick additional tasks to be done by the utility.
  - The user can choose to install the remesh package or not.
  - The user can choose to create desktop shortcuts (one for 2D, another one for 3D).
* The user can now begin the installation.

![Desktop - 2](https://github.com/ItsSim/freeso-web-installer/assets/35347872/fb72d5ba-280c-40ae-a211-7d6dd0dfb1ce)

## Preview 4 - Installation progress
* The installation progress is shown in two ways:
  - Completion percentage.
  - Log of actions taken by the utility for transparency.

![Desktop - 4](https://github.com/ItsSim/freeso-web-installer/assets/35347872/7edd8e62-2f92-4a10-8caa-f15a887affc1)

## Preview 5 - Installation finished
Once successfully done:
* The user can directly run the game.
* The user now has the option to download the launcher.

![Desktop - 5](https://github.com/ItsSim/freeso-web-installer/assets/35347872/99ab5e74-ff6b-4943-a41a-7459fd089d92)

