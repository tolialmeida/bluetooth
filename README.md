# bluetooth
information about bluetooth (usb dongle)

## Configuration:

1.change like root o sudo
2. lsusb ( ok, you can see usb bluetooth dongle)
3. hciconfig -a (you can see all information about usb dongle, normally hci0)
4. hciconfig hci0 up; hciconfig hci0 piscan (start, enable page and inquiry scan)
