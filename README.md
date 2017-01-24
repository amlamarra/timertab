# timertab

An easy way to manage your Systemd Timers.

```
Usage: ./timertab [-u|--user] COMMAND [ARGUMENT...]
Only use one option at a time (not including -u)

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
```
