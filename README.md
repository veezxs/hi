# Nuking Discord Server Bot/Nuke Bot
## C-REAL bot
 C-REAL bot has 36 commands here a list:
```
[aChannel] [aVC] [aCat] [auditLog] [aRole] 
[banAll] [ban] [bans] [channels] [connect] 
[connecting] [clear] [categories] [channelBomb] 
[catBomb] [dRole] [dAllRoles] [dAllChannels] 
[dChannel] [dVC] [disconnect] [dCat] [dAllCat] 
[h] [kick] [kaboom] [leave] [leaveAll] [nuke] 
[off] [roles] [roleTo] [roleBomb] [sn] [si] [servers] 
```
The bot's prefix is a dot (.)

## About the bot
I got idea of creating a nuking discrod server bot from (Cerealwithnomilk)[https://www.youtube.com/channel/UCxX7O68badw2sBbcvQK0wBQ] and the bot is named after that guy.
A shout out to cyxl#9986 for helping me.

You can already tell most of the commands by its name.
There are a few that are confusing for some people that I have tested with. I'm also going to explain it from below.

IMPORT: While creating C-REAL, I have encounter many times that ".aRole" not working. It's not a bug, but I think it's probably discord's bug. So when ".aRole" is not working you'll have to wait for a few minutes, or a few hours or a day to use it again. And during my testing, it seems like there's a limit of how much channels, categories, and roles you can create on a server. It's probably around 500. When you are seeing "unable to" create something many times, that means it's either the don't have permissions to create or the server reached it's limit.

### ".h" the most import one help command
* the bot's prefix is dot (.)
* the help command has 2 opitional arguments, first argument can be "names", "all", or the command you want to know. "names" is the default arg and it will give you a list of commands without description like the above. "all" displays all the commands in pages, and the second arg is used for toggling between pages.

### Connections
Connection is a special feature in C-REAL. Connection commands are for DM attacks. You can DM the bot to connect to a server that the bot is already in, and then use all the available commands in the DM.
Here's how to use connection commands.
*Type ".servers", it'll give you a list of servers that the bot is in.
```
Servers
Total count: 1
Name            ID
testing server  740457514281468024
```

* Type the name or ID of that server after the command ".connect server name here".
.connect testing server
or
.connect 740457514281468024
The bot will tell you if you successfully connected to the server or not.

* After connecting to it you can do want ever you want with the commands. Like ".nuke" or ".aChannel name category name"
* ".disconnect" is for faster reactions. The bot will do less checks if you are disconnected.

### Configuration file
C-REAL will always try to look for the file "default.json" that is next to it, after finding the file it'll use that file. If you don't have a config file, the bot will ask you to enter a path for the config file. This feature is made for multiple nukes.
Here's what the config file should look like if it's expanded:
```
{
	"token": "your.bot's.token",
	"permissions": [
		"TKperson#4883",
		"cyxl#9986",
		"a shout out to cyxl for helping me#3333",
		"you can add more if you want to#1234"
	],
	"bomb_messages": {
		"random": 10,
		"fixed": [
			"fixed bomb",
			"when you run any bomb like '.channelBomb 100 fixed' it'll randomly choose stuff from this array",
			"rip",
			"ezzzzz",
			"c-real on top you are in the bottom",
			"add more if you want to"
		]
	},
	"bot_permission": "2146958847",
	"after": [
		["aCat", "RIP"],
		["aChannel", "RIP", "RIP"],
		["sn", "You are in the bottom"],
		["si", "https://ih1.redbubble.net/image.788111706.5520/st,small,507x507-pad,600x600,f8f8f8.u2.jpg"]
	]
}
```
*token: Your bot's token.
*Permissions: User that can use the bot.
*Bomb messages:
 *random: random base64 characters with a length of 10(in this example).
 *fixed: randomly chose messages, while bombing.
Available bomb commmands: ".channelBomb", ".catBomb", ".roleBomb", and ".kaboom". They all use the same arguments. example. ".kaboom 1000 fixed" this will create 1000 fixed name channels, categories, and roles. ".kaboom" is basically all bomb blow up at once.
*bot permission: permission given to the bot when inviting the C-REAL to a server.
*after: a part that runs during ".nuke" command. It'll run all the commands that is inside the array. NOTE: INSIDE "after" IT'S CASE SENSITIVE, and everything created with "after" part won't get deleted by the nuke command.
In this example of the after part:
it creates a category called RIP
next, it create an RIP channel in the RIP category
then, it changes the server's name to "You are in the bottom"
and lastly, it changes the server icon to that link.

*There's a build.html that comes with C-REAL. It can help you to make a your own config file.

### ".nuke" command
nuke command is one of the main feature in C-REAL. ".nuke" is basically ".dAllRoles" + ".dAllChannels" + "dAllCat" + ".banAll"(below the bot's role rank) + an "after" command.
* the first 4 commands are easy to understand. They are just delete all roles, channels, categories, and ban everyone.
* For the "after" part. It can be configured in the config(.json) file. This "part" is for during nuking it'll do all the commands that you configured in the config(.json) file. Note: everything created with "after" part won't get deleted.
For example:
".si https://link.to/an/image.jpg" will change the server icon to "https://lin.to/an/image.jpg".
".sn you have been nuked" will change the server name to "you have been nuked"

### ".kaboom". What a loud sound...
* Kaboom is another main feature. It's the combination of ".channelBomb", ".catBomb", and ".roleBomb".
If you entered ".kaboom 1000 random", it's equal to:
".channelBomb 1000 random"
".roleBomb 1000 random"
".catBomb 1000 random"
what it does is to spam creating channels, categories, and roles 1000 times with random base64 names.

### ".aRole" there's a hidden feature.
*If you add a " t"(space t) at the end, if the bot has permission to create admin role, then the bot will create a role with admin. And then you can use ".roleTo @TKperson the name or Id of the role"
it'll look something like: ".aRole admin t"

### ".auditLog" command
* an audit log is a list that contains every server changing actions with the user, target, and action commands.
* This command will save the current server's audit log into the host's pc with given path and given number of items.
* Without giving a path it'll save in the local directory. Without giving a limit to save how much item it'll save all of the actions. (it took around 1min to save 5000 actions on my i5 core pc)
examples:
".auditLog directory_min/audit.txt 1000"(you can't have a space in the directory name(I'll fix this in the future), and you don't have to create an output file)
or
".auditLog" (output the file with a name of the server name and ID.txt)

## What is a token/how to setup a token
 1. The token for a bot is the profile for the bot. You'll need a profile for the bot to join servers.
 2. Go to [Discord developers site](https://discord.com/developers/applications), login or sign up.
 3. Create a new application or use your created application
 4. Go to the bot tap in the application.
 5. Click on add bot.
 6. And then click on "Click to Reveal Token" or "Copy" to get your token.
