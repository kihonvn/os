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