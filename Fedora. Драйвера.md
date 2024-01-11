#fedora #linux #инструкция #производительность 
##### Установка драйверов и кодеков
```
sudo dnf install libva-intel-driver intel-media-driver intel-gpu-firmware libheif-freeworld p7zip f2fs-tools ntfs-3g android-tools unrar unzip unace squashfs-tools

sudo dnf groupupdate multimedia sound-and-video

sudo dnf install ffmpeg-libs --allowerasing
```

##### Удаление ненужных репозиториев
- Отключение:
```
sudo dnf config-manager --set-disabled fedora-cisco-openh264
```
- Удаление ненужного софта:
```
sudo dnf remove openh264 mozilla-openh264 gstreamer1-plugin-openh264
```