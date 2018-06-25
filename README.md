audio-library-tools
===================

My scripts, configuration and notes to help organise my audio library.

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

My music library is mostly CD based. I continue to use CDs because they offer high-quality digital audio, actual ownership and often a connection to the source of artwork (e.g. many were bought directly from the artists).

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

1. An audio backup represents the medium it came from as closely as possible.
  * e.g. if a track title has multiple spellings on different albums, use the spelling given on the particular album being backed up.
  * e.g. if an artist releases albums under multiple names, each backup is given the artist name for that particular album, so that previously backed up albums do not require alteration.
2. Different types of things are stored separately and do not have to be consistent.
  * i.e. the formatting of a backed-up LP, or digitally delivered files, need not be identical to a CD backup.
3. Integrity, validity and quality of the backup is important.
  * i.e. backups should be made once at the best possible quality.
  * i.e. taking time to name things accurately and consistently is worth doing.
4. Backups should be flexible and future-proof.
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

## Organisational strategies

* avoid making changes to source or transcoded files. Instead, use symlinks and playlists, which are flexible, to deal with display preferences which may be particular to your tastes or the way your media player organises files.
** e.g. if an artist has released multiple albums under different names, and you want to group them all by the latest name, create playlists under the latest name that reference the track files under the mixed artist naming.

## Backup policy

Backups are kept on two portable hard-drives, one of which must always be kept offline and in a separate physical location.

## Licence

This repository and its contents are covered by the MIT licence. See MIT-LICENSE.txt for details.
