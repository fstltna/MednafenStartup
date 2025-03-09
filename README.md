# Mednafen Server Startup Scripts (1.1.0)
Startup scripts for the Mednafen game server - uses the "screen" command to manage session. This also restarts the Mednafen server process if it crashes.

Official support sites: [Official Github Repo](https://github.com/fstltna/MednafenStartup) - [Official Forum](https://mednafen.gameplayer.club/index.php/forum/our-server-tools)

---
These start up the Mednafen server at boot time with a "screen" process.

1. Copy **mednafen** into **/home/mednafenuser/bin** - make sure it is executable
2. Copy **startmednafen** into **/home/mednafenuser/mednafen-server** - make sure it is executable
4. As mednafenuser run "crontab -e" and add this line: "**@reboot /home/mednafenuser/bin/mednafen start**"

When you want to view the Mednafen console, just enter "**screen -r**" in your shell.

To disconnect from the Mednafen console just press **CTRL-A CTRL-D**. This will leave it running and you can reconnect to it again.

I have only tested this on a Ubuntu 24.04 server...

If you want to turn off the server respawning type "**touch /home/mednafenuser/mednafen-server/nostart**". To reenable it type "**rm /home/mednafenuser/mednafen-server/nostart**".

---
Note: If you don't already have the "screen" tool installed you will need to install it by "**sudo apt-get install screen**".
