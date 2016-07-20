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

### install avahi-daemon for OTA
- apt-get install avahi-daemon
- systemctl enable avahi-daemon.service
- service avahi-daemon restart


### makefile for ArduinoJson
```
#=== Project specific definitions: sketch and list of needed libraries
SKETCH ?= $(HOME)/work/a68-acir-for-bedroom.ino
LIBS ?= $(ESP_LIBS)/ESP8266WiFi \
$(ESP_LIBS)/ESP8266mDNS \
$(ESP_LIBS)/ArduinoOTA \
$(HOME)/esp8266_libraries/pubsubclient/src \
$(HOME)/esp8266_libraries/IRremoteESP8266 \
$(HOME)/esp8266_libraries/lgwhisen \
$(HOME)/esp8266_libraries/Time

INCLUDE_DIRS = $(HOME)/esp8266_libraries/ArduinoJson

# OTA parameters
# hostname of ota + .local
ESP_ADDR ?= esp-irbedroom.local
#ESP_ADDR ?= 192.168.x.x
ESP_PORT ?= 8266
ESP_PWD ?= xxxx


````

### command
- make -f makeEspArduino.mk
- make -f makeEspArduino.mk upload
- make -f makeEspArduino.mk ota
