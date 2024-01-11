#linux #технологии #инструкция #производительность 
# Проверка поколения процессора 

```
/lib/ld-linux-x86-64.so.2 --help | grep supported
```
---
# Репозитории CachyOS
##### Установить ключи
```
sudo pacman-key --recv-keys F3B607488DB35A47 --keyserver keyserver.ubuntu.com

sudo pacman-key --lsign-key F3B607488DB35A47

sudo pacman -U 'https://mirror.cachyos.org/repo/x86_64/cachyos/cachyos-keyring-3-1-any.pkg.tar.zst' 'https://mirror.cachyos.org/repo/x86_64/cachyos/cachyos-mirrorlist-18-1-any.pkg.tar.zst' 'https://mirror.cachyos.org/repo/x86_64/cachyos/cachyos-v3-mirrorlist-18-1-any.pkg.tar.zst' 'https://mirror.cachyos.org/repo/x86_64/cachyos/cachyos-v4-mirrorlist-6-1-any.pkg.tar.zst' 'https://mirror.cachyos.org/repo/x86_64/cachyos/pacman-6.0.2-14-x86_64.pkg.tar.zst'
```
##### Добавление репозиториев в Pacman
```
sudo nano /etc/pacman.conf

[cachyos-v3]
Include = /etc/pacman.d/cachyos-v3-mirrorlist

[cachyos-core-v3]
Include = /etc/pacman.d/cachyos-v3-mirrorlist

[cachyos-extra-v3]
Include = /etc/pacman.d/cachyos-v3-mirrorlist

[core]
Include = /etc/pacman.d/mirrorlist

[extra]
Include = /etc/pacman.d/mirrorlist
```
##### Обновление
```
sudo pacman -Syyuu
```
---
# Репозитории Alph
##### Установка ключей и зеркал
```
yay - S alhp-keyring alhp-mirrorlist
```
##### Подключение репозиториев
```
sudo nano /etc/pacman.conf

[core-x86-64-v3]
Include = /etc/pacman.d/alhp-mirrorlist

[extra-x86-64-v3]
Include = /etc/pacman.d/alhp-mirrorlist

[core]
Include = /etc/pacman.d/mirrorlist

[extra]
Include = /etc/pacman.d/mirrorlist

sudo pacman -Syyuu

reboot
```