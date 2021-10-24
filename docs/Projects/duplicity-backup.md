# duplicity-backup

`duplicity-backup` is a relatively simple wrapper around `duplicity` that makes it simple to have regular, automated backup jobs run for you.

## Design

Instead of setting up a cronjob to fire a script with a bunch of secrets and configuration data, I chose to use a Kubernetes CronJob to run a container that mounted a ConfigMap into it. This meant I could describe all of my backup procudure in YAML and it would work regardless of the host operating system.

`duplicity-backup` makes the assumption that `rsync` is used over `ssh` in order to keep things simple.

## Status

Useful! I keep regular off-site backups in case of fire, flood, theft, natural disaster, etc. The need is becoming and less and less over time thanks to cloud services, switching hobbies, reducing and simplifying our digital footprint, etc. Still, for the few things we do use it for, it's awesome.
