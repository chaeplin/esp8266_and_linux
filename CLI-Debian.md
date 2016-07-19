### A makefile for ESP8266 Arduino projects
- https://github.com/plerup/makeEspArduino
```
cd ~
git clone https://github.com/esp8266/Arduino.git
mv Arduino esp8266
cd esp8266/tools
python get.py
```

```
cd ~
git clone https://github.com/plerup/makeEspArduino.git
cd makeEspArduino
make -f makeEspArduino.mk upload
```

### makeEspArduino.mk:175: recipe for target 'upload' failed
- change reset method for nodemcu
```
#UPLOAD_RESET ?= ck
UPLOAD_RESET ?= nodemcu
```


```
build@debian:~/makeEspArduino$ make -f makeEspArduino.mk upload
heap.c
WMath.cpp
spiffs_api.cpp
core_esp8266_wiring_pwm.c
Schedule.cpp
base64.cpp
abi.cpp
FS.cpp
cencode.c
cdecode.c
Esp.cpp
cbuf.cpp
spiffs_hal.cpp
WString.cpp
core_esp8266_wiring_shift.c
core_esp8266_flash_utils.c
MD5Builder.cpp
pgmspace.cpp
libc_replacements.c
core_esp8266_i2s.c
core_esp8266_wiring_analog.c
core_esp8266_wiring.c
cont.S
Print.cpp
core_esp8266_noniso.c
spiffs_hydrogen.c
spiffs_gc.c
spiffs_nucleus.c
spiffs_cache.c
spiffs_check.c
core_esp8266_main.cpp
core_esp8266_eboot_command.c
debug.cpp
time.c
HardwareSerial.cpp
cont_util.c
uart.c
core_esp8266_phy.c
core_esp8266_timer.c
core_esp8266_wiring_digital.c
IPAddress.cpp
core_esp8266_wiring_pulse.c
core_esp8266_si2c.c
StreamString.cpp
Stream.cpp
Updater.cpp
Tone.cpp
umm_malloc.c
core_esp8266_postmortem.c
Creating core archive
HelloServer.ino
Wire.cpp
WiFiClientSecure.cpp
ESP8266WiFiGeneric.cpp
ESP8266WiFiSTA.cpp
ESP8266WiFiScan.cpp
WiFiClient.cpp
WiFiServer.cpp
ESP8266WiFi.cpp
ESP8266WiFiMulti.cpp
WiFiUdp.cpp
ESP8266WiFiAP.cpp
ESP8266mDNS.cpp
Parsing.cpp
ESP8266WebServer.cpp
Linking /tmp/HelloServer/HelloServer.bin
  Versions: 2.3.0, 2.3.0

Memory usage
  Ram:    35316 bytes
  Flash: 249460 bytes

Build complete. Elapsed time: 9 seconds

esptool v0.4.9 - (c) 2014 Ch. Klippel <ck@atelier-klippel.de>
opening port /dev/ttyUSB0 at 230400
opening bootloader
resetting board
trying to connect
trying to connect
Uploading 253600 bytes from /tmp/HelloServer/HelloServer.bin to flash at 0x00000000
................................................................................ [ 32% ]
................................................................................ [ 64% ]
................................................................................ [ 96% ]
........                                                                         [ 100% ]
starting app without reboot
closing bootloader
build@debian:~/makeEspArduino$ 
```