# ansible-role-rpi_garage_door_opener
Setting up a RedSleeve based Raspberry Pi zero to work as a remote garage door opener (hardware required)

1. Download raspi-redsleeve7.4-cli-1.0.img.xz from [Github](https://github.com/redsleeve-linux/redsleeve-linux.github.io/releases/tag/rpi-7.4-1.0)
2. Write RedSleeve to an SD card with
```xzcat /run/media/jschrode/Drive1/Images/raspi-redsleeve7.4-cli-1.0.img.xz | dd status=progress bs=4M of=/dev/sda```
3. Login with ```rpi login: root``` and ```Password: password1234```
4. Change keyboard layout to your locale with ```loadkeys de``` for german layout
5. Make keyboard layout permanent with ```localectl set-keymap de```
6. Change root password with ```[root@rpi ~]# passwd```
7. Set up networking with ```nmtui```:
  * select ```Activate a connection```
  * choose your Wifi to connect to and provide the password
  * select ```<Back>```
  * select ```Set system hostname``` and provide a meaningful name for the system
  * select ```Quit```
8. Install required software with ```yum install git```
