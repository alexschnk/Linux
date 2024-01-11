#инструкция #производительность #технологии #arch #linux 
##### Ядро и драйвера CPU
```
sudo pacman -S base base-devel linux-zen linux-zen-headers linux-firmware dosfstools btrfs-progs intel-ucode amd-ucode iucode-tool archlinux-keyring bluez bluez-utils nano dhcpcd dhclient networkmanager lrzip unrar unzip unace squashfs-tools android-tools p7zip f2fs-tools ntfs-3g go
```

##### Графические драйвера AMD
```
sudo pacman -S xf86-video-ati xf86-video-amdgpu mesa mesa-demos lib32-mesa vulkan-radeon lib32-vulkan-radeon vulkan-icd-loader lib32-vulkan-icd-loader amdvlk lib32-amdvlk network-manager-applet
```
##### Графические драйвера Intel
```
sudo pacman -S mesa mesa-demos xf86-video-intel lib32-mesa vulkan-intel lib32-vulkan-intel vulkan-icd-loader lib32-vulkan-icd-loader network-manager-applet libva-intel-driver lib32-libva-intel-driver
```