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
  status [NAME...]   Display the status of a specific timer
  disable [NAME...]  Disable timer
  remove [NAME...]   Remove (delete) timer and/or associated service files
  modify [NAME...]   Opens the .timer file for editing in vi
  run [NAME...]      Run a transient (temporary) timer
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

5. Display the status of a timer:

   `$ ./timertab status mytimer`

6. Create a transient (temporary) timer.<br>These timer files are created in the /run/user/$UID/systemd/transient/ directory.<br>They are not "enabled" or "disabled" but will be deleted once they are stopped or there's a reboot.<br>If no name is provided, one will be automatically generated.

   `$ ./timertab -u run mytimer`

#### Known Issues

- Unable to convert user cron jobs to root level timers

  - Workaround:
  
    Do the conversion with the `--user` option, and move the files from ~/.config/systemd/user/ to /etc/systemd/system/
