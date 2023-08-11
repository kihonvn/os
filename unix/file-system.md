# Unix File System

Unix file system is a rooted tree, and `/` denotes the root, a directory.

## File types

- Ordinary (regular)
- Directory
- Special

### Ordinary file

### Directory

Each directory contains at least two hidden system directories, `.` and `..` pointing to itself and its parent, respectively. Since their purpose is to simplify the navigation in the file system, we don't consider them as directory children. That means a directory that only contains `.` and `..` is an empty directory.