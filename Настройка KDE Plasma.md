#linux #окружения #инструкция #plasma
##### Отключение Baloo в Plasma
Baloo - это файловый индекстор в Plasma, аналог Tracker в GNOME, который однако ОЧЕНЬ прожорливый, и ест довольно много ресурсов процессора и памяти, вдобавок фоном нагружая ваш диск, в отличии от того же Tracker 3.
```
systemctl --user mask kde-baloo.service           
systemctl --user mask plasma-baloorunner.service
```

##### Отключение отладочной информации в Plasma 5
```
kdebugdialog5
```