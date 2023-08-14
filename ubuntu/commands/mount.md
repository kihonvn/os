# `mount` - mount a file system into the current working file tree

## `mount -l` - list all mounted file systems

[`findmnt`](findmnt.md#findmnt---list-all-mounted-file-systems-in-a-tree-structure) prints the same result in a tree structure.

The information is in `/proc/self/mountinfo` file.

## `mount device_name target_directory` - mount a file system to a particular directory

The `target_directory` must exist. If it's not empty, the OS will hide them. However, we can get them back after [unmounting the mounted device](umount.md).

```sh
$ sudo mount /dev/sdb1 ~/backup
```