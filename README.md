# PianoMoodDetect
This will be the machine learning port of PianoMoodDetect, which will take audio spectrograms in near real-time and determine its mood.

## Instructions
### Required Hardware
- Arduino Nano 33 BLE Sense
- MicroUSB cable to a port that can connect to a computer
- Computer
- *Smartphone*
- **Power Bank**

### Required Software
- Arduino IDE*
- *rNF Connect (Android) or LightBlue (Apple and Android)*


*italics*: Optional, only needed if want to run remotely connectd to smartphone

**bold**: Optional, only needed if want to run disconnected from computer

\*For Apple devices and most Windows devices, **Arduino IDE 1.8.15** should work, but if on Windows and it returns a "The filename or extension is too long." error, use the **Arduino IDE 2.0 beta** as it avoids the Windows internal 32k character max command line restriction.


### How to Run
1. Make sure all the required hardware and software are installed
2. Donwload the [zip library](ei-pianomd-nano-arduino-1.0.5.zip)
3. Choose which program/s to download
  - [PMD](PMD.ino) - bluetooth enabled, returns most occured mood over 10 sec period and raw mood data
  - [PMD_MostOccured_NoBluetooth](PMD_MostOccured_NoBluetooth.ino) - returns most occured mood over 10 sec period and raw mood data
  - [PMD_Raw](PMD_Raw.ino) - returns raw mood data
4. Run Arduino IDE
5. Connect the Nano to the computer through the USB
6. On the very top, Sketch -> Include Library -> Add .Zip Library and selected the installed **ei-pianomd-nano-arduino-1.0.5.zip** zip file
7. Install required boardss through, Tools -> Boards -> Board Manager and search and install **Arduino Mbed OS Nano Boards** by Arduino
8. Select the board with, Tools -> Boards -> **Arduino Mbed OS Nano Boards** -> Arduino Nano 33 BLE
9. Select the correct port the Nano is connect to with, Tools -> Port -> [USB Port]
10. If using **PDM.ino**, jump to [Blluetooth Instructions](https://github.com/fieryraidenx/PianoMoodDetect#ble-instructions)
11. Press the forward arrow **Upload** button on top left
12. After done compiling (it can take upwards of 30 min the first compile), press magnifying glass **Serial Monitor** on the top right
13. Results will be displayed on the Serial Monitor

### BLE Instructions
11. Install the **ArduinoBLE library**, Sketch -> Include Library -> Manage Library -> Search and Install ArduinoBLE by Arduino
12. Press the forward arrow **Upload** button on top left
13. After done compiling (it can take upwards of 30 min the first compile), press magnifying glass **Serial Monitor** on the top right
14. Results will be displayed on the Serial Monitor
15. Open rNF Connect or LightBlue
16. Select and Connect to PMDMonitor
17. Select the Unknown Attribute typically at the very bottom with the UUID "19B10000-E8F2-537E-4F6C-D104768A1214"
18. If on LightBlue, press Read / Read Again to retrieve value
19. If on rNF Connect, press the download symbol on the very right side of the Unknown Attribute to retrieve value
20. Compare value with key
  - 00 : Error or Initial Value
  - 01 : Angry
  - 02 : Happy
  - 03 : Sad
  - 04 : Silence
21. (OPTIONAL) disconnect the Nano from the computer and connect it to a powerbank, attach both of it to your arm to detect the data without connecting to a computer


## About Us
This group project is made for Wearable Devices and Computer Vision Course (DGMD S-14) from Harvard Secondary School / Harvard Extension School in Summer 2021.
The base classification code is generated by Edge Impulse but modified by Isaac Song (iiisong)

Members: Alex Gianini (aeg224), Kaif Jeelani (fieryraidenx), Isaac Song (iiisong)


To contact us,

Alex Gianini: alexanderegiannini@gmail.com

Kaif Jeelani: kaif.ajeelani@gmail.com

Isaac Song: isaacsong03@gmail.com
