# ttyUSB-fixed
THIS FILE PRESENTS HOW TO FIX A TTYUSB TO ANY SPECIFIC DEVICE.  

Connect with any device. Here is an example with respect to Ultrasonic.  

Open a terminal and enter "lsusb".  

Write down the idVender and idProduct from the numbers in the yellow box, respectively, as follows:  
![](https://github.com/junqi047/ttyUSB-fixed/raw/master/img/idVendor_and_idProduct.png)  

In the terminal and enter "udevadm info /dev/ttyUSB0". The "ttyUSB*" depends on the port number.

Write down the information which is presented in the red box as follows:  

![](https://github.com/junqi047/ttyUSB-fixed/raw/master/img/12.PNG)  

Go to the folder: /ect/udev/rules.d  
Then"ls", check the name of the rules.  

![](https://github.com/junqi047/ttyUSB-fixed/raw/master/img/address.png)  

sudo gedit 77-ttyusb.rules  
Follow the templet as follows:  

KERNEL=="ttyUSB[0-9]*", MODE="0666"  
SUBSYSTEM=="tty", ATTRS{idVendor}=="1a86", ATTRS{idProduct}=="7523", SYMLINK+="Ultrasonic"  
SUBSYSTEM=="tty", ENV{ID_PATH}=="pci-0000:02:10.0-usb-0:2.1:1.0", SYMLINK+="Ultrasonic"  

Restart the USB and check the name according to "ls /dev".  

![](https://github.com/junqi047/ttyUSB-fixed/raw/master/img/13.PNG)  


