`.gitignore` - Specify which files should be tracked or untracked.  Track this.

`upstream/` - The upstream repo to which this repo adds slight modification.  The term "repo" is used very loosely; these are one-off releases to be unpacked and run in place.  Do not track anything under this directory.

`active` - This is where code from upstream gets unpacked, then files from `local/` get copied in, and then the code is executed here to start the server.  Do not track.

`local/` - Files contributed to this repo, including configuration files to copied to the current server release under `unpacked/`.  Track everything under this directory.
