# Noah Notes
Use BUS connection on schematic

White background.
Add voltage for battery, and the actual battery. ~4.5V in text.
Maybe add testpoint to P4 in Linear Regulator

Shield is not attached to GND for X4.
Double check if reset can float.
Double check that RTS can do Reset
Visually connect GPIO to Ports

RFID: Pick I2C or SPI? Guess is using SDA as chip select.
If I2C use pullups, if SPI then SDA should be chip select.

Label J3. 
Switch has values, d2, …

More ground stitching under SP, and at STARS

Show GND; 


The USB might not want to be connected to ground?
Look for a better USB, with shield.
Always get USB design rules errors because it is pushed into board.

Thermal Ground Vias, Overlap DRC. 

# MILES NOTES
# Concept
Door lock
puck goes over the door lock
not modifying the lock itself
RFID card/fob to open the door
Battery with a servo for activation

### RFID Door opener

Black background = fired

### Power
* Battery Voltage
    - Triple AA battery holder
    - Should be on the schematic
* Reverse Voltage Protection
    - Looks good
* As long as reference Adafruit, we're good
* P4 is floating
    - Test point?

### USB UART Bridge
* CP2104
* x4 USB adapter
    - No shield
    - Should not be attached to ground (USB Spec)
* Reset, Suspend floating?
* RTS+CTS is reset
    - Assume that it just works?

### ESP
* GPIO2,15, why? Probably fine.
* Unused pins -> Test Points? 
* Connect the Nets visually GPIO pins

### RFID
* SPY 3.3V
* I2C
* Both? Why? Choose 1.
* 1 is chip select?
* If it works, it works, but red flags.

### Servo
* Battery feedback
* Label J3
    - Internal Lock, unlock
* needs junction for GPIO5 (fixed during review)

### ERC Errors
* Warnings.
    - D2 Should have name
    - Should have values
* No Supply for input power
    - Invoke Thermal slug
    - Needed thermal pad

# Board Design
* Great board
* Nothing wrong?
* Ground vias under the ESP
    - Really wants ground
* A bunch near GND pin of ESP
* Kinda packed
* USB Shield -> GND
    - Is bad
    - Possible Ground loops
    - Will probably work, just not according to spec

### Dimension Errors
* OK.
* USB will lay outside of the board.




# John’s Notes:


Concept of operation
Taking a door lock, augmenting it with attachment that allows door to open with RFID card to open door 
Battery powered
Servo actuator

Schematic:
Board needs black background
Power
Battery:
What is voltage?
3 AA batteries (4.5 V) (label this)
D4 is reverse voltage protection
Linear regulator, enable pulled high
P4 is floating, if we want it put test point
USB Interface
X4 USB adapter does not have shield, should not be attached to ground
Reset should be left floating
RTS and CTS is used as reset
We are just assuming that it works… 

Processor
Unused pins are used for debug
Connect pins physically, not just with label

RFID
I^2C and SPI are attached
One has to be chipselect (SDA likely?)
If this works we can leave it, but it raises red flags
If I^2C use pullups
If SPY use ??
J3 is an open button to lock/unlock (should add label)

ERC check:

No supply for implicit power pin U1G$2 TP
D2 should have a name,
button should also have a name

Invoke:  (CP2104)
Thermal slug
Thermal ground
Solved issue


Board layout

Decent ground via stitching
More ground vias by ESP
Move things around t input more ground vias
The board is packed, so make sure to have a straight path to ground

USB connector shield is connected to ground
Might get ground loops
Consider better USB implementation
If shields are separate, use 100 nF capacitors to connect shields to ground
He likes it

DRC errors from USB aren’t  bad, they are expected. Approve them



USB Placement Notes:


This forum asks a somewhat similar question to our USB setup:
https://forum.sparkfun.com/viewtopic.php?t=22122

USB should not be connected to signal ground.
Adding small capacitors (~ 100nF) between shield and ground reduces EMI problems.






=======================================================================
# Design Review With Team 9: Short, Nickolas; Taylor, Stevie; Xaybanha, Calvin; Zhou, Zeming
# On 11/16/20
=======================================================================

# John’s Notes:

Thermal pad is under the chip

RFID sensor uses SPI protocol 

Servo throws deadbolt on door

Voltage references point up

Ground points down

Nets are labeled

Pull down/up resistors are there where appropriate

Prototyped to as much as possible with what’s available

Using 13.52 HF NFC chip for frequency



via under thermal ground is to allow heat to transfer to other side of the board

A lot of right angle or 45 degree traces. Right angle is not good for high frequency (MOSI an MISO)
recommends possibly making it 45 degree angles

Other test pins on the board?
No, not enough room
What type of test pins are we using?
We just have a pad, not a hook.
Consider adding hooks

Good stitching
Wide power traces
Passed ERC
Pins can be left floating, don’t need to be tied to ground

Antenna is a plane
Ground planes are removed from antenna
Plenty of space given to antenna, polygon area

deadbolt can be actuated by servo by removing spring in door
Spring does not hold door into position, only provides nice feedback









