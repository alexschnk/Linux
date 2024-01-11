#безопасность #инструкция #технологии #linux 
##### Дать systemd-resolved приявлегия основного резолвера

>Важно: Начиная с Fedora 33, systemd-resolved уже используется в качестве основного системного DNS-резолвера.

##### Удалить существующую символическую ссылку, указывающую на Network Manager:
```
sudo rm -f /etc/resolv.conf
```
##### Установить systemd-resolved основным резолвером:
```
sudo ln -sf /run/systemd/resolve/stub-resolv.conf /etc/resolv.conf
```
>Изменения вступят в силу немедленно

##### Открыть файл конфигурации
```
sudo nano /etc/systemd/resolved.conf:

sudoedit /etc/systemd/resolved.conf
```
##### Внести следующие правки:
```
[Resolve]
DNS=1.1.1.1 1.0.0.1 2606:4700:4700::1111 2606:4700:4700::1001
FallbackDNS=8.8.8.8 8.8.4.4 2001:4860:4860::8888 2001:4860:4860::8844
#Domains=
#LLMNR=yes
MulticastDNS=yes
DNSSEC=allow-downgrade
DNSOverTLS=opportunistic
Cache=yes
DNSStubListener=yes
ReadEtcHosts=yes
```
>Здесь используются серверы CloudFlare с поддержкой DNS-over-TLS

##### Сохранить изменения в файле и перезапустить systemd-resolved:
```
sudo systemctl restart systemd-resolved.service
```
>Теперь в информации об используемых DNS должна отображаться информация об использовании этой технологии