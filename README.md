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

# Generally:
You can put in the payload (31 bytes), but there are standar configuration like ibeacon. Ibeacon is a bluetooth advertisen no connetable. eddystone = ibeacon (apple) beacon but made for google, with theirs configuration. 
In mode advertising if you like more information, the central (normaly) ask between every beacon advertising signal---> scan response, if there are more data configurated in the module advertising (in this case beacon) this answer.

# dongle usb ibeacon:
- sudo hciconfig hci0 up
- sudo hciconfig hci0 leadv 3

      command    -------    ogf --- ocf   ---------------------PAYLOAD------31bytes-------------------------------------------     
      
sudo hcitool -i hci0 cmd 0x08 0x0008 1e 02 01 1a 1a ff 4c 00 02 15 e2 c5 6d b5 df fb 48 d2 b0 60 d0 f5 a7 10 96 e0 00 00 00 00 c5 00

where  ogf 0x08, ocf 0x0008:  value to configure payload 
      0x001e: Nº total bytes used (in hex, 30 decimal)
      now the payload is (1º length, 2º type, 2º value) (1º length, 2º value) (1º length, 2º value)..... 
      02 (length) ; 01(type)  1aflags (value)
      1a (length (26 decimal)) = ibeacon configuration: ff(Type) 4c 00 (apple company) 00 02.... (UUID) 

now the dongle is a ibeacon with a uidd. almost everything is data payload is UUID...HOw Can I put more data???: in scan response. 
# scan response
                                    ----- PAYLOAD--------------
sudo hcitool -i hci0 cmd 0x08 0x0008 total_length mibyte mibyte mibyte.....
