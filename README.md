# frankyw/flexget

This is a repository to version control my personal FlexGet configuration. This configuration is used in conjunction with Transmission for downloading, Filebot for post-processing and emby for viewing. You can read more about this [on my blog](https://frankw.net/fully-automated-media-centre-flexget-emby-trakt-imdb/).

## Notes

Be aware of the following:

* This configuration makes heavy use of YML aliases.
* It is 100% private tracker-based, I no longer use public trackers at all due to security concerns.
* Movies are collected from a Trakt Movies watchlist combined with the [Watcht](https://apps.apple.com/us/app/watcht-for-trakt/id1396920723) app, which replaces a broken IMDb-FlexGet solution (and is actually much nicer).
* TV series are controlled via two custom Trakt lists, one for 1080p and one for 4K releases, so I can control what I am getting and don't need to use one list with a "wait" for a good release.
* Most downloads are fetched in real-time via private tracker IRC announce channels.
* Anything else not downloaded in real-time is downloaded via a periodic search of private trackers.
* Extraction is handled by [Filebot-node](https://www.filebot.net/forums/viewtopic.php?t=2663) called by Transmission through a Python script, as Filebot is a) designed for this task, and b) much easier to configure than FlexGet for this.

Combine with a variables.yml file:

    transmission:
      username: xxx
      password: xxx

    trakt:
      account: xxx
      username: xxx
    ...  