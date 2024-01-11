#инструкция #технологии #linux #arch #fedora 
- Ускорение SSD

```
rw,lazytime,compress=zstd,ssd,space_cache=v2, max_inline=256,commit=600,subvol
```
- Кеш програм в ОЗУ

```
tmpfs    /путь    tmpfs    defaults,noatime,mode=1777    0 0

/tmp                                                     
/var/tmp

/var/log

/home/arch (имя пользователя)/.cache                       

/home/arch (имя пользователя)/Загрузки                     

/var/cache/pacman/pkg                 

/home/arch/.local/share/TelegramDesktop/tdata/user_data

/home/arch (имя пользователя)/.var/app/org.kde.kdenlive/cache                                                
/home/arch (имя пользователя)/.var/app/org.telegram.desktop/data/TelegramDesktop/tdata/user_data        
        
/home/arch (имя пользователя)/.var/app/org.telegram.desktop/data/TelegramDesktop/tdata/temp_data

/home/arch (имя пользователя)/.var/app/org.mozilla.firefox/cache
```