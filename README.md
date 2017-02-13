# timertab

An easy way to manage your Systemd Timers.

```
Usage: ./timertab [-u|--user] COMMAND [ARGUMENT...]
Only use one command at a time

  -u, --user         Deal only with user timers (not run as root)

COMMANDS:
  help               Display this help dialog
  list               List the current timers
  new [NAME...]      Create a new timer
  enable [NAME...]   Enable timer
  start [NAME...]    Start timer
  stop [NAME...]     Stop timer
  disable [NAME...]  Disable timer
  remove [NAME...]   Remove (delete) timer and/or associated service files
  modify [NAME...]   Opens the .timer file for editing in vi
  convert            Convert a cron job into a Systemd timer
```

## Usage examples

List all of the user's timers:

    $ ./timertab -u list

Create a user timer named "myscript":
```
$ ./timertab -u new myscript.timer
```
Note: The .timer extension is optional

Enable a timer:

`$ sudo ./timertab enable mytimer`
