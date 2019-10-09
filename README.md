# ansible-role-rpi_garage_door_opener
Setting up a RedSleeve based Raspberry Pi zero to work as a remote garage door opener (hardware required)

* Download *raspi-redsleeve7.4-cli-1.0.img.xz* (or any newer release) from [Github](https://github.com/redsleeve-linux/redsleeve-linux.github.io/releases/tag/rpi-7.4-1.0)
* Write RedSleeve to an SD card with  
  ```xzcat /run/media/jschrode/Drive1/Images/raspi-redsleeve7.4-cli-1.0.img.xz | dd status=progress bs=4M of=/dev/sda```
* Login with ```rpi login: root``` and ```Password: password1234```
* Change keyboard layout to your locale with  
  ```[root@rpi ~]# loadkeys de```  
  for german layout
* Make keyboard layout permanent with  
 ```[root@rpi ~]# localectl set-keymap de```
* Change root password with  
  ```[root@rpi ~]# passwd```
* Set up networking with  
  ```[root@rpi ~]# nmtui```
  - select ```Activate a connection```
  - choose your Wifi to connect to and provide the password
  - select ```<Back>```
  - select ```Set system hostname``` and provide a meaningful name for the system
  - select ```Quit```
* Resize root filesystem with  
  ```[root@rpi ~]# fdisk /dev/mmcblk0```
  - type ```d``` and accept with ```<Enter>```
  - type ```n``` and accept all questions with ```<Enter>```
  - type ```w``` and ```<Enter>``` to write and exit fdisk
  - enter  
    ```[root@rpi ~]# reboot``` to reboot the system and re-read partition table
  - login as root with the password you set above
  - enter  
    ```[root@rpi ~]# resize2fs /dev/mmcblk0p2``` to resize the root filesystem
* Install required software with 
  - ```[root@rpi ~]# yum -y install epel-release```
  - ```[root@rpi ~]# yum -y install git ansible vim screen```
  - ```[root@rpi ~]# yum -y update```
  and activate updated packages with
  - ```[root@rpi ~]# reboot```
* Login again as root and clone this repository with 
  ```[root@rpi ~]#  git clone https://github.com/joschro/ansible-role-rpi_garage_door_opener.git```
* Change directory to this repository with 
  ```[root@rpi ~]# cd ansible-role-rpi_garage_door_opener```
* Run the Ansible playbook to automate the rest of the installation process with
  ```ansible-playbook playbook.yml```
