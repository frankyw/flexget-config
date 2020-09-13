## frankyw/flexget-config

This is a repository to version control my personal FlexGet configuration. This configuration is used in conjunction with Transmission for downloading, Filebot for post-processing and emby for viewing. You can read more about this [on my blog](https://frankw.net/fully-automated-media-centre-flexget-emby-trakt-imdb/).

## Notes

Be aware of the following:

* This configuration makes heavy use of YML aliases.
* It is 100% private tracker-based, I no longer use public trackers at all due to security concerns.
* Movies are collected from a Trakt Movies watchlist combined with the [Watcht](https://apps.apple.com/us/app/watcht-for-trakt/id1396920723) app, which replaces a broken IMDb-FlexGet solution (and is actually much nicer).
* TV series are controlled via two custom Trakt lists, one for 1080p and one for 4K releases. This provides the granularity to control which TV shows should be downloaded in which resolutions, without hard coding the configuration. This is also preferable to using one list, which results in an unnecessary delay waiting for a higher quality release for all shows, even when we know there is not one coming.
* Most downloads are fetched in real-time via private tracker IRC announce channels.
* Anything else not downloaded in real-time is downloaded via a periodic search of private trackers.
* Extraction is handled by [Filebot-node](https://www.filebot.net/forums/viewtopic.php?t=2663) called by Transmission through a Python script, as Filebot is a) designed for this task, and b) much easier to configure than FlexGet for this.
* The custom-cont-init.d folder contains scripts that install custom packages, and are specific to the [Wiserain FlexGet container](https://github.com/wiserain/docker-flexget). They can safely be ignored if you are just interested in FlexGet configuration.

Combine with a variables.yml file:

    transmission:
      username: xxx
      password: xxx

    trakt:
      account: xxx
      username: xxx
    ...  