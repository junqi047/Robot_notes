# ttyUSB-fixed
THIS FILE PRESENTS HOW TO FIX A TTYUSB TO ANY SPECIFIC DEVICE.
Connect with any device. Here is an example with respect to Ultrasonic.
Open a terminal and enter "lsusb".
Write down the idVender and idProduct from the numbers in the yellow box, respectively, as follows:
![](https://github.com/junqi047/ttyUSB-fixed/raw/master/img/idVendor_and_idProduct.png)
Go to the folder: /ect/udev/rules.d
Then"ls", check the name of the rules.
![](https://github.com/junqi047/ttyUSB-fixed/raw/master/img/address.png)
sudo gedit 71-persistent-net 
Follow the templet as follows:
![](https://github.com/junqi047/ttyUSB-fixed/raw/master/img/71-persistent-net.png)
Restart the USB and check the name according to "ls /dev".
