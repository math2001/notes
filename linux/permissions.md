# File permissions

    owner:group:others

    drwxr-xr-x 2 math2001 math2001 4.0K Nov 25 09:30 encryption/
    drwxr-xr-x 2 math2001 math2001 4.0K Nov 17 22:19 hardware/
    drwxr-xr-x 3 math2001 math2001 4.0K Nov 25 10:11 linux/
    -rw-r--r-- 1 math2001 math2001  383 Nov 24 07:50 git.md

- 4: read
- 2: write
- 1: execute

The execute permission bit on a folder allows users to cd into that directory.

## Default permissions

It's usually a good idea to have these permissions:

    files:   0644 (rw-r--r--)
    folders: 0755 (rwxr-xr-x)

## Examples

    0644 => rw-r--r--
    0777 => rwxrwxrwx

