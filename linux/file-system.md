# File System

## Mounting

Mounting "binds" some device's file structure on a regular file tree. Any
manipulation of the file tree will be replicated (maybe with a delay, ie flush)
onto the real device.

For example, to mount a USB key, first find it in `/dev/sd*` where `*` is
usually a letter (a, b, c, ...). Let's say in this case it's `d`

Then, you select the partition (// is it a partition?), so that'll be
`/dev/sdd1` (the USB will probably only have one partition)

```
$ sudo mkdir /mnt/myusbkey
$ sudo mount /dev/sdd1 /mnt/myusbkey
$ ls /mnt/myusbkey
[myusbkey's content!]
```

The folder to mount to (mount point?) must already exist before mounting.

To unmount (unbind the virtual file structure with the actual device):

```
$ umount /mnt/myusbkey
$ # or specify the device, which I guess unmounts every mounting point
$ umount /dev/sdd1
```

## Get info about devices

A little golden nugget:

```
$ sudo blkid
/dev/sdb2: UUID="7be56b9c-67ea-4aae-9a9f-557d3f9cadb4" TYPE="ext4" PARTUUID="558251c8-02"
/dev/loop0: TYPE="squashfs"
/dev/loop1: TYPE="squashfs"
/dev/loop2: TYPE="squashfs"
/dev/loop3: TYPE="squashfs"
/dev/loop4: TYPE="squashfs"
/dev/loop5: TYPE="squashfs"
/dev/loop6: TYPE="squashfs"
/dev/loop7: TYPE="squashfs"
/dev/sda1: LABEL="System Reserved" UUID="3ED87104D870BBA9" TYPE="ntfs" PARTUUID="d42ad42a-01"
/dev/sda2: UUID="CAE2564DE2563E3F" TYPE="ntfs" PARTUUID="d42ad42a-02"
/dev/sda3: UUID="3ED6158AD6154415" TYPE="ntfs" PARTUUID="d42ad42a-03"
/dev/sdb1: LABEL="Backup" UUID="D2C0176EC0175855" TYPE="ntfs" PARTUUID="558251c8-01"
/dev/sdc1: LABEL="USYD" UUID="265D-2924" TYPE="vfat" PARTUUID="42a5c5a8-01"
/dev/loop8: TYPE="squashfs"
/dev/loop9: TYPE="squashfs"
/dev/loop10: TYPE="squashfs"
/dev/loop11: TYPE="squashfs"
```

