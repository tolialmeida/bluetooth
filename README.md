# bluetooth
information about bluetooth (usb dongle)
librarys in /opt/bt/bluez-5.37-src/src/shared
## Bash command
- dmesg |grep -i blue
- lsusb


## Configuration:

- change like root o sudo
- lsusb ( ok, you can see usb bluetooth dongle)
3. hciconfig -a (you can see all information about usb dongle, normally hci0)
4. hciconfig hci0 up; hciconfig hci0 piscan (start, enable page and inquiry scan)
