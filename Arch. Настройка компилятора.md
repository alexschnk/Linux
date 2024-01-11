#инструкция #производительность #технологии #linux #arch 
```
sudo nano /etc/makepkg.conf 
```
##### Нативная компиляция с флагами оптимизации
```
CFLAGS="-march=native -mtune=native -O3 -pipe -fno-plt -fexceptions \
      -Wp,-D_FORTIFY_SOURCE=2 -Wformat -Werror=format-security \
      -fstack-clash-protection -fcf-protection"
CXXFLAGS="$CFLAGS -Wp,-D_GLIBCXX_ASSERTIONS"
RUSTFLAGS="-C opt-level=3"
MAKEFLAGS="-j$(nproc) -l$(nproc)"
OPTIONS=(strip docs !libtool !staticlibs emptydirs zipman purge !debug lto)
```
##### Перенос кеша компиляции в ОЗУ
```
BUILDDIR=/tmp/makepkg
```