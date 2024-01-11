#linux #fedora #arch #технологии #инструкция 
# Включение iwlwifi

```
lsmod | grep iwlwifi
```
Если в окно терминала будет выведена строка «iwlwifi», вы можете переходить к следующему шагу.
```
sudo nano /etc/modprobe.d/iwlwifi11n.conf
options iwlwifi 11n_disable=8
```
Если проблемы с сетью
```
sudo rm -v /etc/modprobe.d/iwlwifi11n.conf
```
# Включение tcp_bbr
```
sudo modprobe tcp_bbr

sudo nano /etc/modules-load.d/tcp-bbr.conf
tcp_bbr
```