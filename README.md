# DepthSensing

## Installation & Setup
### Prerequisites
1.	Ubuntu 18.04 LTS
2.	Dependencies (CUDA)
3.	Linux Machine with at least one USB3.0 port (USB-A)
4.	Internet Connection
5.	Linux Machine with dedicated GPU (Recommended)
###	Hardware Setup
1. Start the hardware setup by booting the Linux Machine. 
2. Open the terminal and type  
```
dmesg –w  
```
3. Plug ZED2 camera USB cable to Linux Machine USB port. 
* New USB device must become visible at the real-time diagnostic output. 
Hardware is now successfully set up. 
### Software setup and Installation
Start the software setup by downloading the ZED SDK for your Linux Machine from:  
https://www.stereolabs.com/developers/release/  
1. Go to the directory where the installer has been downloaded.  
``` 
cd path/to/download/directory  
```
2. Add execution permission to the installer using the chmod +x command. Make sure to replace the installer name with the version you downloaded.  
```
chmod +x ZED_SDK_Tegra_JP45_v3.4.2.run   
```
3. Run the ZED SDK installer.    
```
./ ZED_SDK_Tegra_JP45_v3.4.2.run  
```
* At the beginning of the installation, the Software License will be displayed, hit q after reading it.  
During the installation, you might have to answer some questions on dependencies, tools and samples installation. Type y for yes and n for no and hit Enter. Hit Enter to pick the default option.  

### Generating Makefiles

1. Navigate to directory where project will be generated and built.
```
cd /home/username/  
```
2. Make new directory and navigate there. 
``` 
mkdir depthsensing  
cd depthsensing  
```
 3. Clone DepthSensing git repository.  
```
git clone https://github.com/gerhardmalberg88/DepthSensing.git  
```
4. Navigate to DepthSensing directory.  
```
$ cd DepthSensign  
```
* Depth sensing program and web server need to be set up separately.   
  
### Depth Sensing Program Setup
1. Navigate to DEPTHSENSING directory.  
```cd DEPTHSENSING
```

2. Make new directory named build if it is not created and navigate there.  
```
mkdir build  
cd build  
```
3. Generate native makefiles from CMake project file.  
```
sudo cmake ..  
```
4. Preprocess, compile, assemble and link.  
```
sudo make  
```
Depth sensing program is now successfully set up.   
   
### Web Server Setup
1. Navigate to SERVER/html directory.  
```
cd SERVER/html  
```
2. Give permission to all content in directory.  
```
sudo chmod 755 ExampleContent1 ExampleContent2  
```
3. Copy and replace all content from html directory to your /var/www/html/ directory.  
```
sudo cp {ExampleContent1,ExampleContent2} /var/www/html/  
```
4. Navigate to cgi-bin.  
```
sudo cd ..  
sudo cd cgi-bin  
```
5. Give permission to all content in directory.  
```
sudo chmod 755 ExampleContent1 ExampleContent2  
```
6. Copy and replace all the files from cgi-bin to /usr/lib/cgi-bin/  
```
sudo cp {ExampleContent1,ExampleContent2} /usr/lib/cgi-bin/  
```
* Remember to make sure that apache server has given permission to others in the network to access your
/usr/lib/cgi-bin/   
and  
/var/www/html/  
by modifying the apache2.config  file.  

Web server is now successfully set up.  

### Launch Depth Sensing Program
1. Navigate your build directory and execute program.
```
./DepthsensingV1
```
