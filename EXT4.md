#инструкция #технологии #linux #фс 
# Журналирование
##### Включение полного журналирования
```
sudo tune2fs -O has_journal /dev/sda1
```
##### Отключение полного журналирования
```
sudo tune2fs -O ^has_journal /dev/sda1
```
##### Информация о всех опциях ФС
```
sudo tune2fs -l /dev/sda1
```