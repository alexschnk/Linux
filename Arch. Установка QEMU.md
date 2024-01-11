#linux #arch #технологии #инструкция #софт
```sudo pacman -S qemu virt-manager libvirt virt-viewer dnsmasq vde2 bridge-utils openbsd-netcat nftables libguestfs dmidecode

sudo pacman -S ebtables

sudo systemctl start libvirtd

sudo systemctl enable libvirtd

sudo systemctl status libvirtd

sudo nano /etc/libvirt/libvirtd.conf
unix_sock_group = "libvirt"
unix_sock_rw_perms = "0770"

sudo usermod -a -G libvirt имя_пользователя

sudo nano /etc/group
libvirt:x:963:имя_пользователя

sudo nano /etc/libvirt/qemu.conf
user = "root" -> user = "имя_пользователя"
group = "root" -> group = "libvirt"

sudo systemctl restart libvirtd

sudo systemctl status libvirtd
```