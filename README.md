# arch-setup

## usage example

```bash
curl -LO https://github.com/kohei-noda-qcrg/arch-setup/00-before-chroot
DISK=/dev/sda ./00-before-chroot

# chroot
curl -LO https://github.com/kohei-noda-qcrg/arch-setup/01-create-rootfs-and-bootloader
./01-create-rootfs-and-bootloader
```
