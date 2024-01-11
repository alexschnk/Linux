#безопасность #шифрование #luks #технологии #инструкция #linux 

1) **Создаём пустой файл для будущего контейнера (например 200Мб):**

```
fallocate -l 200M /home/arch/Загрузки/file_name  
```
2) **Создаём в этом файле криптоконтейнер:**
```
sudo cryptsetup luksFormat /home/arch/Загрузки/file_name
```  
3) **Открываем контейнер:**
```
sudo cryptsetup luksOpen /home/arch/Загрузки/file_name data 
```  
4) **Создаём на нём файловую систему:**
```
sudo mkfs.ext4 /dev/mapper/data
``` 
5) **Монтируем расшифрованный контейнер:**
```
sudo mount /dev/mapper/data /mnt/
```
6) **Записываем необходимые файлы в /mnt, после чего его можно отмонтировать:**
```
sudo umount /mnt
```  
7) **Извлекаем контейнер:**
```
sudo cryptsetup luksClose /dev/mapper/data
```