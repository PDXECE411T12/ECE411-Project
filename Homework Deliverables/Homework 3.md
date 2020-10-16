# Executive Summary

The idea of this project came from research into emerging technologies related to biohacking. The easiest way to “become a cyborg” is by getting an RFID implant and kitting your life with smart devices. The biggest pain point on equipping yourself with this technology is the cost involved. One of the most interesting smart technologies to us is smart locks. Most of the solutions out there are expensive and/or not something you’d want to put on the door of the rental you reside in. Being people who like putting technology together, we see how “easy” it is to put together a microcontroller, an RFID module, an actuator, and 3D printing in order to create a smart lock to use with existing hardware already on our doors. We would be able to present our authenticated hand or FOB to the door lock, and the door would unlock, that’s it!

# Market Analysis

Solution 1 - Level Bolt
* Not visible on the outside/inside of the door
* Great battery life
* Easy battery changes
* Bluetooth only
* Lacks internet connectivity
* Lacks a RFID/NFC sensor
* Depends on Bolt app and server support
* Expensive! - $229

Solution 2 - August Wi-Fi Smart Lock
* Not visible on the outside of the door
* Easiest installation
* Great battery life
* Easy battery changes
* Not compatible with all doors
* Wifi and Bluetooth only
* Lacks a RFID/NFC sensor
* Depends on August app and server support
* Expensive! - $249.99

Solution 3 - Most other smart locks
* Replaces entire lock assembly
* Has a pin-pad on the outside (therefore ugly and not discrete)
* Not always able to use existing lock
* Lacks a RFID/NFC sensor
* Less expensive, but still over $100

The smart lock solutions listed here do not have RFID/NFC as a method for unlocking. Existing solutions that use this are mainly focused on enterprise customers that are able to build out integrated locking methods into the door and frame that require a central controller for multiple doors. These methods are not only expensive but not feasible for a standard consumer. The market for smart locks start at around $150, so our solution should be less expensive.

# Requirements

* Must lock and unlock a door
* Must be able to work with existing doors
* Should be able to work with existing locks
* Should be able to use a normal key
* Should be able to lock/unlock from the inside by physical means
* Should be able to last for multiple years
* Should be durable
* Should be cheaper than market offerings (<$150)
* Must be able to work without an internet connection
* Should be able to work during a power outage
* Should be reliable
* May be easy to install
* May have a decent battery life
* May have smart home integration

# System Architecture

(Insert block diagram)

# Design Specification
* 3D printed housing that does not affect the structural integrity of the existing lock
* Custom PCB for ESP-12F Module to connect actuator and sensor
* Servo as the actuator
* RC-522 module located on the outside of the door
* AA battery powered

# Progress so far

* 3D printed model with accompanying lock to assist in CAD
![](./imgs/Lockmodel.jpg)
* Render of current CAD work
![](./imgs/DeadboltAssembly.png)
