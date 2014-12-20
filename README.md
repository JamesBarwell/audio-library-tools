audio-library-tools
===================

My scripts and configuration to help organise my audio library.

## Audio CD backup process

1. Insert audio CD and open [EAC](http://www.exactaudiocopy.de/)
1. Detect gaps
1. Fetch and check track naming
1. Rip CD
1. Compress to FLAC
1. Record EAC ripping log
1. Record CUE
1. Create M3U
1. Make MD5 checksum of FLAC, CUE and log
1. Backup

## Purpose and use

I archive my library using FLAC because it is a popular, free, open and lossless format. The ripping process is time-consuming and in the event of improving my speaker set up, or improvements in lossy compression formats, I do not want to have to rip my audio CDs again. While FLAC suits my archival purposes nicely, it is not the most appropriate format for playback on all devices. For example, my portable music player has limited memory and relatively low quality headphone output, so low bitrate MP3 or Ogg Vorbis files prove more economical here.

I use the scripts included in this repository to transcode from the lossless FLAC masters to an appropriate format for the device in question, and to help organise and verify the integrity of the library.

## Script dependencies

* [sox](http://sox.sourceforge.net/) for transcoding.
* flac
* oggenc (vorbis-tools package)
* lame
* id3v2
* dos2unix

## Licence

This repository and its contents are covered by the MIT licence. See MIT-LICENSE.txt for details.
