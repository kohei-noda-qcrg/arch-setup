# arch-setup

## setup example

```bash
curl -LO https://github.com/kohei-noda-qcrg/arch-setup/raw/main/00-before-chroot
DISK=/dev/sda ./00-before-chroot

# chroot
curl -LO https://github.com/kohei-noda-qcrg/arch-setup/raw/main/01-create-rootfs-and-bootloader
./01-create-rootfs-and-bootloader
exit
reboot

# setup user development and desktop environment
curl -LO https://github.com/kohei-noda-qcrg/arch-setup/raw/main/02-setup-dev-and-desktop-env
./02-setup-dev-and-desktop-env
```
