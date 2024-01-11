#инструкция #производительность #технологии #linux 
```
sudo nano /etc/modules-load.d/zram.conf
zram

sudo nano /etc/modprobe.d/zram.conf
options zram num_devices=4

sudo nano /etc/udev/rules.d/99-zram.rules
ACTION=="add", KERNEL=="zram[0-3]", ATTR{comp_algorithm}="zstd", ATTR{disksize}="1024M", RUN="/usr/bin/mkswap -U clear /dev/%k", TAG+="systemd"

sudo nano /etc/fstab
/dev/zram0 none swap defaults 0 0
/dev/zram1 none swap defaults 0 0
/dev/zram2 none swap defaults 0 0
/dev/zram3 none swap defaults 0 0

reboot
```