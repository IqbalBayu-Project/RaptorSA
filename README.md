# Super advanced discord bot ![alt text](https://i.imgflip.com/xu2ct.jpg)

**RaptorSA** is a multi function bot, you can listen music, manage roles, get various informations and many other things. This Discord bot can be helpful for anyone who wants to learn how to make a discord.js bot, every command has it's own folder so it's more easy to read the entire project. I made this so new users can also look at the methods used for certain commands and get some ideas for their Discord bot. When I was developing the bot I was totally new to node js, I did not even know what was an arrow function. Day by day I learnt discord.js api and node js thanks to various tutorials that I found on internet.

# Contributing

If you want help, don't worry, there are many ways to do it:

* **Contribute with code**: Setup a development environment, make some changes, and [open a pull request](https://github.com/Cramenorn/RaptorSA/pulls).

* **Contribute with ideas**: Have a great idea, but don't know how to code ? No problem! Open an issue so we can talk about your idea.

# Branching

New Pull Requests should be made upon the **testing** branch. If the code does not have any particular issues, then it will be merged into **master** branch.

# Api keys and tokens

Some commands require an **Api Key** or a **Token** which can be find on these websites: 

* [Google Custom Search Api Key and CX](https://developers.google.com/custom-search/)
* [Riot Games Developer](https://developer.riotgames.com/)
* [Discord Developer to get the token for the bot](https://discordapp.com/developers/applications/)

As many of you know i can't provide my **Api Keys**, because i could compromise my security.

# What do i need to make the bot work ?

* You will need [FFmpeg](https://www.ffmpeg.org/) for the play, stop and skip commands, as ytdl-core package needs ffmpeg or it will not work.
* Make a folder and git clone this repository: [RaptorSA.git](https://github.com/Cramenorn/RaptorSA.git).
* Then type **npm install** to get the needed packages (see the next section) for the bot.
* Edit json files in jsonFiles folder, you need a discord bot **Token** and various **Api Keys** to get the bot work.
* Launch the **index.js** file.

# Packages

```json
"discord.js": "^11.6.0",
"discord.js-commando": "^0.10.0",
"discord.js-music-v11": "^1.3.4",
"enmap": "^5.2.4",
"express": "^4.17.1",
"ffmpeg-binaries": "^4.0.0",
"fotology-x": "^1.2.4",
"geolib": "^3.2.1",
"get-json": "^1.0.1",
"google-search-results-nodejs": "^1.3.0",
"googleapis": "^47.0.0",
"jimp": "^0.9.3",
"moment": "^2.24.0",
"opusscript": "^0.0.7",
"overwatch-js": "^1.8.0",
"request": "^2.88.2",
"yql": "^1.0.2",
"yt-search": "^1.1.2",
"ytdl-core": "^2.0.0"
```

# Commands

## Admin

* **$addrole [user] [role]** - Add a role to an user on your server, in order to assign a role the bot role must be above the others.
* **$ban [user] [reason]** - Ban an user from the server.
* **$deletemsg [number]** - Delete an amount of messages, the number must be between 2 and 100.
* **$kick [user] [reason]** - Kick an user from the server.
* **$mute [user] [ms]** - Mute an user for a specific amount of time, you have to create a new role called mute to make the command work.
* **$removerole [user] [role]** - Remove a role of an user.
* **$setbotname [name]** - Set a name for the bot.
* **$setbotstatus [status]** - Set bot status.

## Games

* **$csgo [MySteamID]** - Get csgo stats for an user given by STEAMID64.
* **$csgofloat [inspect Url]** - Get informations about a skin or a weapon.
* **$lolcprot** - Display the current champion rotation in EU West.
* **$loltopfive [SummonerID]** - Display the top 5 played champions of a summoner, based on the SummonerID. You can find your SummonerID at http://www.lolking.net/

## Info

* **$help or $help [commandName]** - Display the list of commands if you just type $help or if you type $help commandName display the current command info.
* **$serverinfo** - Get server info.
* **$serverinvite [ChannelID]** - Get an invite for the server, but you must type the channelID to get the command work.
* **$uptime** - Get bot uptime.
* **$userinfo** - Get your user info.

## Music

* **$deletetrack [PositionNumberInQueue]** - Delete a song from the queue, if you want know your current queue, just type $queue and you will get the songs.
* **$joinchannel** - Make the bot join in a voice channel, you must be in a voice channel.
* **$nowplaying** - Show the currently playing song.
* **$pause** - Pause the currently playing song.
* **$resume** - Resume the currently playing song.
* **$playother [StreamUrl]** - Play a stream url.
* **$playtube [youtubeUrl]** - Play an youtube video.
* **$queue** - List the songs in queue.
* **$skip** - Skip the current playing song.
* **$stop** - The bot leaves the voice channel.
* **$volume [Number]** - Set bot volume in the voice channel, you must type a number betweem 0-200.
* **$ytsearch [SongName]** hit enter then type a **number** - Search for a song on youtube, then type a number between 1-20 (or less).

## Random stuff

* **$distance [latitude1] [longitude1] [latitude2] [longitude2]** - Get the distance between the sets of coordinates
* **$dogs** - Find some cute dog pictures.
* **$flipcoin** - Flip a coin.
* **$google [query]** - Get 3 search queries from Google Custom Search, you need to provide in the json file called googleConfig, your Custom Search Api Key and your CX.
* **$ping** - Ping the bot.
* **$randomcolor** - Generates a random hex color with preview.
* **$rolldice** - Roll a dice.
* **$setafk [status]** - Set your status afk or notafk.
* **$weather [location]** - Get the forecast information for a location.

# Built with
* [Discord.js](https://discord.js.org/#/)
* [Node js](https://nodejs.org/en/)

# Known issues

The google command is not 100% correct, if you do a search query the first result will be correct, but from second above the googleResults.json will corrupt itself. This simply means you will get a wrong query.

## Why the bot does not play music in a voice channel ?

First of all, check if you have installed [FFmpeg](https://www.ffmpeg.org/) and the node modules. If everything is correct but the bot is still not playing the music, open the cmd or terminal and navigate to the root of your repository and type **npm update**.

## Why the music quality is bad ?

There is a Bitrate setting on each voice channel which is defaulted to 64kbps. Click the gear sign next to the voice channel to go to the channel settings and make sure your Bitrate is as high as it will allow. According to GitHub issues on other repositories, Discord channels can reach 96kbps and partnered discord servers can be set up to 128kbps. The music quality also depends from the connection.