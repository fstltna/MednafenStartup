# Mednafen Server Startup Scripts (1.0.0)
Startup scripts for the Mednafen game server - uses the "screen" command to manage session. This also restarts the Mednafen server process if it crashes.

Official support sites: [Official Github Repo](https://github.com/fstltna/MednafenStartup) - [Official Forum](https://gameplayer.club/index.php/ourforum/9)

---
These start up the Mednafen server at boot time with a "screen" process.

1. Copy **mednafen** into **/etc/init.d** - make sure it is executable
2. Copy **startmednafen** into **/root/mednafen-server** - make sure it is executable
4. Run "**systemctl enable mednafen**" (only needed once, will stick)
5. Run "**systemctl start mednafen**" - starts Mednafen without restarting the server

When you want to view the Mednafen console, just enter "**screen -r**" in your shell.

To disconnect from the Mednafen console just press **CTRL-A CTRL-D**. This will leave it running and you can reconnect to it again.

I have only tested this on a Ubuntu 16.04 server...

If you want to turn off the server respawning type "**touch /root/mednafen-server/nostart**". To reenable it type "**rm /root/mednafen-server/nostart**".

---
Note: If you don't already have the "screen" tool installed you will need to install it by "**sudo apt-get install screen**".
