# How the does this computer boot?

## 0. Turn on hardware

Don't know anything about that. Just happens when you press the on button.

## 1. Firmware

That gets interesting. Firmware is code that is hard-coded into the hardware.
There's 2 main ones: the BIOS (basic input/output system) and UEFI (universal
extensible firmware interface).

This computer uses **UEFI**.

I know this because the folder `/sys/firmware/efi` exists (ref 1)

All the firmware does is load a boot loader. How exciting?

## 2. Boot loader

The boot loader will load the kernel.

I am using `systemd` as a boot loader. It is all over the `/boot` folder:

    /boot $ tree

    /boot
    ├── EFI
    │   ├── BOOT
    │   │   └── BOOTX64.EFI
    │   └── systemd
    │       └── systemd-bootx64.efi
    ├── initramfs-linux-fallback.img
    ├── initramfs-linux.img
    ├── initramfs-linux-lts-fallback.img
    ├── initramfs-linux-lts.img
    ├── loader
    │   ├── entries
    │   │   └── arch.conf
    │   └── loader.conf
    ├── vmlinuz-linux
    └── vmlinuz-linux-lts

    5 directories, 10 files

## 3. The kernel

The kernel is the core of the operating system. It runs on a low level (which is
called the *kernel space*). It's between the hardware and the program who use to
hardware to run.

## 4. `initramfs`

The kernel will load the `initframfs` (initial RAM file system). This will be
the initial root file system.

# References

1. https://bbs.archlinux.org/viewtopic.php?pid=1528357#p1528357

## Extras

- https://wiki.archlinux.org/index.php/Arch\_boot\_process
