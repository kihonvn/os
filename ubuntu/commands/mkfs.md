# `mkfs` - make a file system

## `mksf -t filesystem_type device_name` - Make a file system for a particular device

```sh
$ sudo mkfs -t ext4 /dev/sdb1
mke2fs 1.45.5 (07-Jan-2020)
Creating filesystem with 25600 4k blocks and 25600 inodes

Allocating group tables: done                            
Writing inode tables: done                            
Creating journal (1024 blocks): done
Writing superblocks and filesystem accounting information: done
```

The next step is to [`mount`](mount.md#mount--t-filesystem_type-device_name-target_directory---mount-a-file-system-to-a-particular-directory) the device to our file tree.