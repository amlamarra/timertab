# timertab

An easy way to create, delete, and manage your Systemd Timers.

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

### Usage examples

1. List all of the user's timers:

   `$ ./timertab -u list`

2. Create a user timer named "myscript":

   `$ ./timertab -u new myscript.timer`  (Note: The .timer extension is optional)

3. Enable a timer:

   `$ sudo ./timertab enable mytimer`

4. Deleting a timer file:

   `$ sudo ./timertab remove mytimer`

### Known Issues

- Unable to convert user cron jobs to root level timers

  - Workaround:
  
    Do the conversion with the `--user` option, and move the files to /etc/systemd/system/
