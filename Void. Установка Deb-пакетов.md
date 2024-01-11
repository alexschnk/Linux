#инструкция #софт #технологии #linux #void 
##### Клонирование репозитория
```
git clone https://github.com/xdeb-org/xdeb.git
```
##### Дать разрешение на исполнение
```
sudo chmod +x xdeb
```
##### Конвертация Deb в Xbps
```
./xdeb -Sde obsidian.deb
```
##### Переход в директорию с пакетом
```
cd binpkgs
```
##### Установка (копировать все до х86_64)
```
sudo xbps-install -R . obdidian
```