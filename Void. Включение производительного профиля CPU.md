#инструкция #производительность #технологии #linux #void 
# Установка Cpupower
```
sudo xbps-install cpupower
```
# Проверка профиля
```
inxi -Fxxxza | grep governor
```
# Установка профиля Performance
```
sudo cpupower frequency-set -g performance
```
# Установка профиля  Performance навсегда
```
sudo nano /etc/rc.local
cpupower frequency-set -g performance
```