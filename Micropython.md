### upload micropython image
- download image for esp8266 : https://micropython.org/download/#esp8266
- wget http://micropython.org/resources/firmware/esp8266-2016-07-19-v1.8.2-19-gc3f519a.bin
- esptool.py -p /dev/ttyUSB0 --baud 115200 write_flash --flash_size=8m 0 esp8266-2016-07-19-v1.8.2-19-gc3f519a.bin
```
debian:~/build# esptool.py -p /dev/ttyUSB0 --baud 115200 write_flash --flash_size=8m 0 esp8266-2016-07-19-v1.8.2-19-gc3f519a.bin
esptool.py v1.1
Connecting...
Running Cesanta flasher stub...
Flash params set to 0x0020
Writing 507904 @ 0x0... 507904 (100 %)
Wrote 507904 bytes at 0x0 in 44.2 seconds (92.0 kbit/s)...
Leaving...
debian:~/build#
```
- press reset button
- screen /dev/ttyUSB0 115200
```
performing initial setup
bcn 0
del if1
usl
add if1
#4 ets_task(4020e374, 29, 3fff7060, 10)
dhcp server start:(ip:192.168.4.1,mask:255.255.255.0,gw:192.168.4.1)
bcn 100
could not open file 'main.py' for reading

#5 ets_task(4010035c, 3, 3fff62f0, 4)
MicroPython v1.8.2-19-gc3f519a on 2016-07-19; ESP module with ESP8266
Type "help()" for more information.
>>> help()
Welcome to MicroPython!

For online docs please visit http://docs.micropython.org/en/latest/esp8266/ .
For diagnostic information to include in bug reports execute 'import port_diag'.

Basic WiFi configuration:

import network
sta_if = network.WLAN(network.STA_IF); sta_if.active(True)
sta_if.scan()                             # Scan for available access points
sta_if.connect("<AP_name>", "<password>") # Connect to an AP
sta_if.isconnected()                      # Check for successful connection
# Change name/password of ESP8266's AP:
ap_if = network.WLAN(network.AP_IF)
ap_if.config(essid="<AP_NAME>", authmode=network.AUTH_WPA_WPA2_PSK, password="<password>")

Control commands:
  CTRL-A        -- on a blank line, enter raw REPL mode
  CTRL-B        -- on a blank line, enter normal REPL mode
  CTRL-C        -- interrupt a running program
  CTRL-D        -- on a blank line, do a soft reset of the board
  CTRL-E        -- on a blank line, enter paste mode

For further help on a specific object, type help(obj)
>>> 
```

### more info
- https://github.com/micropython/micropython/blob/master/esp8266/README.md

