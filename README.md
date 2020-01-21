# ONSET FRENCH ROLEPLAY
## Windows Server
### Minimum requirements
@Development: Windows 10
Production: Windows Server 2012 or later
Single core processor with SSE2 instructions
50 MB disk space and 100 MB RAM
Setup
Download steamcmd as described on this page: https://developer.valvesoftware.com/wiki/SteamCMD#Windows

Open a Command Window (cmd.exe) and navigate to your steamcmd folder. Run steamcmd.exe

steamcmd.exe

Login to steam as anonymous
login anonymous

Set the install directory for the Onset server files.
force_install_dir C:/OnsetServer/

Download the server application.
app_update 1204170 validate

Exit SteamCMD
quit


Linux Server
We recommend Linux for production servers.

Minimum requirements
Ubuntu 18.04, Debian 9 (with openssl installed)
Single core processor with SSE2 instructions
50 MB disk space and 100 MB RAM
Packages: curl, nano, openssl
Setup
As root install the following package.
apt-get install lib32gcc1

Make sure you run the server on a user without superuser rights. We recommend to add a new user for this step.
Create a new directory for the Onset server.
mkdir Steam

Install SteamCMD
curl -sqL "https://steamcdn-a.akamaihd.net/client/installer/steamcmd_linux.tar.gz" | tar zxvf -

Start SteamCMD
./steamcmd.sh

Login to steam as anonymous
login anonymous

Set the install directory for the Onset server files.
force_install_dir ./OnsetServer/

Download the server application.
app_update 1204170 validate

Exit SteamCMD
quit

Configuration
cd OnsetServer

Edit the server_config.json file nano server_config.json. Info on the config file: server_config.
nano server_config.json

Once you are done with editing press CTRL+X and then Y to save the config file.
Run ./start_linux.sh to start your server. The shell file sets the environment path so the server finds the required SteamAPI files.
Gamemode Packages
Packages make up all of your server. Please see this wiki entry (packages) on how to get started with them.

Game Compatibility Version Number
The parameter "--version" displays server version information. The compatibility number determines what clients can connect. Game and server must have the same compatibility number for the connection to succeed. The version number does not matter in this case.

ServerCommandlineVersion.PNG

Command line arguments
The parameter "--help" displays available command line options.

ServerCommandlineHelp.PNG

Network Ports
The dedicated server requires 3 network ports to be open.

UDP 7777 - Game
UDP 7776 - Server query
TCP 7775 - HTTP server, file downloads
Ports can be changed in the server_config.
