#linux #arch #технологии #инструкция #пакетник
##### Ускорение загрузки пакетов
```
sudo pacman -S reflector

sudo nano /etc/xdg/reflector/reflector.conf

-- sort rate

sudo systemctl start reflector
```
##### Настройка Pacman
```
sudo nano /etc/pacman.conf
ILoveCandy
Color
VerbosePkgList
ParallelDownloads = 2
```