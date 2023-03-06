## frankyw/flexget-config

### ARCHIVED: This repository has been archived as I am no longer using Flexget, and instead have switched to the *arr stack. You can view the [home-server](https://github.com/frankyw/home-server) repo for more info.

This is a repository to version control my personal FlexGet configuration. This configuration is used in conjunction with [Transmission](https://transmissionbt.com/) for downloading, [Filebot](https://www.filebot.net/) for post-processing and extraction, and [Emby](https://emby.media/) for viewing. You can read more about this [on my blog](https://frankw.net/fully-automated-media-centre-flexget-emby-trakt-imdb/).

## Notes

### List Management

* TV shows are managed via two custom Trakt lists, one for 1080p and one for 4K releases.
	* This provides the granularity to control which TV shows should be downloaded in which resolutions, without hard coding the configuration.
	* It is also preferable to using one list, which results in either delays waiting for a quality we know is not available - or having to upgrade qualities later, thereby wasting bandwidth.
	* Begin episodes are set by adding the begin episode to the relevant Trakt list; FlexGet will set the begin episode, and then update the list, replacing the episode with the show.
* Movies are also managed using a Trakt list, allowing for TV/Movie management in one location.
* Movies are removed from the Trakt list after being downloaded; TV Shows are removed from Trakt lists when they have ended or are cancelled.
* The custom lists are easily managed with the [Watcht](https://apps.apple.com/us/app/watcht-for-trakt/id1396920723) App, although there is also now a [Trakt App](https://trakt.tv/apps).

**Note:** do not use the default Trakt Watchlist, this could cause problems as list items are removed when scrobbled. Use custom lists instead.

### Downloading

* This config is 100% private tracker-based, I no longer use public trackers due to security/privacy concerns. A VPN may also be advisable, depending on your jurisdiction. As of April 2022, I use and recommend [Mullvad](https://mullvad.net/).
* Most downloads are fetched in real-time via private tracker IRC announce channels. Immediate downloading of torrents is helpful on ratio sites to maintain ratio.
* Anything not downloaded in real-time via IRC (e.g. offline, added after release, etc) is downloaded via a periodic search of private trackers using the Discover plugin.
* Downloads are seeded for 2 weeks, or until my ratio target (4.0) set in Transmission is met. Cleanup is done using a FlexGet scheduled task.
* When new downloads are started, a push notification is sent to the [Pushover app](https://pushover.net/) (worth paying for), providing details of the download to my mobile device.

### Extraction

* Extraction is handled by [Filebot-node](https://www.filebot.net/forums/viewtopic.php?t=2663), triggered by Transmission upon torrent completion via a Python script. The script makes a http call to begin extraction and placement into the media library.
* I use (and highly recommend) Filebot for this task because it is:
	1. specifically designed for this task
	2.  _much_ easier to configure than FlexGet for this purpose, judging by some of the configs I have seen.

### Miscellaneous

* To use this FlexGet config, it needs to be combined with a variables.yml file, see the example file provided.
* This config runs inside a docker container, I recommend [Wiserain's FlexGet container](https://github.com/wiserain/docker-flexget). An example config can be found in my [home-server repo](https://github.com/frankyw/home-server).
