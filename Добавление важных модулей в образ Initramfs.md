#инструкция #технологии #arch #linux 
```
sudo nano /etc/mkinitcpio.conf

MODULES=(crc32c-intel libcrc32c zlib_deflate btrfs) 

HOOKS=(base udev autodetect modconf kms keyboard keymap block filesystems fsck)

sudo mkinitcpio -P
sudo grub-mkconfig -o /boot/grub/grub.cfg
```