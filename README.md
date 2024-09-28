# Usage

Get the bedrock server for linux from a link on this page:

  https://www.minecraft.net/en-us/download/server/bedrock

* Place the current server zip file under `upstream/`.  
* Write the corresponding version string into `local/version`.  
* Execute `launch` as user `nobody`.  

Any older server instances will be stopped.  The new server will be installed
if necessary and then launched.  Save files should be preserved.


# Files

`.gitignore` - Specify which files should be tracked or untracked.  Track this.

`upstream/` - The upstream repo to which this repo adds slight modification.  The term "repo" is used very loosely; these are one-off releases to be unpacked and run in place.  Do not track anything under this directory.

`active` - This is where code from upstream gets unpacked, then files from `local/` get copied in, and then the code is executed here to start the server.  Do not track.

`local/` - Files contributed to this repo, including configuration files to copied to the current server release under `unpacked/`.  Track everything under this directory.


# To Do

* Clean up after unzip failure and such.  Don't make it look like a new version exists.

* Automatic updates.  It would be cool to check for the latest version, download it, declare that to be the current version, and then proceed as usual.  This should probably be a separate script to be run on a cron job.

* Initify.  This launch script is probably doing the job of an init script.  If it proves worthwhile, modify it into an actual init script.  The automatic update script should refer to the init script to restart the service only if it is already running.

* Package.  This might make a nice deb file.  Frequent updates should not be necessary (not counting corrections to slipshod code) if automatic updates of upstream material can be scripted.

* Ansible.  I should have an ansible role to deploy this.

* Dedicated user.  `nobody` is better than `root`, but a special `minecraft` or `minecraft-server` user would be better.
