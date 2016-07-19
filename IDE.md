### Using IDE
- Verify/Compile
```
"/Users/userX/Library/Arduino15/packages/esp8266/tools/esptool/0.4.9/esptool" -eo "/Users/userX/Documents/Arduino/hardware/esp8266com/esp8266/bootloaders/eboot/eboot.elf" -bo "/var/folders/fl/fwwl5csx3w1520w0kz6kvh940000gq/T/build03e48dfea2dd66c248dfca5f0f1e8743.tmp/_67-WiFiManager.ino.bin" -bm dio -bf 40 -bz 4M -bs .text -bp 4096 -ec -eo "/var/folders/fl/fwwl5csx3w1520w0kz6kvh940000gq/T/build03e48dfea2dd66c248dfca5f0f1e8743.tmp/_67-WiFiManager.ino.elf" -bs .irom0.text -bs .text -bs .data -bs .rodata -bc -ec
Using library ESP8266WiFi at version 1.0 in folder: /Users/userX/Documents/Arduino/hardware/esp8266com/esp8266/libraries/ESP8266WiFi 
Using library DNSServer at version 1.1.0 in folder: /Users/userX/Documents/Arduino/hardware/esp8266com/esp8266/libraries/DNSServer 
Using library ESP8266WebServer at version 1.0 in folder: /Users/userX/Documents/Arduino/hardware/esp8266com/esp8266/libraries/ESP8266WebServer 
Using library WiFiManager at version 0.12 in folder: /Users/userX/Documents/Arduino/libraries/WiFiManager 
Using library Ticker at version 1.0 in folder: /Users/userX/Documents/Arduino/hardware/esp8266com/esp8266/libraries/Ticker 

Sketch uses 340,030 bytes (32%) of program storage space. Maximum is 1,044,464 bytes.
Global variables use 37,084 bytes (45%) of dynamic memory, leaving 44,836 bytes for local variables. Maximum is 81,920 bytes.
```
- copy file after "-bo" to linux : /var/folders/fl/fwwl5csx3w1520w0kz6kvh940000gq/T/build03e48dfea2dd66c248dfca5f0f1e8743.tmp/_67-WiFiManager.ino.bin
- scp /var/folders/fl/fwwl5csx3w1520w0kz6kvh940000gq/T/build03e48dfea2dd66c248dfca5f0f1e8743.tmp/_67-WiFiManager.ino.bin root@homesv
- upload : esptool.py -p /dev/ttyUSB0 --baud 115200 write_flash --flash_size=8m 0 _67-WiFiManager.ino.bin
```
debian:~/build# esptool.py -p /dev/ttyUSB0 --baud 115200 write_flash --flash_size=8m 0 _67-WiFiManager.ino.bin 
esptool.py v1.1
Connecting...
Running Cesanta flasher stub...
Flash params set to 0x0020
Writing 348160 @ 0x0... 348160 (100 %)
Wrote 348160 bytes at 0x0 in 30.3 seconds (92.0 kbit/s)...
Leaving...
debian:~/build# 
```

```
*WM: AutoConnect
*WM: Connecting as wifi client...
*WM: Using last saved values, should be faster
*WM: Connection result: 
*WM: 0
*WM: SET AP STA
Entered config mode
192.168.4.1
AutoConnectAP-2743
*WM: 
*WM: Configuring access point... 
*WM: AutoConnectAP-2743
*WM: password123
*WM: AP IP address: 
*WM: 192.168.4.1
*WM: HTTP server started
```
