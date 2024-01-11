#linux #arch #fedora #инструкция #технологии 

```
sudo nano /etc/sysctl.d/99-sysctl.conf

vm.vfs_cache_pressure=25
vm.dirty_background_ratio=5
vm.dirty_ratio=50
vm.dirty_bytes=0
vm.dirty_background_bytes=0
vm.page-cluster=0
vm.swappiness=100
net.ipv4.tcp_fastopen=3
net.ipv4.tcp_congestion_control=bbr
net.core.default_qdisc=cake
net.ipv4.tcp_window_scaling=1  
net.ipv4.tcp_timestamps=1  
net.ipv4.tcp_sack=1  
kernel.kptr_restrict=2
kernel.kexec_load_disabled=1

sysctl -a
```

# Производительность
>vm.vfs_cache_pressure=25

>vm.dirty_background_ratio=5

>vm.dirty_ratio=20

>vm.dirty_bytes=0

>vm.dirty_background_bytes=0

>vm.page-cluster=0

>vm.swappiness=180

>net.ipv4.tcp_fastopen=3

>net.ipv4.tcp_congestion_control=bbr

>net.core.default_qdisc=cake

>net.ipv4.tcp_window_scaling=1  

>net.ipv4.tcp_timestamps=1  

>net.ipv4.tcp_sack=1  

---
# Безопасность

>kernel.kptr_restrict=2

>kernel.kexec_load_disabled=1
