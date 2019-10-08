# ansible-role-rpi_garage_door_opener
Setting up a RedSleeve based Raspberry Pi zero to work as a remote garage door opener

1. Download raspi-redsleeve7.4-cli-1.0.img.xz from [Github](https://github.com/redsleeve-linux/redsleeve-linux.github.io/releases/tag/rpi-7.4-1.0)
2. Write RedSleeve to an SD card with
```xzcat /run/media/jschrode/Drive1/Images/raspi-redsleeve7.4-cli-1.0.img.xz | dd status=progress bs=4M of=/dev/sda```
3. Login with ```rpi login: root``` and ```Password: password1234```
4. Change root password with ```[root@rpi ~]# passwd```
