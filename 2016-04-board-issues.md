EE issues witn 2016-04 board build

[x] Right hand side- ATTiny pin 18 should be +5V, not ground. The schematic is incorrect and does not match the left hand side. Right now, we're pulling AVCC to ground, causing the ATTiny to try to pull as much juice as it can through internal connections and sink it straight to ground. 

[x] ALL diodes are placed backwards from how they appear in the schematic. The only one that's a catastrophic problem is the diode on the reset line that forces RESET to stay high.

[x] The series resistor on the reset line should be on the other side of the reset switch per Atmel. look at the avr tech note http://www.atmel.com/Images/Atmel-2521-AVR-Hardware-Design-Considerations_ApplicationNote_AVR042.pdf - Figures 2-1 and 2-2 on reset lines and change to that rather than what's in the schematic.

[x] It looks like VDDA on the i2c transceiver should be tied to the same voltage supply as the other i2c devices it's talking to .If VDDA on the I2C transceiver were tied to the atmega and attiny's voltages, on the left, the level translator should work better.

[x] No test points for LEDs - turns out they're useful.

[x] LED Footprints - Pin 1 should move _outside_ the footprint covered by the component

~[ ] Jacob would rather ATTiny on right hand had its own current source separate from LED source. There's not a lot we can do there.
