Initial idea for this came from a desire to use my newly acquired NExT implant. https://dangerousthings.com/product/next/

It contains a T5577 and NTAG216. The T5577 can emulate many LF cards. I can use it for the PSU ID system, but currently have it set to my work’s card which is also HID. 

Trying to find NFC or RFID locks, I have not been able to find any that are less than $100 and they all look terrible in my opinion. The only option that I really appreciate is the Level Bolt which is a retrofit to your existing door. https://level.co/products/bolt The only problem is that this does not include RFID or NFC. 

Looking at DIY options I haven’t been able to find any that look good or have the features I want. On the Dangerous Things forum, they have an open project recently updated with some folks making initial prototypes.

https://forum.dangerousthings.com/t/open-source-deadbolt-lock/4841

Functionally, this is very similar to the project in mind here, with the exception of the removal of the lock core. While I totally agree that the lock provided by most front doors are quite easy to get into, renting a place requires that the lock not be changed. The landlord must be able to access the home and lock changes are sometimes written into the contract must be performed with the owner’s knowledge. 

Using an ESP8266 as an RFID access control system looks to have been accomplished. https://github.com/esprfid/esp-rfid
This project allows the use of a couple of different types of readers in an access control environment. The project’s creators have even spun up a board that has a relay to control various types of standard door locks/actuators. Some of these include strike plates and magnets. 
All else fails when controlling the door, we can just use a magnet as our actuator with a relay just as this project does. 


TBD feature List:
* WiFi
* Battery powered
* NFC / RFID
* Manually bypassable on both sides of the door (key or turn knob)
* Same lock is used (good for renters)

Possible design considerations:
ESP8266 or ESP32 module with built-in wifi
Servo or small stepper motor to actuate the lock
RFID or NFC module (needing approval from the professor)
AA batteries are a good solution for cost-effectiveness, however, a stretch goal could include a small lipo battery and low voltage cut-off. 

Shopping List:
* Microcontroller module ESPXX or ESPXXXX
* Actuator
* NFC/RFID module
* Batteries
* Small screws and fasteners