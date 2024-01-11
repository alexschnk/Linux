#безопасность #браузер #инструкция #linux #android #технологии #производительность 
- **Кеш Firefox в ОЗУ**
```
about:config

browser.cache.disk.enable - "false" 

browser.cache.disk.capacity - 0 

browser.cache.memory.enable - "true" 

browser.cache.memory.capacity - -1

browser.cache.disk_cache_ssl - false

browser.cache.offline.enable - false
```
- **Ускорение интернета**
```
about:config

network.http.max-persistent-connections-per-server - до 10 (но не больше) 

network.http.max-connections - 900

network.http.http3.enabled - false (ускорение Гугл и ютуб)

browser.sessionstore.interval - частота записи на диск (больше - лучше)

browser.sessionhistory.max_entries - 5 (количество ссылок назад/вперёд)
```
- **Отключение телеметрии**
```
browser.ping-centre.telemetry - false

security.ssl.errorReporting.automatic - true

toolkit.identity.enabled - false

toolkit.telemetry.archive.enabled - false

toolkit.telemetry.bhrPing.enabled - false

toolkit.telemetry.coverage.opt-out - false

toolkit.telemetry.enabled - false

toolkit.telemetry.firstShutdownPing.enabled - false

toolkit.telemetry.hybridContent.enabled - false

toolkit.telemetry.infoURL - пусто

toolkit.telemetry.newProfilePing.enable - false

toolkit.telemetry.reportingpolicy.firstRun - false

toolkit.telemetry.server - пусто

toolkit.telemetry.shutdownPingSender.enabled - false

toolkit.telemetry.unified - false

toolkit.telemetry.updatePing.enabled - false
```
- **Отчеты корпорации Mozilla**
```
datareporting.healthreport.uploadEnabled - false

datareporting.policy.dataSubmissionEnabled - false

datareporting.policy.firstRunURL - пусто
```
- **Настройки плавного скрола**
```
general.smoothScroll.currentVelocityWeighting - 0

general.smoothScroll.durationToIntervalRatio - 1000

general.smoothScroll.lines.durationMaxMS -150

general.smoothScroll.lines.durationMinMS - 0

general.smoothScroll.mouseWheel.durationMaxMS - 150

general.smoothScroll.mouseWheel.durationMinMS - 0

general.smoothScroll.mouseWheel.migrationPercent - 0

general.smoothScroll.msdPhysics.continuousMotionMaxDeltaMS - 250

general.smoothScroll.msdPhysics.enabled - true

general.smoothScroll.msdPhysics.motionBeginSpringConstant - 450

general.smoothScroll.msdPhysics.regularSpringConstant - 450

general.smoothScroll.msdPhysics.slowdownMinDeltaMS - 50

general.smoothScroll.msdPhysics.slowdownSpringConstant - 5000

general.smoothScroll.other - true

general.smoothScroll.other.durationMaxMS - 150

general.smoothScroll.other.durationMinMS - 0

general.smoothScroll.pages.durationMaxMS - 150

general.smoothScroll.pages.durationMinMS - 0

general.smoothScroll.pixels - true

general.smoothScroll.pixels.durationMaxMS -150

general.smoothScroll.pixels.durationMinMS - 0

general.smoothScroll.scrollbars.durationMaxMS - 600

general.smoothScroll.scrollbars.durationMinMS - 0

general.smoothScroll.stopDecelerationWeighting - 0.2

mousewheel.acceleration.factor - 5
```
- **Ускорение отрисовки**
```
gfx.use_text_smoothing_setting - true

gfx.webrender.enabled - true

gfx.webrender.highlight-painted-layers - false

layers.acceleration.force-enabled - true

nglayout.initialpaint.delay - 0 (рендер без задержки)

webgl.force-enabled = true

gfx.webrender.all = true

dom.webgpu.enabled = true

widget.wayland-dmabuf-vaapi.enabled = true

media.ffmpeg.vaapi.enabled = true

media.ffmpeg.low-latency.enabled = true

media.navigator.mediadatadecoder_vpx_enabled = true

media.ffvpx.enabled = false

media.rdd-ffvpx.enabled = false

media.rdd-vpx.enabled = false
```
- **Настройки приватности**
```
privacy.resistFingerprinting - true

privacy.resistFingerprinting.autoDeclineNoUserInputCanvasPrompts - false

extensions.pocket.enabled - false

media.peerconnection.enabled - false

Просмотреть все:
1) privacy.trackingprotection (включить все)
2) fingerprinting (включить)
```
- **Расширения**
```
1) No script 
2) Canvas defender 
3) Ublock origin + фильтр IP-логеров
4) Dark reader
5) Clear URLs 
6) Chameleon
7) TWP - translate web page 
8) Firefox multi-account Containers 
9) Decentraleyes
10) Temporary container 
11) Disconnect 
```
- **Профиль в ОЗУ**

а) Установка службы
```
sudo pacman -S profile-sync-daemon
```
б) Генерация настроек
```
psd
```
в) Редактирование настроек

```sudo nano /home/facade/.config/psd/psd.conf
BROWSERS=(firefox)
```
г) После этого нужно закрыть файрфокс и запустить psd командой
```
systemctl --user start psd.service
```
д) После  посмотреть что с сервисом
```
systemctl --user status psd.service
psd preview
```