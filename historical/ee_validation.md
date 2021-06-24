# EE validation 

(Some of this has been done, but needs to be checked systematically)

- [ ] Check sizing on pull-up resistors for I2C.
- [ ] Verify trace widths and layout
- [ ] Verify silkscreen placement
- [ ] Make sure logo and backside silkscreen look nice
- [ ] Verify differential trace length for:
    - [ ] usb in
    - [ ] i2c inter hand diff traces left
    - [ ] i2c inter hand diff traces right
- [ ] Discuss LED mounting with mfg

- [ ] Make sure the input voltage on the transceiver is the same as on the IC
- [ ] Make sure all the ICs run at the same voltage level - make sure they have enough power.
[ ] Test brownouts: drive LEDs to max - check voltage. if the leds are all pulled as high as possible, what is VLED - is it above 3.3v? is it above what the attiny needs to operate? can the attiny still run or does it brown out? Ditto the I2C transceiver.
