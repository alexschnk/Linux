#безопасность #производительность #инструкция #технологии #arch #linux 
```
sudo pacman -S linux-zen linux-zen-headers linux-hardened linux-hardened-headers linux-lts linux-lts-headers

sudo mkinitcpio -P

sudo grub-mkconfig -o /boot/grub/grub.cfg

reboot
```