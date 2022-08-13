# Rom2k40
## Please note! This is currently a WIP

<img src="https://github.com/mengstr/Rom2k40/blob/main/Images/Rom2k40-Side.png" height="350">

This is a EPROM emulator that supports standard EPROM in sizes from the 2716 up to 27512. Upload of new contents into the emulated EPROM is done over a serial link.

Emulating 2716 and 2732 which are 24-pin devices requires a solder jumper at the bottom to be bridged to power the board with +5v from the correct pin.

The USB of the RP2040 is not connected so the firmware must be uploaded over the SWD interface that is broken out into the same connector as the serial port.

The two rows of 14-pin headers that goes to the target board does NOT have a standard 600mil distance! Since standard sockets can't take the regular square pinheader pins I've designed this board to have the pinheaders to be soldered ontop of a real 28-pin device, like a broken/bas EPROM or any other 28-pin DIP. It probably works best using an EPROM since the bond wires to the die of the chip must be severed.  I'm not sure how it would be done on another type of chip, but if it's plastic it could be possible to just drill a hole in the middle straight through it and then check that all pins are is isolated from eachother.

### PCB specs

The PCB is 40 x 19mm (1.6 x 0.75") using a four layer PCB with 0.2mm vias having a 0.2mm annular ring giving a total ring size of 0.6mm. Track with/spacing is mostly 125/125um (4.9 mil). This is in accordance to the Aisler 4-layer specification.

### Schematic

![PDF schematic availabe here](https://github.com/mengstr/Rom2k40/blob/main/Images/Rom2K40.pdf)

### Bill of materials and substitutions

Interactive ![BOM](http://htmlpreview.github.io/?https://github.com/mengstr/Rom2k40/blob/main/Bom/ibom.html)

The MOSFET transistor could probably be replaced with a 2N7002 with a bit of luck, but they can be hard to drive fully from a 3.3 volt device.

The 3.3 volt VREG could be replaced with any other device with a similar pinout and a output current of 150mA (needs to be verified).

The FLASH memory could br replaced with any SO-8 device that is compatible with the RP2040 and also have enough memory for both the emulated EPROM and the firmware. Since a 27512 is the largest EPROM emulated a 1Mbit FLASh should be suffice. I can't imagine that the firmware will take more than 64Kbyte.




