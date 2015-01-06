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

I archive my library using FLAC because it is a popular, free, open and lossless format. The ripping process is time-consuming and in the event of improving my speaker set up (or ears!), or more realistically if storage formats change in the future, I do not want to have to rip my audio CDs again. While FLAC suits my archival purposes nicely, it is not the most appropriate format for playback on all devices. For example, my portable music player has limited memory and relatively low quality headphone output, so low bitrate MP3 or Ogg Vorbis files prove more economical here.

I use the scripts included in this repository to transcode from the lossless FLAC masters to an appropriate format for the device in question, and to help organise and verify the integrity of the library.

## Script dependencies

* [sox](http://sox.sourceforge.net/) for transcoding.
* flac
* oggenc (vorbis-tools package)
* lame
* id3v2
* dos2unix

## Organisational principles, and how they are implemented

Anyone who cares to maintain a large digital audio library will have their own preferences about how it should be organised. These preferences can change over time, perhaps as a collection grows or new genres of music are explored. I have tried to come up with a set of principles to guide my decisions.

1. An audio backup represents the thing it came from as closely as possible.
  * e.g. if a track title has multiple spellings, use the spelling given on the medium being backed up.
  * e.g. if an artist releases albums under multiple names each backup is given the artist name for that particular album, so that previously backed up albums do not require alteration.
1. Different types of things are stored separately and do not have to be consistent.
  * i.e. the formatting of digitally delivered files need not be modified in an attempt to make it consistent with a CD backup.
1. Integrity, validity and quality of the backup is important.
  * i.e. backups should be made once at the best possible quality.
  * i.e. naming things accurately and consistently (where possible) is worth doing.
1. Backups should be flexible and future-proof.
  * i.e. use open and lossless formats, and transcode to lesser formats on demand.

The scripts are designed to work with my preferred file hierarchy, which looks like this:
```
audio
├── albums
│   └─ Artist Name - Album Name
│      ├── 01 Track Title.flac
│      ├── 02 Track Title.flac
│      ├── Album Name.cue
│      ├── Artist Name - Album Name.log
│      ├── Artist Name - Album Name.m3u
│      └── checksum.md5
├── eps
│   └─ Artist Name - Album Name
│      ├── 01 Track Title.flac
│      ├── 02 Track Title.flac
│      ├── Album Name.cue
│      ├── Artist Name - Album Name.log
│      ├── Artist Name - Album Name.m3u
│      └── checksum.md5
├── downloads
│   └─ Example Download
│      ├── cover.jpg
│      ├── 01 Track Title.format
│      └── 02 Track Title.format
```

## Licence

This repository and its contents are covered by the MIT licence. See MIT-LICENSE.txt for details.
