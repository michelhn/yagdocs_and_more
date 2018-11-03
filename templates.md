The go template engine is used for YAGPDB's custom commands and in various other places with custom messages. This page aims to help you to get the most out of templates and custom commands.

# Available template data:


## User

|Field                |Description                                                                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
|.User                |The user's username together with discriminator.                                                                                             |
|.User.Username       |The user's username.                                                                                                                         |
|.User.ID             |The user's ID.                                                                                                                               |
|.User.Discriminator  |The users's discriminator (The four digits in a person's username).                                                                          |
|.User.Avatar         |The user's avatar ID.                                                                                                                        |
|.User.AvatarURL "256"|Gives the URL for user's avatar, argument "256" is the size of the picture and can increase/decrease twofold (e.g. 512, 1024 or 128, 64 etc.)|
|.User.Bot            |Determines whether the target user is a bot - if yes, it will return True.                                                                   |
|.User.Mention        |Mentions user.                                                                                                                               |
|.RealUsername        |Only works with join and leave messages. This can be used to send the real username to a staff channel when invites are censored.            |
|.UsernameHasInvite   |Only works with join and leave messages. It will determine does the username contain an invite link.                                         |


## Guild / Server

|Field                   |Description                                                                         |
|------------------------|------------------------------------------------------------------------------------|
|.Guild.ID               |Outputs the ID of the guild.                                                        |
|.Guild.Name             |Outputs the name of the guild.                                                      |
|.Guild.Icon             |Outputs the ID of the guild's icon.                                                 |
|.Guild.Region           |Outputs the region of the guild.                                                    |
|.Guild.AfkChannelID     |Outputs the AFK channel ID.                                                         |
|.Guild.OwnerID          |Outputs the ID of the owner.                                                        |
|.Guild.JoinedAt         |Outputs when the first userjoined the guild.                                        |
|.Guild.AfkTimeout       |Outputs the time when a user gets moved into the AFK channel while not being active.|
|.Guild.MemberCount      |Outputs the number of users on a guild.                                             |
|.Guild.VerificationLevel|Outputs the required verification level for the guild.                              |
|.Guild.EmbedEnabled     |Outputs whether embeds are enabled or not, true / false.                            |


## Member

|Field        |Description                             |
|-------------|----------------------------------------|
|.Member.Nick |The nickname for this member.           |
|.Member.Roles|A list of role IDs that the member has. |


## Channel

|Field         |Description                                 |
|--------------|--------------------------------------------|
|.Channel.Name |The Name of the channel.                    |
|.Channel.ID   |The ID of the channel.                      |
|.Channel.Topic|The Topic of the channel.                   |
|.Channel.NSFW |Outputs whether this channel is NSFW or not.|


## Current User

|Field                |Description                                                                                       |
|---------------------|--------------------------------------------------------------------------------------------------|
|currentUserCreated   |The time the current user was created.                                                            |
|currentUserAgeHuman  |The account age of the current user in more human readable format (`3 days 2 hours`, for example).|
|currentUserAgeMinutes|The account age of the current user in minutes.                                                   |


## Functions

