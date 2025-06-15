# Configuration

`permissions.json` should look like this:

    [
      {
        "permission": "operator",
        "xuid": "2535412538936360",
        "comment": "Aaron (SlinkyRoom5813)"
      },
      {
        "permission": "member",
        "xuid": "2535441051745407",
        "comment":"Lucy (LuciferBucifer)"
      }
    ]

Anyone not designated as `member` or `operator` can still join, technically,
but will be automatically designated as `visitor` and unable to interact with
the world.

Watch those commas.


# Updates

The launch script will download the version of the server specified.  It cannot
yet determine the latest version, so automatic updates are not yet feasible.


# To Do

* Clean up after unzip failure and such.  Don't make it look like a new version exists.

* Automatic updates.  It would be cool to check for the latest version, download it, declare that to be the current version, and then proceed as usual.  This should probably be a separate script to be run on a cron job.
