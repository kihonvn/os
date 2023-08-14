# Unix File System

## File metadata

- Owner id
- Protection bits
- Address: on the device the file belongs to
- Size
- Last modified time
- Total links: the total number of its symbolic links
- Directory bit: indicate whether the file is a directory
- Special bit: indicate whether the file is special
- Large bit: indicate whether the file is large or small

## File types

- Directory
- Special
- Ordinary (regular)

### Directories

In the Unix file system, a file whose name starts with a dot (`.`) is a hidden file.

A directory is a file used to group other files. 

Unix file system, whose structure is a rooted tree, uses a directory (`/`) to be its root, and all files in the file system are its leaves. 

Every directory contains at least two `.` and `..` files pointing to itself and its parent, respectively (except the root directory that `..` points to itself). Since their purpose is to simplify the navigation in the file system, Unix doesn't consider these two as directory children. It means a directory that only contains `.` and `..` is an empty directory.

Each user in the system has a "home" directory, often located at `/home/username` path, and it is the default path for the user login session.

### Special files

#### I/O device files

Unix represents an I/O device as a file and places it in `/dev` directory. However, we must mount it to a particular directory in the rooted tree.

### Ordinary files



## Files

### `/etc/fstab` - (file system table) mounted file systems list at boot time

```sh
# /etc/fstab: static file system information.
#
# Use 'blkid' to print the universally unique identifier for a
# device; this may be used with UUID= as a more robust way to name devices
# that works even if disks are added and removed. See fstab(5).
#
# <file system> <mount point>   <type>  <options>       <dump>  <pass>
# / was on /dev/ubuntu-vg/ubuntu-lv during curtin installation
/dev/disk/by-id/dm-uuid-LVM-ZqXM1Ik6UWHguiRwZ1ZT5ACfKWSDjwXLiO7NnT8DJRkml0b1nCzqmGYr23Y1Vbv1 / ext4 defaults 0 1
# /boot was on /dev/sda2 during curtin installation
/dev/disk/by-uuid/ad83badc-ca4b-4be1-9a55-99353eb8cf8b /boot ext4 defaults 0 1
```

### `/proc/self/mountinfo` - mounted file systems list

