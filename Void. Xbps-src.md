#инструкция #софт #технологии #пакетник #void 
# Клонирование репозитория
```
git clone https://github.com/void-linux/void-packages.git
```
# Сборка Bootstrap-пакетов
```
cd void-packages
./xbps-src binary-bootstrap
```
# Разрешение на сборку ограниченых пакетов
```
echo XBPS_ALLOW_RESTRICTED=yes >> etc/conf
```
# Редактирование файла template
```
nano scrpkgs/timeshift/template
```
# Сборка пакета
```
./xbps-src pkg timeshift
```
# Установка пакета
```
sudo xbps-install --repository hostdir/binpkgs timeshift
```