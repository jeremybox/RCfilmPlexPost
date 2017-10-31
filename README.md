#RCfilmPlexPost Updates:

October/31/2017

Ok to save space on my NAS drives and to become more MacOS compatible. I have updated the code to a mp4 container & FFmpeg will transcode HEVC. I have included the vtag hvc1 for the Mack OS and iOS compatibility. This means that if you update your iOS and TVos profiles to allow direct play of HEVC and of course you’re running iOS 11 then you will have a great day. 

I have currently tested this with resolutions all the way to 4K with my Apple TV 4K

It takes my server about 45 minutes to transcode at 1080 broadcast of one hour. Before this was about a 1 to 3 GB file. Now the total file size is around 350 to 400 MB for the same quality

You can of course tweak all the settings to your own liking

October/20/2017

I added a RCwrapper.sh to bypass the Plex internal python.
RCfilmPlexPost requires python 2.x on your system to run so if you don’t have it install one and run with env. 

In order to run from the Plex postproccessing you must use the RCwrapper.sh

Files that will need to be edited to work with your system.

RCwrapper.sh

Copy RCfilmPlexPost.conf then edit

Test with ./RCFilmPlexPost.py in cli first then test in Plex with RCwapper.sh




This script was forked from https://github.com/ekim1337/PlexComskip

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
