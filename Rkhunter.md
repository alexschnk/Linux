#безопасность #инструкция #технологии #софт #linux 
##### Проверка обновлений
```
sudo rkhunter --update
```
##### Проверка свежести версии
```
sudo rkhunter --versioncheck
```
##### Проверка корректности конфигурации
```
sudo rkhunter --config-check
```
##### Запуск аудита
```
sudo rkhuner -c -sk
```
##### Отчет по результатам
```
sudo nano /var/log/rkhunter.log
```
##### Конфигурационный файл
```
sudo nano /etc/rkhunter.conf
```
---
##### Проблема WEB_CMD
```
sudo nano /etc/rkhunter.conf
WEB_CMD=curl
```
##### Проблема Mirrors
```
sudo nano /etc/rkhunter.conf
MIRRORS_MODE=0
```
##### Обновить базу целостности файлов
```
sudo rkhunter --propupd
```