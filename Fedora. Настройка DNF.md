#инструкция #пакетник #производительность #технологии #fedora #linux 
```
sudo nano /etc/dnf/dnf.conf
```
##### Включение delta-rpm
```
deltarpm=true
```
##### Ускорение загрузки пакетов через проверку Ping
```
fastestmirror=1
```
##### Отключение телеметрии
```
countme=False
```

##### Очистка кеша fastestmirror
```
sudo rm -f /var/cache/dnf/fastestmirror.cache
```