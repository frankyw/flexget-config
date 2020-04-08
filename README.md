# frankyw/flexget

This is a repository to version control my personal flexget configuration. This configuration is used in conjunction with Transmission for downloading and Filebot for post-processing.

## Notes

Be aware of the following:

* This configuration makes heavy use of YML aliases.
* It is 100% private tracker-based, I no longer use public trackers at all.
* Movies are collected from my IMDB watchlist.
* TV series are controlled via two custom Trakt lists.
* Most downloads are fetched in real-time via private tracker IRC announce channels.
* Anything else not downloaded as it is released is downloaded via a periodic search of private trackers.
* Extraction is handled by Filebot called by Transmission through a Python, as Filebot does a far superior job than flexget and is easier to configure.