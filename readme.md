# home server

Being used in Unraid with the Docker Compose Manager plugin.

## projects

### streaming

Custom Plex server setup for creating libraries of streaming media sourced from Real-Debrid. Allows you to add content to arrs like usual, but instead of downloading the content you can utilise Real-Debrid, which has a giant cache of pretty much every torrent ever. This means you can download torrents directly from them, at your maximum download speed, without having to rely on peers. Using this, you can:

- Mount your Real-Debrid account's added files to the filesystem using `rclone mount` and [zurg](https://github.com/debridmediamanager/zurg-testing) as a webdav server. Now all your added media are available as files in a mount, with the contents being downloaded only as they're played.
- Set up [the blackhole script by westsurname](https://github.com/westsurname/scripts) as a custom torrent downloader in the arrs. This will automatically add torrents to your Real-Debrid account and create symlinks to your zurg mount.

From there, the arrs can use these symlinks like normal files and continue like usual. The media will be renamed and organised like it's been fully downloaded. Your content will show up in Plex and will be able to be played back with no issues, and the total storage use is negligible as all that's stored is metadata.

Pros:

- Infinite storage
- Don't need to wait for content to download (only wait is media processing times, a 48gb movie took 2m30s to appear in Plex after adding it in Radarr with my setup)

Cons:

- Video start times and seeking are slower
- Takes longer to scan for intros/credits/etc.

Notes:

- You need to remove minimum sizes for qualities in Sonarr since season packs don't report sizes properly in the torrentio indexers atm
- Recyclarr doesn't set language for quality profiles, so I needed to set it in radarr to be 'original' since I don't want dubs.

For more information on this sort of setup check out:

- [Ragnarok Discord server](https://discord.gg/wDgVdH8vNM)
- [A Sailarr’s Guide to Plex + Real-Debrid](https://puksthepirate.notion.site/puksthepirate/eebe27d130fa400c8a0536cab9d46eb3)
- [plex-debrid (outdated)](https://github.com/itsToggle/plex_debrid)
