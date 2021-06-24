This is an incomplete list of what we're considering for Model 01 design changes, as well as the current status of those changes.

Tasks are specific engineering actions to take. They have action verbs
Tasks make design changes happen.

Design Changes describe intended outcomes. Every design change will use a key word as described below:

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL
NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and
"OPTIONAL" in this document are to be interpreted as described in
RFC 2119.



# Mechanical

## Specification and design

- [ ] All specifications and parts for the keyboard MUST be metric. Nothing should be specified in inches, feet, pounds, or ounces. The Kickstarter prototypes used a mix of metric and imperial screws.

## Bottom plate

- [ ] We MUST replace the metal bottom plates with ABS or ABS+PC bottom plates.
- [ ] The new bottom plates MUST be possible to remove for service
- [ ] The new bottom plates MUST connect securely to the wooden enclosure
- [ ] The new bottom plates MUST contain a 1/4-20 tripod mount at their center of gravity
- [ ] The new bottom plates MUST connect securely to the PCB + keyplate assembly.
- [ ] The new bottom plates SHOULD provide a protective outer housing for the USB Type C connector (Rather than the existing thin, small wooden cutout which is prone to breakage)
- [ ] The new bottom plates SHOULD help secure and anchor the RJ45 jacks, protecting their outside metal shielding
- [ ] The new bottom plates SHOULD be colored black

## Keyplate

- [ ] We SHOULD devise a new scheme for PCB-to-keyplate mounting. The current scheme using PEM standoffs and screws can damage PCBs if screws overtightened. Retaining clips may be an option. A bent-metal key plate that acts as its own standoff and assembly locating system is another.

- [ ] We MUST modify the keyplate (or PCB, but preferably the keyplate) to make it easy to connect the left hand Attiny ISCP.

# Enclosure changes

- [ ] The enclosure MUST be redesigned to anticipate drops and other stresses on the wood. The current screw cutouts on the inside of the wooden enclosure appear to have been a factor in a drop test failure. The wood flexed and it looks like a pan-head screw slammed into the wood as it flexed, contributing to the enclosure cracking. Possible solutions include thickening all the thinner parts of the side walls of the wood and changing the direction of the wood grain used. 
  
- [ ] The curve between the two butterfly wings on each hand MUST be adjusted to actually be tangent to adjacent contours. Right now, there's a weird angle discontinuity that's bugging jesse

- [ ] Bottom plate screw mountings MUST be adjusted allow a looser tolerance when aligning wooden enclosure to bottom plate



## Feet

- [ ] We MUST design feet for the keyboard.

- [ ] When the two halves of the keyboard are not connected by a center bar, the feet MUST allow the user to adjust the position and angle of each half of the keyboard independently.

- [ ] When the two halves of the keyboard are connected by a center bar, the feet MUST allow the user to keep the keyboard flat on the surface the keyboard is placed on or to tilt the keyboard at a 10 degree negative tilt or a 10 degree positive tilt. An ideal solution SHOULD let the user tilt the keyboard at a 5 degree negative tilt or a 5 degree positive tilt. An ideal solution MAY allow the user to tilt the keyboard at an arbitrary angle.

- [ ] When using the two halves of the keyboard without a center bar, the feet MUST allow the user to use the keyboard flat on the surface it is placed on or to tent one or both halves of the keyboard at a 5 degree angle relative to that surface. The feet SHOULD allow the user to tent either or both halves of the keyboard to 10 degrees relative to the surface the keyboard is placed on. An ideal solution MAY allow the user to tent one or both halves of the keyboard at an arbitrary angle. Going further than 10 degrees would be ideal.

- [ ] When using the feet in a supported configuration, the keyboard's center of gravity MUST be low enough that a typist resting their palms on it can't destabilize the keyboard.

- [ ] The feet MUST have a non-skid, non-marking coating on any surface where they might touch a surface the keyboard is placed on

- [ ] When not in use, the feet SHOULD fold away into the bottom plate

## Interconnect mechanism

- [ ] The interconnect mechanism SHOULD be able to be aligned by the user without looking or flipping the keyboard upside down. 
- [ ] The interconnect mechanism should not easily slide apart when the keyboard is picked up with one hand by the user.
- [ ] The replacment solution SHOULD be designed to make it as easy as possible for a hobbyist to create replacement center bars at other tent angles or separation distances at home. 
- [ ] The interconnect mechanism SHOULD have some sort of locking mechanism, such as retaining pins + magnet or spring-mounted bearing. 
    
- [ ] If the interconnect mechanism has removeable parts, they SHOULD have some sort of coating, edging or bumper so that they don't clatter when dropped. The current center bars make a very loud noise when they fall from a table or slip out of a user's hands.

# Keycap changes

- [ ] left and right palm keys MUST have a symmetrical outline and keyswitch mount position. Verify this
- [ ] Palm keys MAY be more comfortable if their bumps were wider and 2-3mm higher. Test this.

- [ ] We MUST verify that the keystem sizes are all identical and are easy to insert into keys and difficult, but not impossible to remove. (2.25mm x 4.4mm x 3mm deep with a 45 degree chamfer on the end of the stem)

- [ ] We MUST verify that the keycaps won't rub against each other or the sidewalls of the keyboard, especially the thumb and palm keys.  

- [ ] We MUST verify that the homing bumps on pinkie, index and thumb are the same size

- [ ] We MAY make the homing bumps slightly smaller.

- [ ] We MUST finalize the default QWERTY key legend placement after discussions with the manufacturer
  

# Electronics changes

## Electrical Design

## PCB Layout

- [ ] We SHOULD optimize our PCB geometry for mass production.

# Software changes

- [ ] We MUST rewrite our software and firmware from scratch. No, seriously The existing firmware was all proof of concept.

