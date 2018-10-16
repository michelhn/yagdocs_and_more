You can find all commands of the bot here.

# Prefix

The prefix is by default `-`. The first thing you see when you open the command page is the prefix, you can replace this with your own unique prefix if you would like. Be sure to hit the save button afterward.

# Command Override

To create a command override look for the box that says New command override.

**Apply to the following commands:** Once you are in the box, you can select which command you want to override to apply to.

**Specific commands enabled in this command override:** You can then toggle whether or not to enable or disable the command with this override. (Enable this if you have the command disabled in the global settings).

**Auto delete trigger/response:** Toggle to enable/disable the auto delete for the trigger and response respectively and assign it a time to wait until deleting (1-60 Seconds).

**Require one of these roles:** Choose to require someone to have a role in order to use the commands.

**Ignore users with one of these roles:** Choose to ignore someone who has a role and prevent them from using the command.

# Channel Override

Look to the top right on your screen for a box that says *New channel override*.

**Channels this override affects:** Select which channels you want the override to apply to.

**Include current and future channels from the following categories:** By picking a category, you apply this override to all the channels in the category which includes future channels.

**Require one of these roles:** Choose to require someone to have a role in order to use the commands.

**Ignore users with one of these roles:** Choose to ignore someone who has a role and prevent them from using it.

**All commands enabled:** Enable all the commands for this override, you can create command override for the channel overrides below if you wish to customize further.

**Auto delete trigger/response:** Toggle to enable/disable the auto delete for the trigger and response respectively and assign it a time to wait until deleting (1-60 Seconds).