|# |Field                                      |Description                                                                                       |
|--|-------------------------------------------|--------------------------------------------------------------------------------------------------|
|01|`adjective`                                |Returns a random adjective.|
|02|`dict key1 value1 key2 value2 etc`         |Creates a dictionary (not many use cases yet).|
|03|`sdict "key1" "value1" "key2" "value2" etc`|The same as `dict` but with only string keys and can be used in `cembed`.|
|04|`cslice value1 value2 etc`                 |Creates a slice (similar to array) that can be used elsewhere (`cembed` and `sdict` for example).|
|05|`cembed "list of embed values"`            |Function to generate embed inside custom command. [More in-depth here.](/custom-embeds#embeds-in-custom-commands)
|06|`in list value`                            |Returns true if value is in list.|
|07|`add x y`                                  |Returns x + y.|
|08|`seq start stop`                           |Creates a new array of integer, starting from start and ending at stop.|
|09|`shuffle list`                             |Returns a shuffled version of a list.|
|10|`joinStr seperator str1 str2`              |Joins several strings into one, seperated by the first arg the separator, useful for executing commands in templates (e.g.`{{joinStr "" "1" "2" "3"}} = "123")`|
|11|`randInt (stop, or start stop)`            |Returns a random integer between 0 and stop, or start - stop if two args are provided.|
|12|`toString`                                 |Converts something into a string. Usage: `(toString x)`|
|13|`toInt`                                    |Converts something into an integer. Usage: `(toInt x)`|
|14|`toInt64`                                  |Converts something into an int64. Usage: `(toInt64 x)`|
|15|`sendDm "message"`                         |Sends the user a direct message, only one DM can be sent per template (accepts embed objects).|
|16|`sendMessage channel_name message`         |Sends message (string or embed) in channel_name, channel can be either nil, the channel ID or the channel's name.|
|17|`sendMessageNoEscape channel_name message` |send message (string or embed) in channel_name, channel can be either nil, the channel ID or the channel name. Doesn't escape mentions (e.g. role mentions or @here/@everyone)|
|18|`mentionEveryone`                          |Mentions @everyone.|
|19|`EscapeEveryone "input"`                   |Escapes everyone mentions in a string.|
|20|`mentionHere`                              |Mentions @here|
|21|`escapeHere "input"`                       |Escapes here mentions in a string.|
|22|`escapeEveryoneHere`                       |Escapes everyone and here mentions in a string.|
|23|`mentionRoleName "rolename"`               |Mentions the first role found with the provided name (case insensitive).|
|24|`mentionRoleID roleID`                     |Mentions the role found with the provided ID.|
|25|`hasRoleName "rolename"`                   |Returns true if the user has the role with the specified name (case insensitive).|
|26|`hasRoleId roleID`                         |Returns true if the user has the role with the specified ID (use the listroles command for a list of roles).|
|27|`addRoleID roleID`                         |Add the role with the given ID to the user that triggered the command (use the listroles command for a list of roles).|
|28|`removeRoleID roleID`                      |Remove the role with the given ID from the user that triggered the command (use the listroles command for a list of roles).|
|29|`giveRoleName usermention rolename`        |Gives a role by name to the target.|
|30|`giveRoleID usermention roleID`            |Gives a role by ID to the target.|
|31|`takeRoleName usermention rolename`        |Takes away a role by name from the target.|
|32|`takeRoleID usermention roleID`            |Takes away a role by ID from the target.
|33|`deleteResponse time`                      |Deletes the response after a certain time  (1-60 seconds).|
|34|`deleteTrigger time`                       |Deletes the trigger after a certain time (1-60 seconds).|
|35|`addReactions "👍" "👎"`                    |Adds each emoji as a reaction to the message that triggered the command (recognizes Unicode emojis and `emojiname:emojiID`).|
|36|`addResponseReactions "👍" "👎"`            |Adds each emoji as a reaction to the response message (recognizes Unicode emojis and emojiname:emojiid).|
|37|`exec "command" "args" "args" etc`         |Execute a YAGPDB's command (e.g. reverse, roll, kick etc) in a custom command. Max exec can be run 5 times per command. |
|38|`execAdmin "command" "args" "args" etc`    |Functions the same way as exec but will override any permission requirement (such as the kick permission to use kick command etc.).|
|39|`userArg ######`                           |Function that can be used to retrieve a user from a mention string or ID.|
|40|`currentTime`                              |Gets the current time which can be used in an custom embed.|
|41|`.cmdArgs`                                 |Get all the arguments passed to the command.|
|42|`slice "string" integer`                   |Outputs the "string" after cutting/slicing off integer (numeric) value of symbols - e.g. `{{slice "Fox runs" 2}}`outputs `x runs`. For slicing whole words see example below in Snippets.|
|43|`lower "string"`                           |Convert the string to lowercase.|
|44|`title "string"`                           |Returns string with the first letter of each word capitalized.|


## Branching

|Case        |Example                                                     |
|------------|------------------------------------------------------------|
|Basic if    |`{{if (condition)}}{{end}}`                                 |
|Not         |`{{if not (condition)}}{{end}}`
|And         |`{{if and (cond1) (cond2) (cond3)}}`                        |
|Or          |`{{if or (cond1) (cond2) (cond3)}}`                         |
|Equals      |`{{if eq .Channel.ID ########}}`                            |
|Not Equal   |`{{if ne .Channel.ID #######}}`                             |
|Less than   |`{{if lt (len .Args) 5}}`                                   |
|Greater than|`{{if gt (len .Args) 1}}`                                   |
|Else if     |`{{if (case statement}} {{else if (case statement}} {{end}}`|
|Else        |`{{if (case statement}} {{else}} output here {{end}}`       |


## Snippets

* `<@{{.User.ID}}>` Outputs a mention to the user that called the command.
* `<@###########>` Mentions the user that has the ID ###### ([See How to get IDs to get ID](#how-to-get-ids)).
* `<@&###########>` Mentions the role that has ID ###### ([See How to get IDs to get ID](#how-to-get-ids)).
* `<#&&&&&&&&&&&>` Mentions the channel that has ID &&&&&& ([See How to get IDs to get ID](#how-to-get-ids)).
* `{{if hasRoleName "funrole"}} Has role funrole {{end}}`This will only show if the member has a role with name "funrole" .
* `{{if gt (len .Args) 0}} {{index .Args 1}} {{end}}` Assuming your trigger is a command, will display your first input if input was given.
* `{{if eq .Channel.ID #######}}` Will only show in Channel #####.
* `{{if ne .User.ID #######}}` Will ignore if user ID ##### uses command.
* `{{$d := randInt 10}}` Store the random int into variable $d (A random number from 0-9).
* `{{addReactions .CmdArgs}}` Adds the emoji following a trigger as reactions.
* `{{$a := (exec "catfact")}}` Saves the response of the **catfact** command to variable `$a`. 
* `{{$allArgs := (joinStr " " .CmdArgs)}}` Saves all the argument to a variable $allArgs. 
* `{{$args:= (joinStr " " (slice .CmdArgs 1))}}`  Saves all the arguments except the first one to a variable `$args`. 


# How to get IDs

**User IDs:** Can be found by mentioning the user then adding a \ such as `\@jonas747#0001`. Alternatively if you have developer mode on, you can right click and select Copy ID.

**Channel IDs:** Can be found by mentioning the channel then adding a \ such as `\#announcements`. Alternatively if you have developer mode on, you can right click on the channel and select Copy ID.

**Role IDs:** Use the `listroles` command.

**Emote IDs:**

If it is a **custom emote**, adding a \ in front of the emote such as `\:yagpdg:` will display the name along along with the ID such as `<:yag:277569741932068864>`.

If it is an **animated emote**, do the same steps as a normal emote. If you do not have Discord Nitro, you can have a friend or a bot use the emote and right click on the emote to open its link. The ID will be a part of the URL.

If it is a **default emote**, look up the Unicode for the emote on google. Note that some of the more customize default emote such as some of the family emotes will not work in any of Yag Commands. 