# `fdisk` - manipulate disk partition table

`fdisk` is a program for creating and manipulating partition tables.

A device name is usually `/dev/sda`, and its partition names would be its name added the partition indexes, such as `/dev/sda0` or `/dev/sda1`.

Supported partition tables:
- GPT (GUID Partition Table)
- MBR (Master Boot Record)
- Sun
- SGI
- BSD (Berkerley Software Distribution)

## `sudo fdisk -l [device_name]` - list partition tables of the given device

If we don't specify a device name, `fdisk` would use items in `/proc/partitions` file if the file exists.

```sh
$ sudo fdisk -l /dev/sda
Disk /dev/sda: 5 GiB, 5368709120 bytes, 10485760 sectors
Disk model: VBOX HARDDISK   
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: gpt
Disk identifier: CD1CEC96-ABAB-4683-963B-678FF1C7E19B

Device       Start      End Sectors  Size Type
/dev/sda1     2048     4095    2048    1M BIOS boot
/dev/sda2     4096  3674111 3670016  1.8G Linux filesystem
/dev/sda3  3674112 10483711 6809600  3.3G Linux filesystem
```

## `sudo fdisk device_name` - manipulate partitions of a device

```sh
$ sudo fdisk /dev/sdb
Changes will remain in memory only, until you decide to write them.
Be careful before using the write command.

Device does not contain a recognized partition table.
Created a new DOS disklabel with disk identifier 0x3cb86616.

Command (m for help): g
Created a new GPT disklabel (GUID: C5BDBE77-3FA8-8541-8F55-68BC26CFF6BC).

Command (m for help): n
Partition number (1-128, default 1): 
First sector (2048-2097118, default 2048): 
Last sector, +/-sectors or +/-size{K,M,G,T,P} (2048-2097118, default 2097118): +100M

Created a new partition 1 of type 'Linux filesystem' and of size 100 MiB.

Command (m for help): w
The partition table has been altered.
Calling ioctl() to re-read partition table.
Syncing disks.
```

- `g` command: create a new empty GPT partition table
- `n` command: add a new partition

After adding a new partition, we need to use [`mkfs`](mkfs.md#mksf--t-filesystem_type-device_name---make-a-file-system-for-a-particular-device) command to create a file system for it.