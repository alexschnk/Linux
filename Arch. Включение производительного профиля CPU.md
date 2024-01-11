#инструкция #производительность #arch #linux 
```
pacman -S cpupower 

sudo cpupower frequency-set -g performance
 
sudo nano /etc/systemd/system/cpupower.service

[Unit]
Description=Set CPU governor to performance

[Service]
Type=oneshot
ExecStart=/usr/bin/cpupower -c all frequency-set -g performance


[Install]
WantedBy=multi-user.target

sudo systemctl enable cpupower.service

yay -S cpupower-gui

sudo systemctl disable cpupower-gui
```