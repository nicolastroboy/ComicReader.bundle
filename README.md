Comics (fork of coryo/ComicReader.bundle)
===========

A Plex Media Server channel.

Browse and view locally stored CBZ, CBR, CB7 comic book archives. It currently acts like a file browser, starting at the directory specified in the channels preferences.

Each user of the channel will have their reading status saved for each comic. Comics can be marked as read/unread and can be resumed from your previous position.

Why a fork ?
------------
I needed something more adapted to my taste :
- Simplier name
- Minimalistist icons
- Less settings
- Read/Unread/InProgress round icons
- No 'user switching' feature
- French translation
- ...

Format Support
--------------

* .CB**Z** - the ideal format for the channel. Consider converting archives to zip, it's much easier to work with.
* .CB**R** - requires [unrar](http://www.rarlab.com/download.htm).
* .CB**7** - requires [7-Zip](http://www.7-zip.org/download.html) (windows). or [p7zip](http://p7zip.sourceforge.net) (linux, osx).


.zip, .rar, and .7z should also work.

#### Windows

 * [unrar](http://www.rarlab.com/rar/unrarw32.exe)
 * [7-Zip](http://www.7-zip.org/download.html)
 * set channel preferences paths:
   * `C:\Program Files (x86)\WinRAR\unrar.exe` if you installed WinRAR, or `C:\wherever\unrar.exe`
   * `C:\Program Files (x86)\7-Zip\7z.exe` if you installed 7-Zip.


#### Ubuntu

    sudo apt-get install unrar p7zip


#### OSX

use [Homebrew](http://brew.sh/)

    brew install p7zip
    brew install unrar


Plex Client Support
-------------------

**working**: OpenPHT, PMP, Plex Web, Android, iOS


Channel Preferences
-------------------

 * **Comics Path**: path to the root directory of where comic archives are stored.
 * **Unrar Executable Path**: path to `unrar` binary. leave blank if `unrar` is in `$PATH`.
 * **7-Zip Executable Path**: path to `7z` binary. leave blank if `7z` is in `$PATH`.
 * **Items per page**: `default: 50` number of directories/comics to show per page.
 * **Number of pages to include before resume page**: `default: 5` when going to the resume option on a comic, the channel will start the list at the last viewed page. This is the number of pages prior to that page to include so you can get a recap.
 * **Enable channel updater**: `default: enabled` disable this if you don't want the channel to check for updates.
 * **Prevent client image caching**: `default: disabled` In order to keep track of your position in a comic, the channel runs code when it serves a page to the client. If the client holds a cached copy it won't make a request to the server and we can't track what page you are on.
   * Enable this option to get the client to download a new copy of the page every time it's viewed.
   * If you don't have any issues with the resume features, you can leave this disabled to save bandwidth.
