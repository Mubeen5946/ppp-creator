# ppp-creator

1. Connect the USB LTE Modem into Raspberry Pi

2. Type sudo apt-get update to update list

3. Type sudo apt-get install rpi-update to install rpi-update

4. Type sudo rpi-update to update kernel
5. Type sudo reboot to reboot the Raspberry Pi
6. Type ls /dev after rebooting and logging well  to check ttyUSB3 is available or not(Note: Data Port: ttyUSB3, AT Command Port: ttyUSB2)

7. Create ppp-creator.sh with below script and put it into the Raspberry Pi

8. Type chmod +x ./ppp-creator.sh

9. Type sudo ./ppp-creator.sh INTERNET ttyUSB3 (Note: INTERNET is your APN name)

10. Type sudo pppd call quectel-ppp persist to keep PPP connect up，from ifconfig we will find ppp0 up，in this time we type sudo ip route add 0.0.0.0/0 dev ppp0 to make all packets going via ppp0

11. If you want to disconnect PPP, just running killall pppd

#Copied From
https://blog.enchose.com/raspberry-pi-runs-ppp-dial-up-quectel-ec25-lte-modem/
