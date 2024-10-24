# systory

`systory` is a git wrapper meant to help sysadmins with highly-fluid systems (like devboxes and personal computers).

It assumes a single system administrator.

It mainly allows you to use git as a history tracking mechanisms such as `git commit --allow-empty` so you can make log notes.

99% of the time `systory COMMAND` is a wrapper for `git -C /path/to/history COMMAND`, however:

`systory [init|sync [--sudo]|delete [--sudo]|addcommit]`:

- `init` will start the folder
- Use `sync` is like `cp`- it will copy the file into the repo, imagine:

```bash
$ ls /etc
my_config.conf
$ systory sync *
```

This will create an `~/etc/my_config.conf` in `~/system/history`

- `delete` is like `sync`.

Neither require `-r`, but do accept dirs.

- `addcommit` will add and commit the whole directory. Anything piped into it will be availabe in the commit.

`history | systory addcommit "Begin commit message here"` is a good idea.

A `packages-Qe` file, the output of `yay -Qe`, will be in the root directory.

- `go` will take you to the directory. You can then use `popd`.
