#безопасность #инструкция #технологии #linux 

```
sudo pacman -S net-tools

sudo ifconfig
```
Обратите внимание на строку ether - это и есть мак-адрес сетевого  
устройства

>**wifi.scan-rand-mac-address=yes** - генерировать случайные MAC-адреса во время сканирования wifi
 
>**wifi.cloned-mac-address=random** - генерировать случайный MAC-адрес wifi при каждом новом подключении
 
>**ethernet.cloned-mac-address=random** - генерировать случайный MAC-адрес сетевой карты ethernet при каждом подключении

##### Вариант 1
Генерирование уникального псевдослучайного MAC адреса для каждого соединения при загрузке системы (параметр stable). Это избавит от проблем с переподключением к публичным хот-спотам и небходимости повторно проходить аутентификацию в captive-порталах

```
sudo nano /etc/NetworkManager/conf.d/00-macrandomize-stable.conf:

[device]
wifi.scan-rand-mac-address=yes

[connection]
wifi.cloned-mac-address=stable
ethernet.cloned-mac-address=stable
connection.stable-id=${CONNECTION}/${BOOT}
```

##### Вариант 2
Генерирование уникального псевдослучайного MAC адреса для каждого соединения при каждом переподключении (параметр random). Наиболее безопасно, но может вызывать описанные выше проблемы.

```
sudo nano /etc/NetworkManager/conf.d/00-macrandomize-random.conf

[device]
wifi.scan-rand-mac-address=yes

[connection]
wifi.cloned-mac-address=random
ethernet.cloned-mac-address=random

sudo systemctl restart NetworkManager
```
Для отключения рандомизации и возвращения настроек по умолчанию достаточно просто удалить созданный файл и перезапустить Network Manager

##### Вариант 3
Параметры системы > Категория Сеть и связь > Соединения. В списке соединений wifi  
найти требуемое подключение и во вкладке WI-Fi найти строку клонированный MAC-адрес.  
Далее просто вводим MAC-адрес, который будет отличаться на один символ от легитимного.  
Таким образом вы сможете подключаться и работать на роутере, оставаться незамеченным и при этом не мешать людям пользоваться домашним интернетом

