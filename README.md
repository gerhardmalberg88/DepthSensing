# DepthSensing

## Installation & Setup
### Prerequisites
1.	Ubuntu 18.04 LTS
2.	Dependencies (CUDA)
3.	Linux Machine with at least one USB3.0 port (USB-A)
4.	Internet Connection
5.	Linux Machine with dedicated GPU (Recommended)
###	Hardware Setup
Start the hardware setup by booting the Linux Machine. Open the terminal and type  
$ dmesg –w
To get information about the system diagnostic. Then plug ZED2 camera USB cable to Linux Machine USB port. New USB device must become visible at the real-time diagnostic output. Hardware is now successfully set up. 
## Software setup and Installation
Start the software setup by downloading the ZED SDK for your Linux Machine from:  
https://www.stereolabs.com/developers/release/  
Go to the directory where the installer has been downloaded.  
$ cd path/to/download/directory  
Add execution permission to the installer using the chmod +x command. Make sure to replace the installer name with the version you downloaded.  
$ chmod +x ZED_SDK_Tegra_JP45_v3.4.2.run   
Run the ZED SDK installer.    
$ ./ ZED_SDK_Tegra_JP45_v3.4.2.run  
At the beginning of the installation, the Software License will be displayed, hit q after reading it.  
During the installation, you might have to answer some questions on dependencies, tools and samples installation. Type y for yes and n for no and hit Enter. Hit Enter to pick the default option.  
After the ZED SDK is installed clone DepthSensing repository to your local repository by navigating to the directory you want the program to be build. Start by navigating to your chosen directory (for example to the home directory).  
$ cd /home/username/  
Make new directory and navigate there.  
$ mkdir depthsensing  
$ cd depthsensing  
 Then clone DepthSensing git repository.  
$ git clone https://github.com/gerhardmalberg88/DepthSensing.git  
Navigate to DepthSensing directory.  
$ cd DepthSensign  
Depth sensing program and web server need to be set up separately.   
  
To set up Depth sensing program, navigate to DEPTHSENSING directory.  
$ cd DEPTHSENSING  
Make new directory named build if it is not created and navigate there.  
$ mkdir build  
$ cd build  
Generate native makefiles from CMake project file.  
$ sudo cmake ..  
Preprocess, compile, assemble and link.  
$ sudo make  
Depth sensing program is now successfully set up.   
   
To set up web server, navigate to SERVER/html directory.  
$ cd SERVER/html  
Give permission to all content in directory.  
$ sudo chmod 755 ExampleContent1 ExampleContent2  
Copy and replace all content from html directory to your /var/www/html/ directory.  
$ sudo cp {ExampleContent1,ExampleContent2} /var/www/html/  
Navigate to cgi-bin.  
$ sudo cd ..  
$ sudo cd cgi-bin  
Give permission to all content in directory.  
$ sudo chmod 755 ExampleContent1 ExampleContent2  
Copy and replace all the files from cgi-bin to /usr/lib/cgi-bin/  
$ sudo cp {ExampleContent1,ExampleContent2} /usr/lib/cgi-bin/  
Remember to make sure that apache server has given permission to others in the network to access your /usr/lib/cgi-bin/ and /var/www/html/ by modifying the apache2.config  
Web server is not successfully set up.  
