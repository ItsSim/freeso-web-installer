# FreeSO Web Installer (experimental)
Web-based installer that uses a lightweight desktop utility to install the game via https://beta.freeso.org/install

## Technical details
Hosted at https://beta.freeso.org/install, this web installer uses a small Node.js program (a web server) that the user can run to handle the installation. All interactivity with the installer is made through the online web interface at beta.freeso.org, which calls the desktop API hosted via the utility.
* This approach has been used in (and has been proven to work), for example, in Dell's Driver installation website: https://www.dell.com/support/home/en-us?app=drivers

### Advantages 
* Super lightweight and more efficient than using a launcher.
* Easy cross-platform support the get-go.
* Quicker than other installation methods.
* Installs just the necessary software for the game to run.

## Preview 1 - Modified signup page
* The web installer would be the preferred installation method, since it's just quicker and less of a hassle than installing and using a full desktop program. 
* The download button would now take to the web installer. 
* The launcher would now become optional, with a button added at the end of the web installer (see Preview 5).

![Desktop - 1](https://github.com/ItsSim/freeso-web-installer/assets/35347872/1e3881f5-6830-4811-a436-ab7bf264f085)

## Preview 2 - Download and run the desktop utility
* The user will have to download the executable and run it.
* The utility will host a web server locally which can be called by the online website.
* The online interface will only allow the user to continue if the utility has been detected as running.

![Desktop - 3](https://github.com/ItsSim/freeso-web-installer/assets/35347872/01456db2-4d8a-4bc1-a4d1-ff5b5f7cb963)

## Preview 3 - Desktop utility has been detected
* The user can now pick additional tasks to be done by the utility.
  * The user can choose to install the remesh package or not.
  * The user can choose to create desktop shortcuts (one for 2D, another one for 3D).
* The user can now begin the installation.

![Desktop - 2](https://github.com/ItsSim/freeso-web-installer/assets/35347872/3b8c8701-c12b-4e02-8fb7-f7ef60d75d78)

## Preview 4 - Installation progress
* The installation progress is shown in two ways:
  * Completion percentage.
  * Log of actions taken by the utility for transparency.

![Desktop - 4](https://github.com/ItsSim/freeso-web-installer/assets/35347872/b320eb40-99e4-4469-8a64-473cd85ff953)

## Preview 5 - Installation finished
Once successfully done:
* The user can directly run the game.
* The user now has the option to download the launcher.

![Desktop - 5](https://github.com/ItsSim/freeso-web-installer/assets/35347872/9656e571-0556-46de-a7b7-50c3dba33f01)

