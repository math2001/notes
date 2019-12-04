# File System

## Mounting

```
$ sudo mkdir /mnt/myusbkey
$ sudo mount /dev/sdd1 /mnt/myusbkey
$ ls /mnt/myusbkey
[myusbkey's content!]
```

To unmount (unbind the virtual file structure with the actual device):

```
$ umount /mnt/myusbkey
$ # or specify the device, which I guess unmounts every mounting point
$ umount /dev/sdd1
```

## Check if USB is bootable

```
$ sudo fdisk -l <device>
```

(check the boot column)

## Check where a block device is mounted

    $ df

If a device is mounted on multiple mounting points, then you can see them with

    $ df -a

Also, you probably want to alias/abbreviate `df` to `df -h`

Note that df only shows mounted devices.

## Get info about block devices

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

