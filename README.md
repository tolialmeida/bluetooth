# bluetooth
- information about bluetooth (usb dongle)
- librarys in /opt/bt/bluez-5.37-src/src/shared

# Bash command
- dmesg |grep -i blue
- lsusb


# Configuration:

- change like root o sudo
- lsusb ( ok, you can see usb bluetooth dongle)
3. hciconfig -a (you can see all information about usb dongle, normally hci0)
4. hciconfig hci0 up; hciconfig hci0 piscan (start, enable page and inquiry scan)

# dongle usb ibeacon:
- sudo hciconfig hci0 up
- sudo hciconfig hci0 leadv 3
- sudo hcitool -i hci0 cmd 0x08 0x0009 0c 0b 09 6c 69 6e 6b 6d 6f 74 69 6f 6e 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
where 0x08 : ofg and ocf value to configure payload 
      0x0009: Nº total bytes used (in hex)
      