**New command override:** Create a command override that will apply to all the channels in the channel override. For help on creating command overrides, refer to [Command override](#command-override)

# Command List

*You may get a list of every command by typing* `-help` on *your server.*<br/>
*You may also get more specific help by typing* `-help` *(command)* 

## General

|Command|Aliases         |Optional Args|Description                                       |
|-------|----------------|-------------|--------------------------------------------------|
|help   |h,how,command(s)|(command)    |Shows help for all or one specific command.       |
|info   |N/A             |N/A          |Response with bot information.                    |
|invite |inv,i           |N/A          |Response with the bot website link for invitation.|

## Tools & Utilities

|Command       |Aliases                 |Required Args                      |Optional Args                   |Description                                       |
|--------------|------------------------|-----------------------------------|--------------------------------|--------------------------------------------------|
|prefix        |N/A                     |N/A                                |(serverID)                      |Shows the command prefix on current server or specified server.|
|calc          |c,calculate             |(what to calculate)                |N/A                             |Calculator. Example: `2+2`|
|ping          |N/A                     |N/A                                |N/A                             |Response with pong and pingtime.|
|currenttime   |ctime, gettime          |N/A                                |(timezone) (delta time in hours)|Shows UTC time, or the timezone you chose.  List of [timezones](https://pastebin.com/ZqSPUhc7)|
|mentionrole   |mrole                   |rolename                           |N/A                             |Sets a role to mentionable, mentions the role, then sets it back to not mentionable after 30 seconds.|
|listroles     |N/A                     |N/A                                |N/A                             |List roles and their IDs, and some other stuff on the server.|
|poll          |N/A                     |(description) (option 1) (option 2)|(option3) etc                   |Creates a reaction poll.|
|undelete      |ud                      |N/A                                |-a                              |Views your recent deleted messages, or all users deleted messages (with "-a" and manage messages perm) in this channel.|
|viewperms     |N/A                     |(mention/ID)                       |N/A                             |Shows you requested user's permissions in this channel.|
|stats         |N/A                     |N/A                                |N/A                             |Shows server stats (only if public stats are enabled).|
|customcommands|cc                      |N/A                                |(commandID) (trigger string)    |Shows a custom command specified by id or trigger or lists them all. [More info](/commands-1/custom-commands).|
|logs          |ps, paste, pastebin, log|N/A                                |(count)                         |Creates a log of the channels messages (max. 100).|
|whois         |whoami                  |N/A                                |(username)                      |Shows information about given member.|
|nicknames     |nn                      |N/A                                |(username)                      |Shows past nicknames of given member.|
|usernames     |unames, un              |N/A                                |(username)                      |Shows past usernames of given member.|
|remindme      |remind                  |(time) (message)                   |N/A                             |Schedules a reminder. Example: `remindme 1h30min are you still alive?`|
|reminders     |N/A                     |N/A                                |N/A                             |List of your active reminders with an ID.|
|creminders    |N/A                     |N/A                                |N/A                             |Lists reminders only in the current channel with an ID. Only members with `manage server` permissions can use this command.|
|delreminders  |rmreminder              |(ID)                               |N/A                             |Deletes the reminder with the given ID.|
|role          |N/A                     |N/A                                |(rolename)                      |Give yourself a role or list all available roles. Needs to be set up first on the control panel.|

## Moderation

|Command       |Aliases  |Required Args          |Optional Args     |Description                               |
|--------------|---------|-----------------------|------------------|------------------------------------------|
|ban           |banid    |(username) or (userID) |(reason)          |Bans given member by name mention or ID.  |
|kick          |N/A      |(username) or (userID) |(reason)          |Kicks given member by name mention or ID. |
|mute          |N/A      |(username)             |(minutes) (reason)|Mutes given member.                       |
|unmute        |N/A      |(username)             |(reason)          |Unmutes given member.                     |
|report        |N/A      |(username)             |(reason)          |Reports given member.                     |
|clean         |clear, cl|(count)                |(username)        |Cleans the chat.                          |
|reason        |N/A      |(ID) (reason)          |N/A               |Add/Edit modlog reason from given ID.     |
|warn          |N/A      |(username) (reason)    |N/A               |Warns given member. Warnings are saved.   |
|warnings      |N/A      |(username)             |N/A               |Lists warnings of given member with an ID.|
|editwarnings  |N/A      |(ID) (reason)          |N/A               |Edit given warning.                       |
|delwarnings   |dw       |(ID)                   |N/A               |Deletes the warning with the given ID.    |
|clearwarnings |clw      |(username) or (userID) |N/A               |Clears all warnings from given member.    |
|automod toggle|t        |(Ruleset)              |N/A               |Toggles a ruleset on/off.                 |

## FUN

|Command       |Aliases          |Required Args        |Optional Args                  |Description                         |
|--------------|-----------------|---------------------|-------------------------------|------------------------------------|
|define        |df               |(topic/string)       |N/A                            |Looks for an Urban Dictionary definition.|
|reverse       |r, rev           |(text)               |N/A                            |Reverse the text given.|
|weather       |w                |(location)           |N/A                            |Show the weather for the given location.|
|topic         |N/A              |N/A                  |N/A                            |Generates a chat topic.|
|catfact       |cf, cat, catfacts|N/A                  |N/A                            |Catfacts. What else?!|
|advice        |N/A              |N/A                  |(for?)                         |Get some advice. **NB!** Currently not working.|
|throw         |N/A              |N/A                  |(username)                     |Throws random stuff at nearby people or at the given member.|
|roll          |N/A              |N/A                  |(number of sides)              |Roll a dice. Specify nothing for 6 siddes, or specify a number for max. sides.|
|customembed   |ce               |(json)               |N/A                            |Creates an embed from what you give it in json form: [Embed Object](https://discordapp.com/developers/docs/resources/channel#embed-object)|
|wouldyourather|wyr              |N/A                  |N/A                            |Presents you with 2 choices. Somewhat NSFW text wise.|
|topservers    |N/A              |N/A                  |(skip:number - entries to skip)|Responds with the top 15 servers the bot is on.|
|takerep       |-, tr, trep      |(username)           |(count)                        |Takes away given number of rep from given member. Default number is 1.|
|giverep       |+, gr, grep      |(username)           |(count)                        |Give given number of rep to given member. Default number is 1.|
|setrep        |setrepID         |(mention/ID) (number)|N/A                            |Sets someones rep, by mention or ID. This is a rep admin command (manage server perms. or rep admin role) and bypasses cooldowns and other restrictions.|
|delrep        |N/A              |(mention/ID)         |N/A                            |Deletes someone from the reputation list completely. This is a rep admin command and bypasses cooldowns and other restrictions. This action cannot be undone.|
|replog        |N/A              |(mention/ID)         |(page number)                  |Shows specified user's rep log. Longer logs are divided into pages.|
|rep           |N/A              |N/A                  |(username)                     |Shows your or the given member's current rep and rank.|
|toprep        |N/A              |N/A                  |(offset)                       |Shows top 15 rep members on the server.|
|sentiment     |sent             |N/A                  |(text)                         |Does sentiment analysis on the given text or your last 5 messages longer than 3 words.|
|8ball         |N/A              |(question)           |N/A                            |Wisdom.|
|soundboard    |sb               |N/A                  |(soundname)                    |Play or list soundboard sounds.|

### Cards Against Humanity

Everything here starts with cah such as `-cah create`

|Command|Aliases|Required Args|Optional Args|Description                                                                 |
|-------|-------|-------------|-------------|----------------------------------------------------------------------------|
|create |c      |N/A          |(pack name)  |Creates a cards against humanity game in this channel.                      |
|end    |N/A    |N/A          |N/A          |Ends a cards against humanity game that's ongoing in this channel.          |
|kick   |N/A    |(user)       |N/A          |Kicks a player from the ongoing cards against humanity game in this channel.|
|packs  |N/A    |N/A          |N/A          |Lists available packs.                                                      |


## Rolemenu

Everything here starts with rolemenu such as `-rolemenu create`

|Command       |Aliases|Required Args     |Optional Args                       |Description   |
|--------------|-------|------------------|------------------------------------|--------------|
|create        |c      |(rolegroup's name)|(m:messageID)(nodm)(rr)(skip:number)|Sets up a role menu, specify a message with **-m** to use an existing message instead of having the bot make one. **-nodm, -rr** are  switches - first one enables/disables DM response and second one alters reaction removed state, by default reaction removed is also role removed.**-skip** Skips certain number of roles in that rolegroup, if not needed in that rolemenu.|
|remove        |N/A    |(messageID)       |N/A                                 |Removes the rolemenu from a message, the message wont be deleted but the bot will now not do anything with reactions on that message.|
|update        |u      |(messageID)       |(nodm)(rr)                          |Updates a rolemenu, toggling the provided flags and adding missing options, aswell as updating the order.|
|resetreactions|reset  |(messageID)       |N/A                                 |Removes all reactions on this menu and re-adds them, can be used to fix the order.|
|editoption    |edit   |(messageID)       |N/A                                 |Allows you to reassign the emoji of an option, tip: use ResetReactions afterwards.|

## Debug

|Command      |Aliases |Otional Args   |Description                                               |
|-------------|--------|---------------|----------------------------------------------------------|
|yagstatus    |status  |N/A            |Shows YAGPDB's status.                                    |
|currentshard |cshard  |N/A            |Shows the current shard this server is on.                |
|memberfetcher|memfetch|N/A            |Shows the current status of the member fetcher.           |
|roledbg      |N/A     |N/A            |Debug autorole assignment.                                |
|stateinfo    |N/A     |N/A            |Responds with state debug info.                           |
|topcommands  |N/A     |(hours: number)|Shows command usage stats, defaults to last hour.         |
|topevents    |N/A     |(shard: number)|Shows gateway event processing stats for all or one shard.|

## Administrative (only for self-hosting)

|Command     |Aliases|Required Args|Optional Args|Description                                                    |
|------------|-------|-------------|-------------|---------------------------------------------------------------|
|allocstat   |N/A    |N/A          |N/A          |Memory statistics.                                             |
|leaveserver |N/A    |(ID)         |N/A          |Makes the bot leave a server by ID.                            |
|banserver   |N/A    |(ID)         |N/A          |Makes the bot leave and ban a server by ID.                    |
|unbanserver |N/A    |(ID)         |N/A          |Makes the bot unban a server by ID.                            |
|findserver  |N/A    |(name)(user) |N/A          |Looks for a server by server name or the servers a user was on.|
|createinvite|N/A    |(ID)         |N/A          |Maintenance command, creates a invite for the specified server.|