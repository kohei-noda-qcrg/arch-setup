# arch-setup

## setup example

```bash
# if you need to multi-boot, you need to mount the existing EFI partition to arbitrary directory
# grub-install in 01-setup-rootfs-and-bootloader will find the existing EFI partition and add the boot entry
# e.g. /dev/nvme0n1p1 is the existing EFI partition
# mkdir -p /tmp/efi
# mount /dev/nvme0n1p1 /tmp/efi

# initialize disk and chroot to the new rootfs
curl -LO https://github.com/kohei-noda-qcrg/arch-setup/raw/main/00-disk-init-and-chroot
./00-disk-init-and-chroot --initialize /dev/sda # Erase all data on /dev/sda and create BOOT and ROOT partitions
# or ./00-disk-init-and-chroot --efi /dev/nvme0n1p1 --root /dev/nvme0n1p2  # if you already have BOOT and ROOT partitions

# setup rootfs and bootloader
curl -LO https://github.com/kohei-noda-qcrg/arch-setup/raw/main/01-setup-rootfs-and-bootloader
./01-setup-rootfs-and-bootloader
exit
reboot

# setup user development and desktop environment
curl -LO https://github.com/kohei-noda-qcrg/arch-setup/raw/main/02-setup-dev-and-desktop-env
./02-setup-dev-and-desktop-env
```
