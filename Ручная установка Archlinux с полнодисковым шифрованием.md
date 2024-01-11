#безопасность #инструкция #технологии #шифрование #linux #luks #arch 
# Подготовка к установке 
```
dhcpcd

ping ya.ru

nano /etc/pacman/pacman.conf
[multilib]

pacman -Syy

pacman -S reflector 
nano /etc/xdg/reflector/reflector.conf
-- sort rate
systemctl start reflector
```
# Разметка диска
```
cfdisk
```
# Монтирование разделов
```
mkfs.vfat -F32 /dev/sda1

cryptsetup luksFormat -v -y --type luks1 /dev/sda2
cryptsetup luksOpen /dev/sda2 root

mkfs.btrfs -f /dev/mapper/root
mount /dev/mapper/root /mnt

umount -R /mnt
cryptsetup close root

cryptsetup luksOpen /dev/sda2 root

mount /dev/mapper/root /mnt

btrfs su cr /mnt/@

umount -R /mnt

mount -o rw,lazytime,compress=zstd,max_inline=256,space_cache=v2,ssd,commit=300,subvol=@ /dev/mapper/root /mnt

df -h

ls /mnt

mkdir /mnt/efi
mount /dev/sda1 /mnt/efi

ls /mnt
```
# Установка базовой системы 
```
pacstrap -i /mnt base base-devel linux-zen linux-zen-headers linux-firmware dosfstools btrfs-progs intel-ucode iucode-tool archlinux-keyring bluez bluez-utils nano dhcpcd dhclient networkmanager 
```
### Установка графических драйверов

##### Графические драйвера Intel
```
mesa mesa-demos xf86-video-intel lib32-mesa vulkan-intel lib32-vulkan-intel vulkan-icd-loader lib32-vulkan-icd-loader network-manager-applet libva-intel-driver lib32-libva-intel-driver
```
##### Графические драйвера AMD
```
xf86-video-ati xf86-video-amdgpu mesa mesa-demos lib32-mesa vulkan-radeon lib32-vulkan-radeon vulkan-icd-loader lib32-vulkan-icd-loader amdvlk lib32-amdvlk network-manager-applet
```
### Установка оболочки 

##### KDE Plasma
```
xorg xorg-server xorg-xwayland plasma konsole dolphin cups sddm sddm-kcm packagekit-qt5 bluez bluez-utils plasma-wayland-session
```
##### Gnome
```
xorg xorg-server gnome cups nautilus gnome-terminal gdm 
```
# Генерация Fstab
```
genfstab -U /mnt >> /mnt/etc/fstab

cat /mnt/etc/fstab
```
# Переход в Chroot и конфигурирование системы
```
arch-chroot /mnt

ln -sf /usr/share/zoneinfo/Europe/Moscow /etc/localtime

hwclock --systohc

nano /etc/locale.gen
en_US.UTF-8 UTF-8
ru_RU.UTF-8 UTF-8

locale-gen

nano /etc/locale.conf
LANG=ru_RU.UTF-8

nano /etc/vconsole.conf
KEYMAP=ru
FONT=cyr-sun16

nano /etc/hostname
archlinux

nano /etc/hosts
127.0.0.1 localhost
::1       localhost
127.0.0.1 archlinux.localdomain archlinux

mkinitcpio -P

passwd

nano /etc/sudoers
%wheel или wheel

useradd -m -G wheel -s /bin/bash имя_юзера

passwd имя_юзера
```
# Создание файла-ключа
```
dd bs=512 count=4 if=/dev/random of=/root/crypt.key iflag=fullblock

chmod 000 /root/crypt.key 

cryptsetup -v luksAddKey /dev/sda2 /root/crypt.key
```
# Добавление важных модулей в Initramfs
```
nano /etc/mkinitcpio.conf

FILES=(/root/crypt.key)

MODULES=(crc32c-intel libcrc32c zlib_deflate btrfs) 

HOOKS=(base udev autodetect modconf kms keyboard keymap consolefont block encrypt filesystems fsck)

mkinitcpio -P
```
# Установка загрузчика
```
pacman -S grub efibootmgr os-prober mtools

blkid | grep sda2
  
nano /etc/default/grub
GRUB_ENABLE_CRYPTODISK=y
GRUB_CMDLINE_LINUX="cryptdevice=UUID=XXX:root:allow-discards root=/dev/mapper/root cryptkey=rootfs:/root/crypt.key

grub-install --target=x86_64-efi --efi-directory=/efi /dev/sda

grub-mkconfig -o /boot/grub/grub.cfg
```
# Включение всех служб
```
systemctl enable NetworkManager

systemctl enable sddm
или
systemctl enable gdm
```
# Завершение
```
mkinitcpio -P

grub-mkconfig -o /boot/grub/grub.cfg

exit

umount -R /mnt
cryptsetup close root

reboot

```