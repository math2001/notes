# Hardware

## Get basic system info

    $ uname -a

## Bunch of info about hardware

    $ sudo lshw
    $ sudo lshw -short
    $ sudo lshw -html > index.html

## Get CPU details

    $ lscpu

## Block devices

    $ lsblk
    $ lsblk -a

Block devices are storage devices (hard disks, USB sticks, etc...)

## USB ports

    $ lsusb
    $ sudo lsusb -v


Shows details about USB ports (version, etc)

## PCI devices

    $ lspci
    $ sudo lspci -v


> See filesystem.md for information about the file system

## References

1. <https://www.tecmint.com/commands-to-collect-system-and-hardware-information-in-linux/>
