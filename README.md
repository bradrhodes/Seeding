## battlefield-seeder

Coded by Tim Froehlich (Avatar2453, Avatar_Ko, Advacar, etc)

Goal: This script was made to automate seeding of Battlefield Servers. It will:

Join a server automatically if there are less than the minimum number of players in the server
After joining, will minimize the game so that it takes less resources
Leave the server automatically if there are more than the maximum number of players in the server
Prompt you whether you want to launch or leave the game before it does so, and do it anyways if you don't respond in time (5 and 10 seconds respectively)   

Pre-requisites: 
Internet Explorer, Being logged into Battlelog and Origin.    

How to run: 
Just run BattlefieldSeeder.exe

How to change settings: 
Open BFSeederSettings.ini in notepad, modify the Settings as you want, save, and restart BattlefieldSeeder.exe.   

How to stop the script: 
There will be an entry in your system tray with the same logo as the script. Right click it and click Exit

What are "SleepWhen[Not]Seeding" in the settings?
These specify how often (in minutes) to open up internet explorer and check the player count of the server. Checking the player count occurs in the background but you will see your PC momentarily slow down when it opens IE.
SleepWhenSeeding is active when BF is open, SleepWhenNotSeeding is active when BF is not open.

#### Settings:
**ServerAddress** - set the address of the server to monitor/seed
**MinPlayers** - auto-seeding will occur if player count is below this threshold
**MaxPlayers** - BF4 will exit if player count is above this threshold
**Username** - set to your Battlelog username
**SleepWhenNotSeeding** - Explained above
**SleepWhenSeeding** - ExplainedAbove
**PlayerCountRetry** - The number of retries the seeder will attempt to get the player count before quitting. Set to -1 to retry indefinitely.
**EnableLogging** - Enables logging to an output file that can aid in troubleshooting. Default is false.
**EnableGameHangProtection** - Causes the BF4 game to be closed every 30 mins and re-opened to deal with the game hanging


### Changelog      
##### v2.4

- merged the BF3 and BF4 seeder tools into 1 tool   
   - it determines which game is being seeded by the server url
- cleaned up the folder structure to reflect these changes
- added a folder with default .ini's   

##### v2.3
- removed wait for BF window to exist
- fixed some of the hang protection logic that may allow many hang protection windows to stack up
- added logic for idle kick avoidance
	- caveats:
		- should work in windowed mode, borderless or full screen mode
		- may cause BF sound effects to play through speakers (because BF gains focus)
		- will not work if the player is spawned, only if in the deploy menu or the main menu   
		
##### v2.2   
- fixed bug with hang protection timer timing out instaneously after first timeout
- fixed IE related bugs where current user couldn't be detected   

##### v2.1
- fixed bug where seeding would not occur when player count was >= 2

##### v2.0
- improve handling of game crashes
- improved protection for game hangs by forcing BF4 to be restarted every half hour
- added feature to allow for multiple retries for finding player count before giving up
- fixed bug where many IE instances would be opened, eventually consuming all memory
- fix bug wher incorrect browser is spawned
