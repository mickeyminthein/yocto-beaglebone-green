Hardware  

1. Beaglebone Green  
2. USB to TTL Serial Cable  
    (https://www.adafruit.com/product/954?srsltid=AfmBOopoXZV1nY7bMRwU13Qbwtu_iGT67DTkfTvBMrB0jgwm4haW3SpB)    
4. Mini USB Cable  
5. Host Computer (preferred 8 cores, 16 threads, 32 GB RAM, 500 GB SSD, Ubuntu OS: 22.04)  


Yocto Build Beaglebone Green 

Step 1. Setup Host computer : Install following packages from the host computer (OS: Ubuntu 22.04 LTS)    
$ sudo apt update
$ sudo apt install gawk wget git diffstat unzip texinfo gcc build-essential chrpath socat cpio python3 python3-pip python3-pexpect xz-utils debianutils iputils-ping python3-git python3-jinja2 libegl1-mesa libsdl1.2-dev pylint3 xterm python3-subunit mesa-common-dev zstd liblz4-tool   
$ pip3 install pylint  
$ sudo apt update
$ sudo apt install snapd  
$ sudo snap install --classic code                     

Step 2: Create a project folder and clone the poky in it  
$ mkdir yocto_beaglebone   
$ cd yocto_beaglebone 
$ git clone git://git.yoctoproject.org/poky -b kirkstone  

Step 3: Initialize Build Environment  
$ cd poky   
$ source oe-init-build-env  

Step 4: Edit Local Config
From vs code terminal,   
$ code local.conf  

MACHINE ?= "beaglebone-yocto"  
RM_OLD_IMAGE = "1"  
INHERIT += "rm_work"

Step 5: Build Image  
$ bitbake core-image-full-cmdline  







