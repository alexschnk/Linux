#безопасность #инструкция #софт #технологии #linux 
# Основное
##### Каталог со всеми профилями
```
/etc/firejail
```
##### Создать симлинки на все пакеты, имеющие профили в базе
```
sudo firecfg
```
##### Удалить созданные симлинки 
```
sudo firecfg --clean
```
##### Исправление проблемы со звуком
```
firecfg --fix-sound
```
##### Каталог с действующим профилями
```
~/.config/firejail/
```
##### Генерирование профиля
```
firejail --build appname #вывод шаблона профиля для приложения на стандартный вывод

или

firejail --build=appname.profile appname #вывод шаблона в файл
```
##### Запуск в песочнице
```
firejail [название пакета]
```
##### Уничтожение созданных софтом файлов и ограничение его доступа к системе 
```
firejail --private 
```
---
# Ключи 
##### Фильтрация протоколов взаимодействия

```
--protocol= 

unix
inet
inet6
netlink
packet
bluetooth
```
---