#безопасность #инструкция #технологии #linux 
```
sudo nano /etc/selinux/config
```
>**SELINUX=enforcing**
>включён и блокирует всё, что явно не разрешено

>**SELINUX=permissive**
>включён, но ничего не блокирует, а лишь записывает события в [системный журнал](https://russianfedora.github.io/FAQ/administration.html#journal-current)


>**SELINUX=disabled**
>полностью отключен
