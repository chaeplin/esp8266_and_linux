### Using IDE
- Sketch --> Export compiled Binary : binary will be in sketch foler
- copy file _67-WiFiManager.ino.bin to server
- scp _67-WiFiManager.ino.bin build@homesv:
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
