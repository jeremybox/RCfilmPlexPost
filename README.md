#RCfilmPlexPost: Updates
added RCwrapper.sh to bypass Plex's internal python
you must have python 2.x on your system
in order to run from plex postproccessing you must use the RCwrapper.sh

This script was forked from https://github.com/ekim1337/PlexComskip

The original application was discussed on the plex forums: https://forums.plex.tv/discussion/232408/postproccessing-usage-examples/p1

This script is a complete post processing solution which includes the following functionality:

- Scanning a show and removing commercials
- Transcoding the recorded show from mpeg2 to h264 in order to save space
- Logging of all processing and the option to stash the original file in a safe place in case something goes wrong

Improvements over the original PlexComskip include the following:

- Use of a new comskip.ini from the comskip forums tuned for use with USA broadcast TV
- Option to transcode the now commercial free video to h264 using ffmpeg
- The option to stash the original file in a safe place in case something goes wrong during processing
- Support for NFS based sources. The original script would crash on shares where the ability to set permissions is limited
- A new name to reflect the additional functionality

#Requirements

You will need the following software

- Python 2.7 (or something close to it, you are not getting extensively tested software here)
- MKVToolNix https://mkvtoolnix.download/
- comskip https://github.com/erikkaashoek/Comskip
- ffmpeg (available in pretty much any distribution)
- mediainfo cli version https://mediaarea.net/en/MediaInfo

#Limitations

- This script uses alot of storage during the processing. A 30 minute 1080i show will need 5G or more of space during the processing step
- This was only tested on Linux, further testing is needed for windows

#TODO

- Remove need for mediainfo binary by finding a better way to scan the resolution from the file
- Re-arrange script to only transcode if sanity checks pass
- Filters for shows you don't want to comskip
- Transcode ONLY option
- Rewrite to be better in every way
