# WebRemote-ESP32
This is migration of the KushlaVR/Web-Remote to ESP32

In order to use it:
0) Install USB/COM port driver for your ESP32 board, e.g. Silicon Labs CP210x USB to UART Bridge.
1) Install VSCode + PlatformIO extension.
2) In PlatformIO install ESP32 platform
3) Connect ESP32 board to PC
4) Check connectivity and COM port using *"Devices"* task of PlatformIO.
You should see something like that:
 > Executing task in folder WebRemote-ESP32: C:\Users\\<Windows_User>\.platformio\penv\Scripts\platformio.exe device list <
 > COM3
 > ----
 > Hardware ID: USB VID:PID=10C4:EA60 SER=0001 LOCATION=1-2  
 > Description: Silicon Labs CP210x USB to UART Bridge (COM3)

5) Open this project 
6) Select *Clean* project task on the project:
![Clean task](https://github.com/krukhlis/WebRemote-ESP32/blob/assets/Clean.PNG)
7) Select *Build* task
![Build task](https://github.com/krukhlis/WebRemote-ESP32/blob/assets/Build.PNG)
8) If everything was built successfully:
* push and hold "boot" button of your ESP32. If you don't have it -- the corresponding pin( e.g. IO0 for ESP-Cam) should be connected to GND. 
* select *Upload* task.
![Upload task](https://github.com/krukhlis/WebRemote-ESP32/blob/assets/Upload.PNG)
* After succesfull upload -- reset board( either by button, either disconnect and re-connect it via USB). 
**PLEASE NOTE, IF YOU HAD PIN connected to GND -- disconnect it before re-connect**
9) You also need to flash data folder to File System memory:
* (Optional) Erase existing flash data by selecting Erase Flash
* Upload FileSystem using corresponding task under your board's platform menu:
![Upload FileSystem/data task](https://github.com/krukhlis/WebRemote-ESP32/blob/assets/UploadFS.PNG)
Now, you are done flashing firmware and file system. The next steps are the same as with regular WebRemote firmware:
1) Connect from your phone/tablet/pc to corresponding WiFi network of your ESP32. The default WiFi password is 12345678
2) Open webbrowser and navigate to http://192.168.4.1
3) Enjoy :)
