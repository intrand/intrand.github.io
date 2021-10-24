# rsync-server

`rsync-server` is an `openssh` daemon listening for SCP connections which is useful for automated backups. The name is slightly misleading, although the same image can also be used to run an instance of `rsyncd` if you wanted.

## Design

`rsync-server` can be deployed using a pre-defined public key for the `root` user, or it can generate a password for you.

## Status

Useful! I can throw files over to another server very quickly with a `kubectl apply` followed by `rsync -a` and it'll end up where I think it should. This is especially useful if matched with `duplicity-backup`.
