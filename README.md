
# Hardware Build Guide
This guide will show you how to read use a USB GPS sensor and obtain user coordinates. The sensor used in this project is BU-353-S4 - USGlobalsat Corporate.
<br>
![Alt text](https://github.com/JustlikeRav/GPS-reciever/blob/master/GPS.jpeg?raw=true "GPS")
<br>
## Step 1: Order the Parts
The GPS used is fully compatible with Raspbian and the USGlobalsat Corporate has their own command line software to run it. Following is summary of the parts purchased.

1.	One Raspberry Pi 3 Model B for CA$45.95 from https://www.canakit.com/raspberry-pi-3-model-b.html?cid=cad&src=raspberrypi

2.	One BU-353-S4 USB GPS for CA$44.02 from https://www.amazon.ca/USGlobalsat-BU-353-S4-USB-Receiver-Black/dp/B008200LHW

3.	One 16GB mirco-sd card for the Raspberry pi. for CA$14.73 from https://www.amazon.ca/Sandisk-Ultra-Micro-UHS-I-Adapter/dp/B073K14CVB/ref=sr_1_1?s=electronics&ie=UTF8&qid=1516607340&sr=1-1&keywords=micro+sd+card+16gb

The total cost: CA$104.7
<br>
![Alt text](https://github.com/JustlikeRav/GPS-reciever/blob/master/eveything.jpeg?raw=true "Everything")
<br>
## Step 2: Disclaimer
The entire project should not take more than 45 minutes to complete. The sensor is pretty easy to install and it should not take more than 25 minutes. But before we have to start by installing Raspbian OS on Raspberry Pi.
<br>
## Step 3: Preparing your SD Card by installing Raspbian OS image.
1.	Insert your microSD card into your card reader and connect it with the computer
2.	Format the card in FAT32 format. I recommend using a free software called SD-card formatter for this purpose.
3.	Download Win32DiskImager from https://sourceforge.net/projects/win32diskimager/  unzip the downloaded file and run the utility file.
4.	Download the Raspbian image file from Raspberry Pi website https://www.raspberrypi.org/downloads/
5.	Select the Raspbian image file you downloaded.
6.	Select the drive of your SD card in the ‘Device’ dropdown.
7.	Select ‘Write’. The process will take 20 minutes to finish and then you're done.<br>
## Step 4: Mechanical Assembly
<br>The following steps will guide you to assemble your own working GPS sensor:<br>
1.	Place the Raspberry Pi on a non-conductive surface with GPIO pins facing up
2.	Connect the raspberry-pi-3-model-b with the internet using a CAT-5 cable.
3.	Connect the raspberry-pi-3-model-b with a mouse and a keyboard using USB.
4.	start terminal and input the following command to install the GPS drivers: "sudo apt-get install gpsd gpsd-clients python-gps"
5.	Next we need to start the daemon. This is done using the following command: "sudo gpsd /dev/ttyUSB0 -F /var/run/gpsd.sock"
6.	Ignore any messages from the console or in the log files, you may see it complaining about IPv6 but you can ignore that.
7.	Connect the GPS receiver with the pi by USB.
8.	Use the following command and the program will start running: cgps -s
<br>
![Alt text](https://github.com/JustlikeRav/GPS-reciever/blob/master/GPSoutput.JPG?raw=true "GPS")
<br>
## Unit Testing
<br>
This GPS receiver doesn't work indoors. The information of user's location is received by connecting with multiple satellites orbiting the Earth. For this connection, the sensor must be under open sky.
<br>
## Production Testing
If the raspberry-pi-3-model-b is purchased in bluck, i.e. more than 100 raspberrypis then cost of each pi drops down to CA$35 per pi. No such discount is offered by the GPS receiver. Since the code running on the pi is free and same for every scenario the total cost of production would reach CA$9,375 which is 10.7% cheaper than the original cost per unit. 

# References:
http://usglobalsat.com/p-688-bu-353-s4.aspx#images/product/large/688.jpg
<br>
https://www.raspberrypi.org/forums/viewtopic.php?f=28&t=128028
