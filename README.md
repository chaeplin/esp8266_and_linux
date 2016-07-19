- [IDE](IDE.md)
- [CLI](CLI-Debian.md)
- [Micropython](Micropython.md)

### monitor serial
- screen /dev/ttyUSB0 115200
- Ctrl-a \

### install esptool.py
- pip2 install esptool

### erase flash completely
- esptool.py --port /dev/ttyUSB0 erase_flash

### Serial with non-root or su
- run sudoedit /etc/udev/rules.d/50-ttyusb.rules
- add
```
KERNEL=="ttyUSB[0-9]*",NAME="tts/USB%n",SYMLINK+="%k",GROUP="uucp",MODE="0666"
```
- replug serial

### Screen: cannot open your terminal '/dev/pts/0'
- check : http://www.electrictoolbox.com/screen-cannot-open-your-terminal/
- 1) Log out of the terminal/SSH session and log back in as the user you want to run screen as instead of using su.
- 2)
```
script /dev/null
screen /dev/ttyUSB0 115200
```
