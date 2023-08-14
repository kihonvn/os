# `snap` - tool to interact with snaps

A snap is a Linux app package.

## `snap list [--all]` -  list installed snaps

- `--all`: show all revisions.

```sh
$ snap list --all
core20  20230207       1828   latest/stable  canonical✓  base,disabled
core20  20230622       1974   latest/stable  canonical✓  base
lxd     4.0.9-a29c6f1  24061  4.0/stable/…   canonical✓  -
snapd   2.58.2         18357  latest/stable  canonical✓  snapd,disabled
snapd   2.59.5         19457  latest/stable  canonical✓  snapd
```

## `sudo snap remove [--revision] [--purge] snap_name` - remove snaps

- `--revision`: remove the given revision only
- `--purge`: without saving a snapshot

```sh
$ sudo snap remove --revision 1828 --purge core20
core20 (revision 1828) removed
```

```sh
$ sudo snap remove --revision 18357 --purge snapd
snapd (revision 18357) removed
```

## `snap changes` -  list recent changes

```sh
$ snap changes
ID   Status  Spawn               Ready               Summary
4    Done    today at 05:01 UTC  today at 05:01 UTC  Remove "core20" snap
5    Done    today at 05:03 UTC  today at 05:04 UTC  Remove "snapd" snap
```

## `sudo snap install snap_name` - install snaps

## `sudo snap disable snap_name` - disable a snap

```sh
$ sudo snap disable lxd
lxd disabled
```

## `sudo snap enable snap_name` - enable a snap

## `snap info snap_name` - show detailed information about snaps

```sh
$ snap info core20
name:      core20
summary:   Runtime environment based on Ubuntu 20.04
publisher: Canonical✓
store-url: https://snapcraft.io/core20
contact:   https://github.com/snapcore/core20/issues
license:   unset
description: |
  The base snap based on the Ubuntu 20.04 release.
type:         base
snap-id:      DLqre5XGLbDqg9jPtiAhRRjDuPVa5X1q
tracking:     latest/stable
refresh-date: 11 days ago, at 02:24 UTC
channels:
  latest/stable:    20230622 2023-07-05 (1974) 66MB -
  latest/candidate: 20230801 2023-08-10 (2015) 66MB -
  latest/beta:      20230801 2023-08-02 (2015) 66MB -
  latest/edge:      20230803 2023-08-03 (2027) 66MB -
installed:          20230622            (1974) 66MB base
```

## `sudo snap stop [--disable] snap_name` - stop a snap and its services

- `--disable`: disable the given snap also

## `sudo snap start snap_name` - start a snap and its services