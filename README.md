# Lethe
Simple YouTube playback bot for Discord. Warning: Lethe is absolutely not stable at all! It is likely to either not run at all or crash soon after running. If you experience anything like that, please report an [issue](https://github.com/meew0/Lethe/issues)!

## Dependencies
* The ones in package.json
* ffmpeg, it needs to be installed and in your path

Until hydrabolt/discord.js#60 is fixed, `next` and `destroy` won't work. You can try removing the offending line in discord.js, however there's no guarantee that it'll work.

If node-opus is not present, playback will silently fail. Make sure it's installed correctly (it requires Python). See #9.

## Usage
Run Lethe using the email and password as command line arguments:

```
$ node lethe.js email@example.com hunter2 YouTube-api-key(optional)
```

Then, run commands over Discord using the bot's username mention as a prefix, for example:

```
@Bot init
```

Where "Bot" is your bot's username.

## Commands

`init [voice channel name]`: Initializes Lethe and binds it to the text channel this command was run in and the specified voice channel. If no voice channel was specified, the first available one will be used (usually General).  
`destroy`: Destroys Lethe's binding. This stops the current playback and unbinds it from the text and voice channel.

The following commands will only work inside the text channel Lethe was bound to.

`yt [id]`: Queues a video from YouTube to be played. If this is the only song in the queue, start playback. `queue [id]` does the same thing, as does `play [id]`. `id` can be replaced with a keyword used to save a video using `save`.  
`list`: Lists the videos on the queue.  
`next`: Stops the current playback and skips to the next video in the queue.  
`save [id] [keyword]` Saves a video under a keyword. It can later be played back using `yt`.  
`time`: Gets the time the video is currently at.  
`yq [search-value]`: Searches a youtube video that matches the search value.  
`pl [playlist-id]`: Queues the 50 first videos of a playlist.
