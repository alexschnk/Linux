#инструкция #технологии #linux #фс
# Опции монтирования
>**rw**: чтение / запись

>**ro**: чтение

>**noatime**: отключить обновление кеша инод

>**lazytime**: хранить кеш инод в ОЗУ

>**max_inline=256**:

>**space_cache=v2**:

>**compress=zstd**: прозрачное сжатие алгоритмом zstd; степень сжатия по умолчанию 3

>**ssd**: ФС оптимизируется для SSD

>**commit=300**: кеширование изменений в ФС в ОЗУ; сброс изменений в ФС на диск раз в 300 сек

>**nodatacow**: отключить копирование при записи

>**subvol**: наименование подтома

___

# Подтома

#### Типы и примеры
- **@**: монтируется в `/`; корневой подтом

- **@home**: монтируется в `/home`; домашний подтом

- **@machine**: монтируется в `/var/lib/libvirt/images`; виртуальные машины libvirt

#### Создание и монтирование
```
btrfs su cr /mnt/@

mount -o rw,lazytime,compress=zstd,max_inline=256,space_cache=v2,ssd,commit=300,subvol=@ /dev/sdX /mnt
```