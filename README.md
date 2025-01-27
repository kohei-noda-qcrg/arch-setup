# arch-setup

## setup example

```bash
# install git
pacman-key --init && pacman-key --populate archlinux && pamcan -Sy git
git clone https://github.com/kohei-noda-qcrg/arch-setup
pushd arch-setup

# initialize disk, copy arch-setup to the new rootfs and chroot to the new rootfs
./00-disk-init-and-chroot --initialize /dev/sda # Erase all data on /dev/sda and create BOOT and ROOT partitions
# or ./00-disk-init-and-chroot --efi /dev/nvme0n1p1 --root /dev/nvme0n1p2  # if you already have BOOT and ROOT partitions

# [optional] if you need to multi-boot, you need to mount the existing EFI partition to arbitrary directory
# grub-mkconfig in 01-setup-rootfs-and-bootloader will find the existing EFI partition and add the boot entry
# e.g. /dev/nvme0n1p1 is the existing EFI partition
# mkdir -p /tmp/efi
# mount /dev/nvme0n1p1 /tmp/efi

# setup rootfs and bootloader
/arch-setup/01-setup-rootfs-and-bootloader --username archuser
exit
reboot

# setup user development and desktop environment
/arch-setup/02-setup-dev-and-desktop-env
```