```sh
24 30 0:22 / /sys rw,nosuid,nodev,noexec,relatime shared:7 - sysfs sysfs rw
25 30 0:5 / /proc rw,nosuid,nodev,noexec,relatime shared:14 - proc proc rw
26 30 0:6 / /dev rw,nosuid,noexec,relatime shared:2 - devtmpfs udev rw,size=1960808k,nr_inodes=490202,mode=755
27 26 0:23 / /dev/pts rw,nosuid,noexec,relatime shared:3 - devpts devpts rw,gid=5,mode=620,ptmxmode=000
28 30 0:24 / /run rw,nosuid,nodev,noexec,relatime shared:5 - tmpfs tmpfs rw,size=401388k,mode=755
30 1 253:0 / / rw,relatime shared:1 - ext4 /dev/mapper/ubuntu--vg-ubuntu--lv rw
31 24 0:7 / /sys/kernel/security rw,nosuid,nodev,noexec,relatime shared:8 - securityfs securityfs rw
32 26 0:26 / /dev/shm rw,nosuid,nodev shared:4 - tmpfs tmpfs rw
33 28 0:27 / /run/lock rw,nosuid,nodev,noexec,relatime shared:6 - tmpfs tmpfs rw,size=5120k
34 24 0:28 / /sys/fs/cgroup ro,nosuid,nodev,noexec shared:9 - tmpfs tmpfs ro,mode=755
35 34 0:29 / /sys/fs/cgroup/unified rw,nosuid,nodev,noexec,relatime shared:10 - cgroup2 cgroup2 rw,nsdelegate
36 34 0:30 / /sys/fs/cgroup/systemd rw,nosuid,nodev,noexec,relatime shared:11 - cgroup cgroup rw,xattr,name=systemd
37 24 0:31 / /sys/fs/pstore rw,nosuid,nodev,noexec,relatime shared:12 - pstore pstore rw
38 24 0:32 / /sys/fs/bpf rw,nosuid,nodev,noexec,relatime shared:13 - bpf none rw,mode=700
39 34 0:33 / /sys/fs/cgroup/cpu,cpuacct rw,nosuid,nodev,noexec,relatime shared:15 - cgroup cgroup rw,cpu,cpuacct
40 34 0:34 / /sys/fs/cgroup/hugetlb rw,nosuid,nodev,noexec,relatime shared:16 - cgroup cgroup rw,hugetlb
41 34 0:35 / /sys/fs/cgroup/devices rw,nosuid,nodev,noexec,relatime shared:17 - cgroup cgroup rw,devices
42 34 0:36 / /sys/fs/cgroup/pids rw,nosuid,nodev,noexec,relatime shared:18 - cgroup cgroup rw,pids
43 34 0:37 / /sys/fs/cgroup/perf_event rw,nosuid,nodev,noexec,relatime shared:19 - cgroup cgroup rw,perf_event
44 34 0:38 / /sys/fs/cgroup/net_cls,net_prio rw,nosuid,nodev,noexec,relatime shared:20 - cgroup cgroup rw,net_cls,net_prio
45 34 0:39 / /sys/fs/cgroup/memory rw,nosuid,nodev,noexec,relatime shared:21 - cgroup cgroup rw,memory
46 34 0:40 / /sys/fs/cgroup/blkio rw,nosuid,nodev,noexec,relatime shared:22 - cgroup cgroup rw,blkio
47 34 0:41 / /sys/fs/cgroup/freezer rw,nosuid,nodev,noexec,relatime shared:23 - cgroup cgroup rw,freezer
48 34 0:42 / /sys/fs/cgroup/cpuset rw,nosuid,nodev,noexec,relatime shared:24 - cgroup cgroup rw,cpuset
49 34 0:43 / /sys/fs/cgroup/rdma rw,nosuid,nodev,noexec,relatime shared:25 - cgroup cgroup rw,rdma
50 25 0:44 / /proc/sys/fs/binfmt_misc rw,relatime shared:26 - autofs systemd-1 rw,fd=28,pgrp=1,timeout=0,minproto=5,maxproto=5,direct,pipe_ino=15029
51 26 0:45 / /dev/hugepages rw,relatime shared:27 - hugetlbfs hugetlbfs rw,pagesize=2M
52 26 0:20 / /dev/mqueue rw,nosuid,nodev,noexec,relatime shared:28 - mqueue mqueue rw
53 24 0:8 / /sys/kernel/debug rw,nosuid,nodev,noexec,relatime shared:29 - debugfs debugfs rw
54 24 0:12 / /sys/kernel/tracing rw,nosuid,nodev,noexec,relatime shared:30 - tracefs tracefs rw
55 24 0:46 / /sys/fs/fuse/connections rw,nosuid,nodev,noexec,relatime shared:31 - fusectl fusectl rw
56 24 0:21 / /sys/kernel/config rw,nosuid,nodev,noexec,relatime shared:32 - configfs configfs rw
325 50 0:47 / /proc/sys/fs/binfmt_misc rw,nosuid,nodev,noexec,relatime shared:67 - binfmt_misc binfmt_misc rw
124 30 7:0 / /snap/core20/1974 ro,nodev,relatime shared:69 - squashfs /dev/loop0 ro
127 30 7:1 / /snap/lxd/24061 ro,nodev,relatime shared:71 - squashfs /dev/loop1 ro
130 30 8:2 / /boot rw,relatime shared:73 - ext4 /dev/sda2 rw
133 30 7:2 / /snap/snapd/19457 ro,nodev,relatime shared:75 - squashfs /dev/loop2 ro
761 28 0:50 / /run/user/1000 rw,nosuid,nodev,relatime shared:433 - tmpfs tmpfs rw,size=401384k,mode=700,uid=1000,gid=1000
```